---
project: cz-message-helper
stars: 2
description: A commit message helper for commitizen
url: https://github.com/linpengteng/cz-message-helper
---

Commit message helper for commitizen
====================================

> A commit message helper of Commitizen plugin.  
> Note that you can achieve consistent commit messages.  
> Note that you can customizable commit message pattern.

  

Chinese README.md
=================

> https://github.com/linpengteng/cz-message-helper/blob/main/README.zh-CN.md

  

Installation
============

> Since cz-message-helper is a plug-in for committen. you need to install the following dependencies
> 
> -   commitizen ------------------------- Standardize your commit message
> -   @commitlint/cli --------------------- A commitizen cli
> -   @commitlint/config-conventional ---- A commit message specification rule
> -   husky ------------------------------- Brefore git commit lint commit message

  # commitizen
  pnpm add commitizen -g
  yarn global add commitizen


  # @commitlint/cli @commitlint/config-conventional
  pnpm add @commitlint/cli @commitlint/config-conventional -D
  yarn add @commitlint/cli @commitlint/config-conventional -D


  # husky
  pnpm add husky -D
  yarn add husky -D


  # cz-message-helper
  pnpm add cz-message-helper -D
  yarn add cz-message-helper -D

  

Usage
=====

1.  Add commitizen configurate in package.json

{
  "config": {
    "cz-message-helper": {
      "config": ".cz-message.cjs"
    },
    "commitizen": {
      "path": "node\_modules/cz-message-helper"
    }
  }
}

  

1.  Create `.cz-message.cjs` configuration file in the project root directory

module.exports \= {
  language: 'en' // options: en | cn
}

  

1.  Create `commitlint.config.js` configuration file in the project root directory

module.exports \= {
  extends: \['@commitlint/config-conventional'\],
  rules: {
    'type-enum': \[
      2,
      'always',
      \[
        'fix',
        'feat',
        'begin',
        'docs',
        'style',
        'refactor',
        'chore',
        'perf',
        'test',
        'merge',
        'revert',
        'wip'
      \]
    \],
    'type-case': \[0\],
    'scope-case': \[0\],
    'subject-case': \[0\],
    'header-case': \[0\],
    'body-case': \[0\],
    'type-empty': \[2, 'never'\],
    'scope-empty': \[0\],
    'subject-empty': \[2, 'never'\],
    'body-empty': \[0\],
    'subject-full-stop': \[0\],
    'header-full-stop': \[0\],
    'body-full-stop': \[0\],
    'header-max-length': \[2, 'always', 100\],
    'body-leading-blank': \[2, 'always'\],
    'footer-leading-blank': \[2, 'always'\]
  }
}

  

1.  Install husky And add git commit-msg hook

  # step1
  npx husky install  

  # step2 
  npx husky add .husky/commit-msg 'npx --no-install commitlint --edit $1'

  

1.  Good, You can use by `git add .` and `git cz`

  

More configuration options -- `.cz-message.cjs`
===============================================

module.exports \= {
  questions: \[
    {
      type: 'list',
      name: 'type',
      message: 'Please select the type of change that you\\'re committing:',
      choices: \[
        { value: 'fix', name: 'fix: -------- A bug fix' },
        { value: 'feat', name: 'feat: ------- A new feature' },
        { value: 'begin', name: 'begin: ------ Begin new repository' },
        { value: 'docs', name: 'docs: ------- Documentation only changes' },
        { value: 'style', name: 'style: ------ Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)' },
        { value: 'chore', name: 'chore: ------ Changes to the build process or auxiliary tools and libraries such as documentation generation' },
        { value: 'refactor', name: 'refactor: --- A code change that neither fixes a bug nor adds a feature' },
        { value: 'perf', name: 'perf: ------- A code change that improves performance' },
        { value: 'test', name: 'test: ------- Add Test Unit' },
        { value: 'revert', name: 'revert: ----- Revert to a commit' },
        { value: 'merge', name: 'merge: ------ Merge from branches' },
        { value: 'wip', name: 'wip: -------- Work in progress' }
      \]
    },

    {
      type: 'list',
      name: 'scope',
      message: 'Please select the SCOPE of this change (optional):',
      choices() {
        return \[
          { name: 'empty', value: false },
          { name: 'custom', value: 'custom' }
        \]
      }
    },

    {
      type: 'input',
      name: 'customScope',
      message: 'Please input the custom SCOPE of this change:',
      when(answers) {
        return answers.scope \=== 'custom'
      },
      filter(value, answers) {
        answers.scope \= value || ''
        return value || ''
      }
    },

    {
      type: 'input',
      name: 'subject',
      message: 'Please write a SHORT tense description of the change(word number less than 72):',
      validate(value) {
        if (!value.trim()) {
          return 'Cannot be empty'
        }

        return value.length \> 72
          ? \`Exceed limit: 72\`
          : true
      }
    },

    {
      type: 'input',
      name: 'body',
      message: 'Please provide a LONGER description of the change (optional). Use "\\\\n" to break new line:'
    },

    {
      type: 'input',
      name: 'breaking',
      message: 'Please list any BREAKING CHANGES (optional):',
      when(answers) {
        return /^(\\:\[a\-z0\-9A\-Z\_\-\]+(\\:)(\\s\*))?(feat|fix)(\\2\\s\*)?$/.test(answers.type.toLowerCase())
      }
    },

    {
      type: 'input',
      name: 'footer',
      message: 'Please list any ISSUES CLOSED by this change (optional). Eg: #31, #34:'
    }
  \],

  templater: (answers, wrap) \=> {
    let template \= ''

    template += answers.type ? \`${answers.type}\` : \`\`
    template += answers.scope ? \`(${answers.scope})\` : \`\`
    template += answers.subject ? \`: ${answers.subject}\` : \`\`
    template += answers.body ? \`\\n\\n${wrap(answers.body)}\` : \`\`
    template += answers.breaking ? \`\\n\\nBREAKING CHANGE: ${wrap(answers.breaking)}\` : \`\`
    template += answers.footer ? \`\\n\\nISSUES CLOSED: ${wrap(answers.footer)}\` : \`\`

    return template
  },

  language: 'en'
}

> Note
> 
> 1.  templater --- Template used to generate message
> 2.  questions --- About questions options and description look Inquirer
> 3.  language ---- The preset options only support Chinese and English, Invalidate when customizing a questions

  

Licence
=======

> MIT
