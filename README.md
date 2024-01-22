# Express Library

- [Express Library](#express-library)
  - [Build Steps](#build-steps)
    - [Auto Set up](#auto-set-up)
    - [Dev Friendly Environment](#dev-friendly-environment)
  - [Pre-requirement Knowledge \& Concept](#pre-requirement-knowledge--concept)
    - [Mongoose Tutorial](#mongoose-tutorial)
    - [MVC(Model-View-Controller) Pattern](#mvcmodel-view-controller-pattern)
    - [Form Handling](#form-handling)
    - [Pug essential tutorial](#pug-essential-tutorial)
  - [Other Notes](#other-notes)
      - [Why I lose code hint node.js module!!](#why-i-lose-code-hint-nodejs-module)
      - [Use "express-async-handler" without try...catch](#use-express-async-handler-without-trycatch)
      - [Use "express-validator" to validate/sanitize form data](#use-express-validator-to-validatesanitize-form-data)
      - [Use gzip/deflate compression for responses](#use-gzipdeflate-compression-for-responses)
      - [Use Helmet to protect against well known vulnerabilities](#use-helmet-to-protect-against-well-known-vulnerabilities)
      - [Production Best Practices: Security](#production-best-practices-security)

---

## Build Steps

### Auto Set up

1. `npx express-generator --view=pug`
   > `jade` have already deprecated.
2. `npm install` to install dependencies
3. if you are in **powershell**: `SET DEBUG=[FolderName]:* ; npm start` or **cmd**: `SET DEBUG=[FolderName]:* & npm start`

<br>

### Dev Friendly Environment

Your every changes can not be seen soon iff restart server. Configure following setting to help your developing process easier.

1. `npm install --save-dev nodemon`
2. In `package.json`, edit as below
   > ```javascript =
   > "scripts": {
   >   "start": "node ./bin/www",
   >   "devstart": "nodemon ./bin/www"
   > },
   > ```
3. run `npm run devstart` instead

> Make sure your ip address is in `whitelist` of MongoDB Atlas.

---

## Pre-requirement Knowledge & Concept

### Mongoose Tutorial

Mongoose is an ORM on MongoDB. (Good for using schema, and of course, id key)

[Tutorial Link](https://developer.mozilla.org/zh-TW/docs/Learn/Server-side/Express_Nodejs/mongoose)

<br>

### MVC(Model-View-Controller) Pattern

<img src='https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/routes/mvc_express.png'>

<br>

### Form Handling

<img src='https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/forms/web_server_form_handling.png'>

<br>

### Pug essential tutorial

[Template primer](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/Displaying_data/Template_primer)

> Other quick notes of Pug
>
> - 'extends' means to use `layout.pug` as base template ant it must be placed in first line
> - only named blocks and mixins can appear at the top level of an extending template
> - use '[tag]=', for example 'h1=', to treat the following text as javascript expression.
> - `block` tag is used to mark up sections of content that may be replaced in a derived template (if the block is not redefined then its implementation in the base class is used). For example, 'block content' replaces 'content mark base on base template
> - '[tag]!=' means any HTML tags or special characters within the error message will be rendered as raw HTML
> - if you want to compare variable with `undefined`, it's necessary to put `undefined` before variable. Such as `(undefine===VARIABLE) ?`

---

## Other Notes

#### Why I lose code hint node.js module!!

> run `npm i @types/express`

#### Use "express-async-handler" without try...catch

[express-async-handler](https://www.npmjs.com/package/express-async-handler), this module provides a wrapper function.

#### Use "express-validator" to validate/sanitize form data

[express-validator](https://www.npmjs.com/package/express-validator)

#### Use gzip/deflate compression for responses

Web servers can often compress the HTTP response sent back to a client, significantly reducing the time required for the client to get and load the page.
[compression](https://www.npmjs.com/package/compression)

#### Use Helmet to protect against well known vulnerabilities

Helmet helps secure Express apps by setting HTTP response headers.
[Helmet](https://www.npmjs.com/package/helmet)

#### Production Best Practices: Security

Including above packages(e.g. Helmet).
[Production Best Practices: Security](https://expressjs.com/en/advanced/best-practice-security.html)
