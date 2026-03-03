# R33 Dashboards Public Repository

Welcome to the DETECT-RPC R33 Phase Dashboard project! This documentation guides new users through installation, setup, and development.

---

## Table of Contents

1. [Overview of the Study](#overview-of-the-study)
2. [Prerequisites](#prerequisites)
3. [Installation](#installation)
4. [Project Setup](#project-setup)
5. [Building the Dashboard](#building-the-dashboard)
6. [Development Workflow](#development-workflow)
7. [Contributing](#contributing)

---

## Overview of the Study

The primary objective of the study is to evaluate whether the use of the DETECT-RPC screening tool increases the average reporting of elder mistreatment (EM) by HBPC clinicians relative to a baseline period where they did not use the DETECT-RPC screening tool.

The R33 phase is divided into two parts:

1. Universal EM Screening (RCT)
2. Caregiver Dyad Follow-Up Interviews

### Universal EM Screening

In this part of the study (year 3-5), we will randomize approximately 43 home-based primary care clinicians to either use the adapted DETECT screening tool at every qualified home based primary care patient encounter (experimental condition) or continue to provide standard care (control condition). Providers randomized to the experimental condition will use the adapted DETECT tool at every qualified patient encounter. A waiver of informed consent is approved, as it requires no direct input from the patient; rather, it is a purely observation-based tool, which is completed by the clinician. Over the three years of follow-up, we expect our partner home-based primary care programs to treat approximately 6,150 older adults. Through the randomization process, we expect half of that number to be screened by a clinician using the adapted DETECT tool.

### Caregiver Dyad Follow-Up Interviews

In this part, we will recruit a purposive sample of 180 caregiving dyads consisting of family caregivers and their care recipients, half of which will be living with Alzheimer’s Disease or Related Dementias (ADRD). The study is recruiting dyads because we are interested in caregiver behaviors and their relationship to care recipient outcomes. The caregiving dyads will be recruited from among patients who are actively enrolled in one of our site-specific home-based primary care programs.

This repository contains the code used to create dashboards for tracking the progress of the study.

## Prerequisites

### System Requirements:

* **Operating System**: Windows, macOS, or Linux
* **Memory**: Minimum 8 GB RAM
* **Storage**: At least 10 GB free space

### Software Requirements:

* [R](https://cran.r-project.org/) (version 4.5)
* [Positron](https://positron.posit.co/) **OR** [RStudio](https://posit.co/download/rstudio-desktop/) IDE (latest version)
* [Quarto](https://quarto.org/docs/get-started/) (version 1.7.\*)
* [Git](https://git-scm.com/downloads) (latest version)

---

## Installation

Follow these steps to install necessary software:

### Step 1: Install R

* Download and install R from [CRAN](https://cran.r-project.org/)

### Step 2: Install an IDE (RStudio or Positron)

* Download and install the latest version of RStudio or Positron from [Posit](https://posit.co/)

### Step 3: Install Quarto

* Download and install Quarto from [Quarto](https://quarto.org/docs/get-started/)

### Step 4: Install Git

* Download and install the latest version from [Git](https://git-scm.com/downloads)

Verify installations by opening your terminal and checking versions:

```shell
R --version
quarto --version
git --version
```

---

## Project Setup

### Step 1: Clone the Repository

```shell
git clone https://github.com/brad-cannell/r33_dashboards.git
cd r33_dashboards
```

> [!NOTE]
> Don't clone to a cloud storage folder (Box, Dropbox, Google Drive, OneDrive, etc.). File-locking and sync conflicts can corrupt the renv library.

### Step 2: Save the Data Locally

[Instructions for saving the required data locally](https://github.com/brad-cannell/r33_dashboards/wiki/DETECT%E2%80%90RPC-Data)

### Step 3: Open in the IDE

* Open r33_dashboards in the IDE.

### Step 4: Install Project Dependencies

In the R console:

```r
install.packages('renv')
renv::restore()
```

This project uses [renv](https://rstudio.github.io/renv/articles/renv.html) to manage project package dependencies. Click the link for more details.

> [!NOTE]
> `renv::restore()` may take several minutes and requires an active internet connection.

### Step 5: Request API Keys

[Instructions for requesting API keys](https://github.com/brad-cannell/r33_dashboards/wiki/DETECT%E2%80%90RPC-Data#accessing-data-through-api)

API Keys needed:
- DETECT-RPC Tool Data
    - REDCap: https://redcap.uth.tmc.edu/index.php
    - Project: DETECT Tool
- DETECT-RPC Baseline Reporting Data
    - REDCap: https://redcap.uth.tmc.edu/index.php
    - Project: DETECT-RPC APS Reporting
- DETECT-RPC Clicks
    - Go UTHealth: https://apps.uth.edu/go/pages/welcome.xhtml
    - Title: Elder Abuse Definitions

### Step 6: Add API Keys to Keyring

```r
keyring::key_set("DETECT_TOOL_REDCAP_API_TOKEN")
keyring::key_set("DETECT_APS_REDCAP_API_TOKEN")
keyring::key_set("DETECT_TOOL_LINKS_TOKEN")
```

[Click for additional information about the keyring package](https://keyring.r-lib.org/)

---

## Building the Dashboard

This section assumes you have already successfully completed all of the installation and project setup steps above.

### Step 1: Render the Dashboard

In the IDE, navigate to the project root and run:

```shell
quarto publish gh-pages
```

- Type `Yes` when asked "? Update site at https://brad-cannell.github.io/r33_dashboards/?"
- You may need to enter your computer's password one or more times giving `keyring` permission to access the API keys.

### Step 2: View in Browser

* A rendered preview of the dashboard should automatically open in the browser.

### Step 3. Commit and Push to GitHub

```shell
git add .
git commit -m "YYYY-MM-DD Dashboard Update"
git push
```

---

## Development Workflow

### Branching

Use feature branches for development:

```shell
git checkout -b feature/your-feature-name
```

### Commit Changes

Make commits descriptive and focused:

```shell
git add .
git commit -m "Describe changes clearly"
```

### Push to Remote

Push your feature branch:

```shell
git push origin feature/your-feature-name
```

---

## Contributing

1. Fork the repository.
2. Create your feature branch.
3. Submit a Pull Request (PR) to the main repository.
4. Clearly document your changes in the PR description.

---