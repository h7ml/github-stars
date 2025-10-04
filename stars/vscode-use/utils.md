---
project: utils
stars: 130
description: vscode lodash
url: https://github.com/vscode-use/utils
---

English | 简体中文

🐰 vscode use has a secondary encapsulation of the vscode api, providing a large number of streamlined and practical functions, and making the function names closer to the actual meaning, just like lodash in vscode.

📘 Documentation
----------------

📍 Install
----------

```
npm i @vscode-use/utils -d
```

Recommended VSCode Starter
--------------------------

-   https://github.com/Simon-He95/vitesse-vscode

### Example

📝 Api
------

-   registerCommand： _**Registration instructions**_
-   executeCommand： _**Trigger instructions**_
-   getConfiguration： _**get workspace configuration**_
-   message {type:'info'|'error',message:string,buttons:\['ok'\]}： _**Pop up message**_
-   openFile： _**Open a file.**_
-   addEventListener： _**Listen to file switching, terminal, content change, add, delete and other events in vscode**_
-   createTerminal： _**Quickly create a terminal**_
-   createCompletionItem： _**Generate the prompt content of registerCompletionItemProvider**_
-   registerCompletionItemProvider： _**Generate the corresponding prompt according to the input**_
-   isDark： _**Determine whether the current vscode theme is dark**_
-   getSelection： _**Get the information of the line where the current mouse is located**_
-   getActiveTextEditorLanguageId： _**Get a type of the current file javascriptreact | typescriptreact | vue, etc.**_
-   createProgress： _**Create an execution progress bar in vscode**_
-   registerInlayHintsProvider： _**Give a hint similar to copilot.**_
-   getCopyText： _**Read the pasteboard Content.**_
-   setCopyText： _**Plug the content into the pasteboard.**_
-   updateText： _**Modify the text content**_
-   jumpToLine： _**Open a file and jump to a certain line**_
-   createBottomBar： _**Create the bottom bar button**_
-   nextTick： _**Create the bottom bar button**_
-   createSquare： _**Create a square block**_
-   watchFiles： _**Monitor changes in file content and deletion**_
-   createEvents： _**Tools for subscribing to event communication**_
-   getActiveText： _**Get the text content of the current activation tab**_
-   fold： _**fold code**_
-   unFold： _**unfold code**_
-   registerDefinitionProvider： _**It provides option + click to achieve the function of fast jump.**_
-   registerHoverProvider： _**Provide a callback for mouse hover**_
-   registerCodeActionsProvider _**Registered Code Action Provider**_
-   openExternalUrl： _**Open the external url in the browser**_
-   getLineText： _**Get the text of a certain line**_
-   useTheme： _**Theme Configuration and Operatation**_
-   isInPosition： _**Determine whether one area is a sub-area of another**_
-   getCurrentFileUrl： _**Get the path of the current activation file**_
-   createInput： _**Create an input box**_
-   getLocale： _**Get the local language environment**_
-   rename： _**Quickly rename files**_
-   createDefinitionLocation _**Create jump address data after left-clicking after pressing option**_
-   setStyle _**Add style to a certain area**_
-   createStyle _**Create Style**_
-   getActiveTextEditor _**Get the currently activated editor**_
-   getKeyWords _**Get the keywords at the position**_
-   setCommandParams _**Set the click command parameter of MarkdownString**_
-   getOffsetFromPosition _**Get the offset from position**_
-   getRootPath _**Get the root directory path of the project**_
-   registerCodeLensProvider _**Register the text button at the head of the text and tie the event.**_
-   createCodeLens _**Quickly create items in provideCodeLenses**_
-   saveFile _**Save the file**_
-   createStyleAnimation _**Add style animation**_
-   createStyleAnimations _**Add style animation group**_
-   getWordRangeAtPosition _**Get the area of ​​keywords for your location**_

📖 @vscode-use/utils api description
------------------------------------

### The registration instruction needs to be declared in package.json. A prompt pops up in the lower right corner.

```
registerCommand('vscode-use.hello', () => {
  message.info('Hello World!')
})
```

### The registration instruction needs to be declared in package.json. An error prompt pops up in the lower right corner.

```
registerCommand('vscode-use.error', () => {
  message.error('Hello World!')
})
```

### Registration instructions need to declare in package.json to open Baidu

```
registerCommand('vscode-use.openExternalUrl', () => {
  openExternalUrl('http://www.baidu.com')
})
```

### Get the current language

```
const isZh = getLocale().includes('zh')
message.info(`当前语言：${isZh ? '中文' : '英文'}`)
```

### Monitor and switch the active text editor

```
addEventListener('activeText-change', (e) => {})
```

### Monitor login status changes

```
addEventListener('auth-change', (e) => {})
```

### Monitoring configuration changes (including: plug-in configuration, user configuration, workspace configuration)

```
addEventListener('config-change', (e) => {})
```

### Monitor editor visibility changes

```
addEventListener('editor-visible', (e) => {})
```

### Monitor file creation

```
addEventListener('file-create', (e) => {})
```

### Monitoring file deletion

