---
project: tauri-egui
stars: 376
description: null
url: https://github.com/tauri-apps/tauri-egui
---

tauri-egui
==========

Dependency
----------

Component

Description

Version

**tauri**

runtime core

**egui**

immediate mode GUI library for Rust

**tao**

cross-platform application window creation library in Rust

**glutin**

low-level library for OpenGL context creation, written in pure Rust.

About tauri-egui
----------------

`tauri-egui` is a Tauri plugin for using the `egui library` in a Tauri application via `glutin`. `egui` is a pure Rust GUI library that runs natively, recommended by the Tauri team for secure contexts such as password and secret interfaces.

Example
-------

use tauri::Manager;
use tauri\_egui::{eframe, egui, EguiPluginBuilder, EguiPluginHandle};

struct LoginApp {
  password: String,
  on\_submit: Box<dyn Fn(&str) -> bool + Send\>,
}

impl LoginApp {
  fn new<F: Fn(&str) -> bool + Send + 'static\>(
    ctx: &eframe::CreationContext,
    on\_submit: F,
  ) -> Self {
    Self {
      password: "".into(),
      on\_submit: Box::new(on\_submit),
    }
  }
}

impl eframe::App for LoginApp {
  fn update(&mut self, ctx: &egui::Context, frame: &mut eframe::Frame) {
    let LoginApp {
      password,
      on\_submit,
    } = self;
    egui::CentralPanel::default().show(ctx, |ui| {
      ui.label("Enter your password");
      let textfield = ui.add\_sized(
        \[ui.available\_width(), 24.\],
        egui::TextEdit::singleline(password).password(true),
      );
      let button = ui.button("Submit");
      if (textfield.lost\_focus() && ui.input().key\_pressed(egui::Key::Enter)) || button.clicked() {
        if on\_submit(password) {
          frame.close();
        }
      }
    });
  }
}

fn main() {
  tauri::Builder::default()
    .setup(|app| {
      app.wry\_plugin(EguiPluginBuilder::new(app.handle()));
      let egui\_handle = app.state::<EguiPluginHandle\>();

      let native\_options = eframe::NativeOptions {
        drag\_and\_drop\_support: true,
        initial\_window\_size: Some(\[1280.0, 1024.0\].into()),
        ..Default::default()
      };

      let \_window = egui\_handle
        .create\_window(
          "native-window".to\_string(),
          Box::new(|cc| Box::new(LoginApp::new(cc, |pwd| pwd == "tauriisawesome"))),
          "Login".into(),
          native\_options,
        )
        .unwrap();

      Ok(())
    })
    .run(tauri::generate\_context!("examples/demo/tauri.conf.json"))
    .expect("error while building tauri application");
}

Semver
------

**tauri-egui** is following Semantic Versioning 2.0.

Licenses
--------

Code: (c) 2019 - 2022 - The Tauri Programme within The Commons Conservancy.

MIT or MIT/Apache 2.0 where applicable.
