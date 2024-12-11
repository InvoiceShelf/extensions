# Extensions Repository for InvoiceShelf

Welcome to the official Extensions Repository for **InvoiceShelf**. This repository serves as a central hub for creating, managing, and submitting extensions to enhance the functionality of InvoiceShelf.

## 📖 Table of Contents
- [Introduction](#introduction)
- [Getting Started](#getting-started)
  - [Requirements](#requirements)
  - [Repository Structure](#repository-structure)
- [Creating an Extension](#creating-an-extension)
  - [Metadata File](#metadata-file)
  - [Code Structure](#code-structure)
- [Submitting an Extension](#submitting-an-extension)
- [Versioning and Updates](#versioning-and-updates)
- [Extension Guidelines](#extension-guidelines)
- [Support](#support)

---

## 🧩 Introduction
Extensions are modular pieces of functionality that you can add to your InvoiceShelf installation. This repository contains the guidelines, tools, and best practices for creating and submitting extensions.

---

## 🚀 Getting Started

### Requirements
To develop an extension, you need the following:
- Basic knowledge of InvoiceShelf's API or extension architecture.
- GitHub, GitLab, or other Git hosting platforms for managing your extension.

### Repository Structure
Your extension repository should follow this structure:

> TBD


---

## ✍️ Creating an Extension

### Metadata File
The `extension.json` file is a mandatory file that provides metadata about your extension. Below is a sample:

```json
{
  "name": "Example Extension",
  "description": "Adds example functionality to [Your Project Name].",
  "version": "1.0.0",
  "author": "John Doe",
  "license": "MIT",
  "tags": ["example", "utility"],
  "compatibility": {
    "min_version": "1.0.0",
    "max_version": "2.0.0"
  },
  "repository": "https://github.com/username/example-extension",
  "download_url": "https://github.com/username/example-extension/archive/refs/tags/v1.0.0.zip"
}
```

***Metadata Fields***

- name: A unique name for your extension.
- description: A brief description of what your extension does.
- version: The current version of your extension, using Semantic Versioning.
- author: The name of the developer(s) or organization.
- license: The license under which your extension is distributed.
- tags: Keywords to help categorize your extension.
- compatibility: Specifies the minimum and maximum versions of [Your Project Name] your extension supports.
- repository: URL of your extension's Git repository.
- download_url: Direct link to the downloadable package (ZIP file).

***Code Structure***

Write your extension's functionality in the src/ directory. Follow coding standards for [Your Project Name]. Include documentation in README.md and tests in the tests/ folder (if applicable).
📝 Submitting an Extension

To submit your extension to the marketplace:

- Create a public repository on GitHub, GitLab, or similar.
- Add a README.md and LICENSE file.
- Create a PR in order to add your extension in the list

Once submitted, your extension will be reviewed for inclusion in the marketplace.

🔄 Versioning and Updates

- Tag releases in your repository using Git tags.
- Update the version field in extension.json for each release.
- Ensure the download_url points to the latest release package.

📜 Extension Guidelines

To maintain quality, all extensions must adhere to the following:

- Follow the InvoiceShelf Coding Standards.
- Ensure backward compatibility as per the compatibility field.
- Avoid malicious or unethical behavior in your code.

💬 Support

If you encounter any issues or have questions, reach out to:

- InvoiceShelf Discord
- Github Issues

We look forward to seeing your amazing extensions!
