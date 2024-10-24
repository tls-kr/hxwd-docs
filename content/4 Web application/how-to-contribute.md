---
title: How to contribute to the documentation
---

# How to contribute to the documentation

## Setting up git and GitHub

The documentation is maintained separately from the other parts of the HXWD website.   Instead of your HXWD account, you will need [a GitHub account](https://github.com/join) to contribute to the HXWD Documentation.
If you are comfortable working with git and GitHub, you can skip ahead to [Contributing to the HXWD Docs](#contributing-to-hxwd).
If you've created a new GitHub account and want to know what to do next, you can choose one of the following ways to contribute changes:

- [GitHub UI](https://docs.github.com/en/repositories/working-with-files/managing-files) -
  This is the easiest way to contribute **small changes** described in [Simple changes](#simple-changes).
- [GitHub Desktop](https://docs.github.com/en/get-started/using-github/github-desktop) - A desktop app for managing interaction with GitHub.
- [GitHub CLI](https://docs.github.com/en/github-cli/github-cli/about-github-cli) - A command-line wrapper for interacting with GitHub.
- [`git`](https://git-scm.com/downloads) - You can use `git` from the command line to interact with GitHub.
  The examples in this document assume you are using this method.
  The [`git` cheat sheet](https://training.github.com/) and [Using Git](https://docs.github.com/en/get-started) guide are useful resources for beginners and advanced users.
## Contributing to the HXWD Docs

### Simple changes

If you want to make a small change like fixing a typo, the GitHub UI is the easiest way to get started.
If you've found a typo on the page [The results of a full text search](Search%20results.md), for example, you can propose a fix as follows:

1. Sign in to [GitHub](https://github.com/)
2. Navigate to [https://github.com/tls-kr/tls-kr.github.io](https://github.com/tls-kr/tls-kr.github.io)
3. Find the source file, in this case `en/manual/search-results.md`
4. Click the edit (pencil) button

From there, the GitHub UI will walk you through the rest by creating a [fork](https://docs.github.com/en/get-started/quickstart/fork-a-repo) and a branch to commit your changes to.
After you have made changes to your branch, open a [pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) with your changes to be incorporated.

A pull request represents the work you want to be reviewed, approved, and merged into the `main` branch of the HXWD repository.
See the [Creating a pull request](#creating-a-pull-request) for more details on creating and handling pull requests successfully.

If you're not certain of the changes that you want to make, [get in touch with us](https://github.com/tls-kr/tls-kr.github.io/issues) by reporting the problem here!

> [!NOTE]
> You can click the 🌟**Edit This Page** link at the top of an HXWD page to jump directly to the page source on GitHub. 

A pull request represents the work you want to be reviewed, approved, and merged into the `main` branch of the HXWD repository.
See the [Creating a pull request](#creating-a-pull-request) for more details on creating and handling pull requests successfully.

### More elaborate changes

If you would like to more thoroughly contribute, the recommended way is as follows:
1. *Fork* the repository at [HXWD Docs](https://github.com/tls-kr/hxwd-docs) using the "Fork" button in the upper left area of the page to your own GitHub account.
2. *Clone* the forked repository to your own computer or device where you would like to do the editing.
3. Use the application [Obsidian](https://obsidian.md) to open the folder `hxwd-docs/content` as a "Vault". 
4. You have now the complete copy of the documentation on your own computer, ready to be edited and improved to your hearts content. 
5. (Optional, but also highly recommended) - you can preview how your changes would look on the published site locally on your computer. To do this, you need **at least [Node](https://nodejs.org/)** **v20** and `npm` v9.3.1. In most cases, using a tool called `nvm` is the best way to install these, here is a [step by step tutorial](https://dev.to/sanzhanov/node-version-manager-nvm-how-to-install-and-use-step-by-step-guide-k4a) that works on many platforms. 
	- With `npm` in place, you can simply run
	   ```
	   npx quartz build --serve
       ```
	    in the folder `hxwd-docs` and you can then access the local website [here](http://localhost:8080)
	 
	- An additional advantage of this method is that you can easily sync your changes back to the GitHub repository with
	   ```
	   npx quartz sync
	   ```
	   once you are satisfied with your changes.
6. If you do not install `npx`, you will not be able to locally preview your changes, and you will have to manually *push* then back to your GitHub repository.
7. Once you are satisfied with the changes, you can open a *pull request* (PR) and the maintainers will add your contributions to the published version. 