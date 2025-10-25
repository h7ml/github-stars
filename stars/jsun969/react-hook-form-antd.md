---
project: react-hook-form-antd
stars: 75
description: 📋🐜 Master your Ant Design form with React Hook Form! 用 React Hook Form 拿捏你的 Ant Design 表单！
url: https://github.com/jsun969/react-hook-form-antd
---

📋 React Hook Form Antd 🐜
==========================

Master your Ant Design form with React Hook Form!

English | 简体中文

📜 Requirement
--------------

-   react-hook-form `^7`
-   antd `^5`

🕶 Example
----------

EXAMPLE

📦 Installation
---------------

npm install react-hook-form-antd

🎯 Quickstart
-------------

You may have an original antd form like below

Show code

<Form onFinish\={onFinish}\>
	<Form.Item
		label\="Username"
		name\="username"
		rules\={\[
			{ required: true, message: 'Required' },
			{ max: 15, message: 'Username should be less than 15 characters' },
		\]}
	\>
		<Input />
	</Form.Item\>
	<Form.Item
		label\="Password"
		name\="password"
		rules\={\[{ required: true, message: 'Required' }\]}
	\>
		<Input.Password />
	</Form.Item\>
	<Form.Item name\="remember" valuePropName\="checked"\>
		<Checkbox\>Remember me</Checkbox\>
	</Form.Item\>
	<Form.Item\>
		<Button type\="primary" htmlType\="submit"\>
			Submit
		</Button\>
	</Form.Item\>
</Form\>

Check the EXAMPLE for this form after using `react-hook-form-antd`!

All you need to do:

1.  Use `useForm` from `react-hook-form` and get `control`
2.  Use `FormItem` from `react-hook-form-antd` instead of `Form.Item`
    -   Pass `control` to all `FormItem` (Field names can be inferred by `control` 😎)
    -   Remove `rules` and use react hook form resolver instead (You can use schema from any validation libraries 🤩)
    -   Use `handleSubmit` in `onFinish`
3.  Enjoy! 🎉

🕹 API
------

### 🔗 `FormItem`

> Ant Design `Form.Item` API

A component instead of `Form.Item` in antd. It has inherited all props from `Form.Item` except `rules` `validateStatus` (If you need rules, please use react hook form resolver instead)

Added and modified props:

Prop

Type

Description

`control`

Control

control object from `useForm`

`name`

string

form field name

🚧 Known Issues
---------------

#### TypeError: elm.focus is not a function

When using an upload component, set `shouldFocusError: false` in your `useForm` configuration. This will prevent React Hook Form from trying to focus on the error, effectively resolving the issue.

👥 Contributors
---------------

Thanks goes to these wonderful people (emoji key):

  
**Yeyang (Justin) Sun**  
💻 🤔 🚧 📖

  
**Jakub Szewczyk**  
💻

  
**Dino Muharemagić**  
💻 🐛

  
**avegatolber**  
💻 🐛

  
**Ahmed Rowaihi**  
💻

  
**Yorman Rodriguez**  
🐛

  
**Sinan**  
📖

  
**nagamejun**  
🐛 💻

  
**Andrey**  
🐛

  
**ray-overjet**  
🚇

This project follows the all-contributors specification. Contributions of any kind welcome!
