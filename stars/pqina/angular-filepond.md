---
project: angular-filepond
stars: 60
description: 🔌 A handy FilePond adapter component for Angular
url: https://github.com/pqina/angular-filepond
---

**This adapter has been deprecated, please use ngx-filepond instead.**

* * *

Angular FilePond
================

Angular FilePond is a handy adapter component for FilePond, a JavaScript library that can upload anything you throw at it, optimizes images for faster uploads, and offers a great, accessible, silky smooth user experience.

Installation
------------

Install FilePond component from npm.

npm install angular-filepond --save

Add `FilePond` to an NgModule and if needed register any plugins. Please note that plugins need to be installed from npm separately.

import { FilePond, registerPlugin } from 'angular-filepond';

// Registering plugins
import FilePondPluginFileValidateType from 'filepond-plugin-file-validate-type/dist/filepond-plugin-file-validate-type.esm';
registerPlugin(FilePondPluginFileValidateType);

// Adding FilePond to imports
@NgModule({
  imports: \[
    FilePond
  \]
})

export class AppModule { }

Add the FilePond stylesheet to your `angular-cli.json` build script.

"styles": \[
  "styles.css",
  "../node\_modules/filepond/dist/filepond.min.css"
\]

Now FilePond can be used in your templates.

import { Component, ViewChild } from '@angular/core';

@Component({
  selector: 'app-root',
  template: \`
    <div class="root">
        <FilePond #myPond 
            name="my-name" 
            className="my-class" 
            labelIdle="Drop files here..."
            allowMultiple="true"
            acceptedFileTypes="image/jpeg, image/png"
            server="/api"
            \[files\]="myFiles" 
            (oninit)="handleFilePondInit()">
        </FilePond>
    </div>
  \`
})

export class AppComponent {

  myFiles \= \['index.html'\];

  // Allows us to get a reference to the FilePond instance
  @ViewChild('myPond') myPond: any;

  handleFilePondInit \= () \=> {

    console.log('FilePond has initialised');

    // FilePond instance methods are available on \`this.myPond\`

  }
}

Read the docs for more information
