# Lepton

[![Build Status](https://travis-ci.org/hackjutsu/Lepton.svg?branch=master)](https://travis-ci.org/hackjutsu/Lepton)
[![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg?style=flat)](http://standardjs.com/)
[![Dependency Status](https://david-dm.org/hackjutsu/Lepton.svg?style=flat-square)](https://david-dm.org/hackjutsu/Lepton)
[![MIT Licensed](https://img.shields.io/badge/License-MIT-blue.svg?style=flat)](https://opensource.org/licenses/MIT)


**Lepton** is a lean snippet manager based on *GitHub Gist*. [Check out its latest release.](https://github.com/hackjutsu/Lepton/releases)
- Group snippets by languages
- Create/Edit/Delete snippets
- Search
- Custom tags
- Markdown rendering
- Immersive mode
- Proxy
- Dashboard
- GitHub Enterprise support
- Cross-platform support (macOS/Win/Linux)

![Screenshot](./docs/img/portfolio/stay_organized.png)

|      Organize         |  Markdown | Immersive Mode *(⌘/Ctrl + i)* |
| :-------------:| :-----:| :-----: |
| ![Screenshot](./docs/img/portfolio/stay_organized.png) | ![Screenshot](./docs/img/portfolio/markdown.png) | ![Screenshot](./docs/img/portfolio/immersive.png)

|      Search (*⇧ + Space*)         |    Tags    | Dashboard *(⌘/Ctrl + d)* |
| :-------------:| :-----:| :-----: |
| ![Screenshot](./docs/img/portfolio/search_bar.png) | ![Screenshot](./docs/img/portfolio/edit.png) | ![Screenshot](./docs/img/portfolio/dashboard.png)

## Shortcuts
| Function       | Shortcut       |  Note     |
| :------------: |:-------------: |:-----:|
| New Snippet    | `Cmd/Ctrl + N` | Create a snippet      |
| Edit Snippet   | `Cmd/Ctrl + E` | Edit a snippet      |
| Submit         | `Cmd/Ctrl + S` | Submit the changes from the editor      |
| Cancel         | `Cmd/Ctrl + ESC` | Exit the editor without saving   |
| Immersive Mode | `Cmd/Ctrl + I` |  Toggle the [Immersive mode](https://github.com/hackjutsu/Lepton/blob/master/docs/img/portfolio/immersive.png)    |
| Dashboard      | `Cmd/Ctrl + D` |  Toggle the [dashboard](https://github.com/hackjutsu/Lepton/blob/master/docs/img/portfolio/dashboard.png)     |
| About Page     | `Cmd/Ctrl + ,` |  Toggle the [About page](https://github.com/hackjutsu/Lepton/blob/dev/docs/img/portfolio/about.png)    |
| Search         | `Shift + Space`|  Toggle the [search bar](https://github.com/hackjutsu/Lepton/blob/master/docs/img/portfolio/search_bar.png)    |

## Tech Stack
![Based on](./docs/img/erb-logo.png)

1. Framework: [Electron](http://electron.atom.io/)
2. Bundler: [Webpack](http://webpack.github.io/docs/), [Babel](https://babeljs.io), [electron-builder](https://github.com/electron-userland/electron-builder)
3. Language: [ES6](https://babeljs.io/docs/learn-es2015/), [Sass](http://sass-lang.com/)
4. Library: [React](https://facebook.github.io/react/), [Redux](https://github.com/reactjs/redux), [Redux Thunk](https://github.com/gaearon/redux-thunk), [Redux Form](http://redux-form.com/)
5. Lint: [ESLint](http://eslint.org/)

## Installation
- Download released binaries(macOS/Windows/Linux) [here](https://github.com/hackjutsu/Lepton/releases).
- Install via Homebrew (macOS)
```bash
brew cask install lepton
```

## Development


### Install dependencies

```bash
$ git clone git@github.com:hackjutsu/Lepton.git
$ cd Lepton && npm i
```

### Client ID/Secret
[Register your application](https://github.com/settings/applications/new), and put your client id and client secret in `./configs/account.js`.
```js
module.exports = {
  client_id: <your_client_id>,
  client_secret: <your_client_secret>
}
```

### Run
```bash
$ npm run build && npm run start
```

## Build Installer App
>Read [electron-builder docs](https://github.com/electron-userland/electron-builder#readme) and check out the [code signing wiki](https://github.com/electron-userland/electron-builder#code-signing) before building the installer app.

Build apps for macOS.
```bash
$ npm run dist -- -m
```
Build apps for Windows.
```bash
$ npm run dist -- -w
```
Build apps for Linux. 

>Need a running [Docker](https://www.docker.com/) daemon to build a `snap` package.
```bash
$ npm run dist -- -l
```
Build apps for macOS, Windows and Linux.
```bash
$ npm run dist -- -wml
```
Build apps for the current OS with the current arch.
```bash
$ npm run dist
```

## Configurations
Lepton can be configured by `<home_dir>/.leptonrc` in the these fields. (Create the file if it does not exist.)

- Snippet
- Editor
- Logger
- Proxy
- Enterprise

Check out the [.leptonrc template](https://gist.github.com/1ad7e4968eb64d881ec9dedd6c0f400b) to explore their options.

## Shortcuts
| Function       | Shortcut       |  Note     |
| :------------: |:-------------: |:-----:|
| New Snippet    | `Cmd/Ctrl + N` | Create a snippet      |
| Edit Snippet   | `Cmd/Ctrl + E` | Edit a snippet      |
| Submit         | `Cmd/Ctrl + S` | Submit the changes from the editor      |
| Cancel         | `Cmd/Ctrl + ESC` | Exit the editor without saving   |
| Immersive Mode | `Cmd/Ctrl + I` |  Toggle the [Immersive mode](https://github.com/hackjutsu/Lepton/blob/master/docs/img/portfolio/immersive.png)    |
| Dashboard      | `Cmd/Ctrl + D` |  Toggle the [dashboard](https://github.com/hackjutsu/Lepton/blob/master/docs/img/portfolio/dashboard.png)     |
| About Page     | `Cmd/Ctrl + ,` |  Toggle the [About page](https://github.com/hackjutsu/Lepton/blob/dev/docs/img/portfolio/about.png)    |
| Search         | `Shift + Space`|  Toggle the [search bar](https://github.com/hackjutsu/Lepton/blob/master/docs/img/portfolio/search_bar.png)    |

## FAQ
#### My snippet's language is classified as "Other"
Lepton depends on GitHub API to detect the language. If it fails, the snippet's language is marked as "Other". However, we can put `// vim: syntax=<your_language>` at the top to explicitly specify the language.
```
// vim: syntax=javascript
let test = 'This is a javascript file'
```

#### Search
Limited by GitHub API, Lepton supports searching for following fields.
- file name
- description
- tag
- gist id

#### Title and Tags
```
[title] description #tag1 #tag2
```

#### Donation
*We DON'T accept donation personally.* If you like, feel free to donate to [Wikimedia Foundation](https://wikimediafoundation.org/wiki/Ways_to_Give), which helps sustain free knowledge through Wikipedia and its sister projects for people around the world. You are welcome to create an issue to share how much you have contributed.

## Contributors
<table id="contributors">
   <tr>
      <td><img src=https://avatars1.githubusercontent.com/u/7756581?v=3><a href="https://github.com/hackjutsu">hackjutsu</a></td>
      <td><img src=https://avatars1.githubusercontent.com/u/5550402?v=3><a href="https://github.com/wujysh">wujysh</a></td>
      <td><img src=https://avatars2.githubusercontent.com/u/14959483?v=3><a href="https://github.com/DNLHC">DNLHC</a></td>
      <td><img src=https://avatars2.githubusercontent.com/u/13786673?v=3><a href="https://github.com/meilinz">meilinz</a></td>
      <td><img src=https://avatars3.githubusercontent.com/u/5697293?v=3><a href="https://github.com/lcgforever">lcgforever</a></td>
      <td><img src=https://avatars1.githubusercontent.com/u/180032?v=3><a href="https://github.com/Calinou">Calinou</a></td>
      <td><img src=https://avatars0.githubusercontent.com/u/7173984?v=3><a href="https://github.com/rogersachan">rogersachan</a></td>      
   </tr>
   <tr>
      <td><img src=https://avatars3.githubusercontent.com/u/2075566?v=3><a href="https://github.com/passerbyid">passerbyid</a></td>
      <td><img src=https://avatars2.githubusercontent.com/u/12994810?v=3><a href="https://github.com/YYSU">YYSU</a></td>
      <td><img src=https://avatars3.githubusercontent.com/u/26782336?v=3><a href="https://github.com/cixuuz">cixuuz</a></td>
      <td><img src=https://avatars2.githubusercontent.com/u/4332224?v=3><a href="https://github.com/Gisonrg">Gisonrg</a></td>
      <td><img src=https://avatars2.githubusercontent.com/u/7821318?v=3><a href="https://github.com/ArLEquiN64">ArLEquiN64</a></td>
      <td><img src=https://avatars1.githubusercontent.com/u/1841272?v=3><a href="https://github.com/popey">popey</a></td>
      <td><img src=https://avatars3.githubusercontent.com/u/6280136?s=400&v=3><a href="https://github.com/yihan-us">yihan-us</a></td>
   </tr>
</table>

## License
MIT © [hackjutsu](https://github.com/hackjutsu)
