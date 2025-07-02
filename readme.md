# 🚀 GitHub Automation Script

This repository contains a Node.js automation script that records the current date and time in a JSON file (`data.json`), commits the update to your git repository, and pushes the commit—all with just one command!

## ✨ Features

- 🕒 Writes the current timestamp to a `data.json` file.
- 🤖 Automates git add, commit, and push using `simple-git`.
- 📅 Formats dates easily with `moment`.
- 💬 Uses the timestamp as the commit message.

## 📁 Files

- **`index.js`** – Main script for writing and committing the date.
- **`data.json`** – Stores the latest timestamp.
- **`package.json`** – Project metadata and dependencies.

## 📦 Dependencies

- [`jsonfile`](https://www.npmjs.com/package/jsonfile) – Read and write JSON files.
- [`moment`](https://www.npmjs.com/package/moment) – Format dates.
- [`simple-git`](https://www.npmjs.com/package/simple-git) – Automate git operations.

Install everything with:

```bash
npm install
```

## ▶️ Usage

Update the timestamp and push the commit:

```bash
node index.js
```

This will:
- ✍️ Write the current date and time to `data.json`
- 📝 Commit with the timestamp as the message
- 🚚 Push the commit to your repository

## 💡 Example Code

```js
import jsonfile from 'jsonfile';
import moment from 'moment';
import simpleGit from 'simple-git';

const path = "./data.json";
const date = moment().format();

const data = {
    date: date,
};

jsonfile.writeFile(path, data);

simpleGit().add([path]).commit(data,{'--date':date}).push();
```

## 🪪 License

This project is licensed under the MIT License.
