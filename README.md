# GitHub Key-Value Store

[![npm version](https://badge.fury.io/js/github-kv.svg)](https://badge.fury.io/js/github-kv)

GitHub as a Key Value store.

## Installation

```bash
npm install -g github-kv
```

## Caveat


When [create new Personal Access Token](https://github.com/settings/tokens/new), You should check only repo.


## Usage

### Example key-value store

please show store.json in this repo.

```json
{
    "ACCESS_KEY": "HELLO",
    "SECRET_KEY": "WORLD"
}
```

### Global CommandLine Interface

in Terminal. extract is optional

```bash
# gh-kv --token <GitHub Token> --owner <Owner or Organization> --repo <REPO_NAME> --file <TARGET_FILENAME> --extract <OUTPUT_FILENAME>
gh-kv --token <GitHub Token> --owner changjoo-park --repo kv --file store.json --extract key.json
```

### Module in Node.js

extract is optional same as global CLI

```js
const getGitHubStore = require('github-kv')

// Promise
getGitHubStore({ token, owner, repo, file, extract })
    .then(store => {})
    .catch(error => {})

// async - await
const store = await getGitHubStore({ token, owner, repo, file, extract })
```