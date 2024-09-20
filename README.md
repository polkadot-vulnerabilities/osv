# Polkadot Open Source Vulnerabilities

## Contributing to the Open Source Vulnerability Repository

Thank you for your interest in contributing to this open-source vulnerability repository! To ensure
consistency, accuracy, and ease of use, we’ve outlined the following guidelines and instructions.
Please read through them carefully before making any contributions.

## Table of Contents
- [How to Contribute](#how-to-contribute)
- [Repository Structure](#repository-structure)
- [File Naming Conventions](#file-naming-conventions)
- [JSON Content Format](#json-content-format)
- [Submitting a Pull Request](#submitting-a-pull-request)
- [Code of Conduct](#code-of-conduct)
- [License](#license)

## How to Contribute

### Step 1: Fork the Repository
Fork this repository to your GitHub account by clicking the "Fork" button at the top of this page.

### Step 2: Clone the Fork
Once the repository is forked, clone it to your local machine:
```bash
git clone https://github.com/YOUR-USERNAME/OSV-vulnerability-repository.git
cd OSV-vulnerability-repository
```

### Step 3: Create a New Branch
Create a new branch to work on:
```bash
git checkout -b your-feature-branch
```

### Step 4: Make Edits or Add New Files
Create a new JSON files following the [naming conventions](#file-naming-conventions) and [content format](#json-content-format) guidelines.

### Step 5: Commit Changes
Once you’ve made the changes, commit them to your branch:
```bash
git add .
git commit -m "Descriptive message about the changes"
```

### Step 6: Push to Your Fork
Push your changes to your forked repository:
```bash
git push origin your-feature-branch
```

### Step 7: Submit a Pull Request
Submit a pull request (PR) to the main repository with a detailed description of your changes.

---

## Repository Structure

The repository follows a simple structure with each vulnerability documented in its own JSON file under a folder named after the year of discovery:

```
/2024
    POLKA-20240108-SRL-373.json
    POLKA-20231218-SRL-367.json
/2023
    POLKA-20230706-SRL-316.json
    POLKA-20231130-SRL-364.json
/2022
        ...
/README.md
```

- **202\*/**: Each vulnerability is stored in a year-specific folder and is identified with a unique identifier in the file name.
- **README.md**: Contains an overview of the repository.

---

## File Naming Conventions

Each JSON file representing a vulnerability must follow the naming convention below:

```
POLKA-YYYYMMDD-ZZZ-XXX.json
```

Where:
- **POLKA**: Prefix indicating this is a Polkadot/Substrate-related vulnerability.
- **YYYYMMDD**: The date of discovery or reporting in the format year, month, and day.
- **ZZZ**: Short reference to the organization reporting the vulnerability (for example, Parity, SRLabs).
- **XXX**: Unique identifier number for the vulnerability.

### Example:
```
POLKA-20240101-PARITY-1.json
```

---

## JSON Content Format

Each vulnerability JSON file must follow the Open Source Vulnerability (OSV) schema. Below is a breakdown of the expected fields and structure:

### JSON Structure:

```json
{
  "schema_version": "1.6.3",
  "id": "POLKA-YYYYMMDD-ZZZ-XXX",
  "modified": "YYYY-MM-DDT12:00:00Z",
  "published": "YYYY-MM-DDT12:00:00Z",
  "related": [],
  "summary": "Short description of the vulnerability.",
  "details": "Full description of the vulnerability and its impact.",
  "affected": [
    {
      "package": {
        "ecosystem": "Polkadot",
        "name": "PACKAGE-NAME"
      },
      "severity": [
        {
          "type": "CVSS_V4",
          "score": "X.X"
        }
      ],
      "ranges": [
        {
          "type": "SEMVER",
          "events": [
            {
              "introduced": "VERSION"
            },
            {
              "fixed": "VERSION"
            }
          ]
        }
      ],
      "versions": [
        "VERSION"
      ]
    }
  ],
  "references": [
    {
      "type": "FIX",
      "url": "LINK-TO-PATCH"
    },
    {
      "type": "DISCUSSION",
      "url": "LINK-TO-DISCUSSION"
    }
  ],
  "credits": [
    {
      "name": "FINDER-NAME",
      "contact": [],
      "type": "FINDER"
    }
  ],
  "database_specific": {
    "title": "Descriptive title of the vulnerability",
    "affected_system": "The affected system (e.g., FRAME, XCM, etc.)",
    "type": "Vulnerability type (e.g., DoS, Double Spending)",
    "discovery_method": "Code Review/Analysis",
    "discovery_date": "YYYY-MM-DDT12:00:00Z",
    "public": false
  }
}
```

### Fields Explanation:
- **schema_version**: Version of the OSV schema used.
- **id**: The unique identifier of the vulnerability.
- **modified/published**: The date the vulnerability was modified/published in the format `YYYY-MM-DDT12:00:00Z`.
- **summary**: A brief summary of the vulnerability.
- **details**: Full details of the vulnerability, including context and impact.
- **affected**: List of affected packages, severity scores, and the versions affected.
- **references**: URLs linking to fixes, discussions, or documentation.
- **credits**: List of individuals or teams responsible for discovering and reporting the vulnerability.
- **database_specific**: Metadata specific to the vulnerability, including the title, system, and vulnerability type.

---

## Submitting a Pull Request

1. Ensure that your contribution follows the naming and format guidelines.
2. Provide a detailed description in your pull request, outlining the vulnerability or improvement made.
3. Tag any reviewers or maintainers as needed.
4. Wait for feedback or approval from the repository maintainers.

---

## Code of Conduct

All contributors are expected to abide by our [Code of Conduct](CODE_OF_CONDUCT.md), fostering a welcoming and respectful environment.

---

## License

By contributing, you agree that your contributions will be licensed under the same license as the repository: [MIT License](LICENSE).

