# publiccode-issueopener

[![License](https://img.shields.io/github/license/italia/publiccode-issueopener.svg)](https://github.com/italia/publiccode-issueopener/blob/main/LICENSE)

<p align="center">
  English | 
  <a href="README.it.md">Italiano</a>
</p>

publiccode-issueopener is a Python-based automation bot designed to ensure the correctness
of `publiccode.yml` files in GitHub repositories.

This bot gets the list of repositories in a software catalog
through its [open-catalog-api](https://github.com/publiccodeyml/open-catalog-api) instance,
checks the validity of the `publiccode.yml` file for errors, logs them, and opens GitHub issues
accordingly.

This aids in maintaining the high quality of software catalog metadata, and eventually
ensures smooth public code sharing and reuse across different administrations.

## 🚀 Features

- **Automated issue generation:** Any detected errors in the `publiccode.yml` file
automatically trigger the creation of GitHub issues.
- **publiccode.yml compliance:** Ensures publiccode.yml files adhere to the Standard set
by the publiccode.yml schema.

## Screenshot

`publiccode-issueopener` will open issues looking like this:

![image](./images/screenshot.png)


## 💻 Getting Started

### Prerequisites

- Python 3.10 or higher

Install the required Python libraries using pip:

```bash
pip install -r requirements.txt
```

### Installation

Clone the repository to your local machine.

```bash
git clone https://github.com/italia/publiccode-issueopener
cd publiccode-issueopener
```

## 🎮 Usage

You can run the script with the following command:

```bash
./publiccode-issueopener.py [--since NUMBER_OF_DAYS]

```

The `--since` option defines the number of past days to analyze in the logs.
By default, the script checks the past day's logs for any publiccode.yml errors.

### Environment Variables

To use the bot, you'll need to set some environment variables in your system:

- `BOT_GITHUB_TOKEN`: (**required**) The GitHub token for the bot, used to authenticate when opening issues in repositories
- `GITHUB_USERNAME`: The username of the GitHub bot that will open the issues. Default is `publiccode-validator-bot`
- `API_BASEURL`: The base URL for the API used to retreive the errors in publiccode.yml files. Default is `https://api.developers.italia.it/v1`

## Opting out

Repository maintainers can stop the bot from opening or updating issues
on their repo by adding the `publiccode-issueopener: disabled` label to
any issue authored by the bot. As long as that label exists on at least
one bot-authored issue (open or closed), the repo is skipped on every
run.

To re-enable, remove the label.

## 🤝 Contributing

We always welcome contributions! Feel free to open issues, fork the repository or submit a Pull Request.

## 🔗 Related Projects

* [publiccode.yml Standard](https://github.com/publiccodeyml/publiccode.yml)
* [publiccode-crawler](https://github.com/italia/publiccode-crawler)
* [open-catalog-api](https://github.com/publiccodeyml/open-catalog-api)

## 📄 License

This software is released under the EUPL-1.2 license. Please see the `LICENSE` file for more details.

The version control system provides attribution for specific lines of code.