```
addEventListener('file-delete', (e) => {})
```

### Monitor folder creation and deletion

```
addEventListener('folder-change', (e) => {})
```

### Listen to file renaming

```
addEventListener('rename', (e) => {})
```

### Monitor the changes of selected content

```
addEventListener('selection-change', (e) => {})
```

### Monitor terminal changes

```
addEventListener('terminal-change', (e) => {})
```

### Monitoring terminal is closed

```
addEventListener('terminal-close', (e) => {})
```

### Monitoring terminal creation

```
addEventListener('terminal-open', (e) => {})
```

### Monitor text modifications

```
addEventListener('text-change', (e) => {})
```

### Monitor new text

```
addEventListener('text-open', (e) => {})
```

### Monitor text saving

```
addEventListener('text-save', (e) => {})
```

### Monitor text visibility changes

```
addEventListener('text-visible-change', (e) => {})
```

### Monitor theme changes

```
addEventListener('theme-change', (e) => {})
```

### Jump to a certain line of a file

```
jumpToLine(10, 'path/Uri')
```

### Collapse all lines between the start line and the end line

```
onFold([
  createRange([1, 0], [5, 0]),
  createRange([5, 0], [10, 0])
])
```

### Expand all lines between the start line and the end line

```
unFold([
  createRange([1, 0], [5, 0]),
  createRange([5, 0], [10, 0])
])
```

### Update text

```
updateText(edit=>{
//Insert text in the first line
edit.insert(new vscode.Position(0, 0), 'Hello World!')

// Delete the first 5 characters of the first line
edit.delete(new vscode.Range(new vscode.Position(0, 0), new vscode.Position(0, 5)))

// Replace the first 5 characters of the first line with Hello World!
edit.replace(new vscode.Range(new vscode.Position(0, 0), new vscode.Position(0, 5)), 'Hello World!')
})
```

### Get the currently active editor text

```
const activeText = getActiveText()
```

### Get the text of a certain line

```
const lineText = getLineText(0)
```

### Read config

```
const mode1 = getConfiguration('vscode-use').get('mode')
const mode2 = getConfiguration('vscode-use.mode')
```

### Update config

```
setConfiguration('vscode-use.mode', 'dev')
```

### Create terminal

```
createTerminal('test')
```

### Create bottom bar

```
createBottomBar({
  position: 'left',
  text: 'I am the bottom bar',
  color: '#fff',
  backgroundColor: '#000',
})
```

### Get the position based on offset

```
const pos = getPosition(100)
```

### Get the content of the copy

```
getCopyText().then(text=>{})
```

### Write content to the clipboard

```
setCopyText('Hello World!')
```

### Get the path of the currently active text

```
const currentFileUrl = getCurrentFileUrl()
```

### Set selected content

```
 setSelection([0, 0], [0, 5])
```

### Set multiple selections

```
setSelections([{
  start: [0, 0],
  end: [0, 5],
  position: 'left' // Control cursor position
}, {
  start: [1, 0],
  end: [1, 5],
  position: 'right'
}])
```

### Monitor file changes

```
watchFiles('filepath', (e) => {})
```

### Create a progress bar

```
createProgress({
  title: 'Progress Bar',
  async done(report) {
    report({
      message: 'Progress bar 10% completed',
      increment: 10
    })
    setTimeout(() => {
      report({
        message: 'Progress bar completed 50',
        increment: 50
      })
    })
  }
})
```

### Create a selection box

```
createSelect(['vue','react','svelte','solid']).then((res)=>{})
```

### Listen to the event of hover element

```
registerHoverProvider('vue', (e) => {})
```

### Monitor the click jump position when the option key is pressed.

```
registerDefinitionProvider('vue', (e) => {})
```

### Get topic-related APIs

```
const { getCurrentTheme, getAllTheme, setTheme, } = useTheme()
```

### Get the language of the currently active text

```
const language = getActiveTextEditorLanguageId() // vue
```

### Rename file

```
rename('url', 'newUrl')
```

### nextTick, some operations after file changes need to wait for the file to change before executing

```
 nextTick(()=>{})
```

### Add style

```
setStyle(createStyle({
  backgroundColor: 'yellow',
  border: '1px solid red'
}), createRange([0, 0], [0, 10]))
```

### Create input box

```
createInput({
  title: 'I am an input box',
  placeHolder: 'Please enter content',
  value: ''
})
```

### getActiveTextEditor

```
const activeTextEditor = getActiveTextEditor()
```

### getKeyWords

```
const keyWords = getKeyWords(position)
```

### Set the click command parameter of MarkdownString

```
const md = new vscode.MarkdownString()
md.isTrusted = true
md.supportHtml = true
const commandUri = `command:a.b?${setCommandParams(['params1', 'params2'])}`
md.appendMarkdown(`[🦘](${commandUri})`);
```

### getOffsetFromPosition

```
const offset = getOffsetFromPosition(position) // Get the offset of the current text and location
const offset = getOffsetFromPosition(position,code) // 获取指定code，位置的offset
```

License
-------

MIT License © 2022 Simon He
