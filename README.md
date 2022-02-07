# Starter guide for new projects

This is a starter guide that will work for most projects built with javascript, however, some of the methods and technologies used in this guide could apply to any project regardless of the language they are based on. It is possible that the needs are very specific for some projects, in these cases the most optimal thing is to follow the standards that will be mentioned in this guide and apply the necessary solutions.

## Requirements

The following technologies will be necessary for the configuration of a new project:

- ESLint
- Prettier
- CommitLint
- Husky
- Lint Staged

## Configuration

The first thing to do in a new project is to initialize the repository and the project with npm or yarn

### Initialize the repository

```bash
git init
echo "# README" >> README.md
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin <Origin>
git push -u origin main
```

### Add License

`nano LICENSE`

```
MIT License

Copyright (c) <YEAR> <FULL NAME>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

### Configure `.github` Folder

Folder structure

```
.github/
  |
  |--workflows/
  |  |
  |  |--actions.yml
  |
  |--release-drafter.yml
```

### Initialize the project

#### With NPM

```
npm init
```

#### With Yarn

```
yarn init
```
