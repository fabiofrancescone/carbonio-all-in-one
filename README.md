#  Carbonio All-in-One Meta Package

The **Carbonio All-in-One** repository provides a lightweight Debian meta-package designed to install the complete **Zextras Carbonio Community Edition (CE)** stack on an Ubuntu server with a single command.

---

##  Overview

The `carbonio-bundle` package simplifies the installation process of Carbonio CE by automatically pulling and installing all required components and dependencies from the configured APT repositories.


---

##  IMPORTANT PREREQUISITE

> **Before installing this package, PostgreSQL 16 must be installed on the server.**  
> Make sure that the PostgreSQL repository is correctly configured, then install it with:
> ```bash
> sudo apt install postgresql-16
> ```

---

##  Building the Package

You can build the meta-package locally with standard Debian packaging tools.

###  Clone the repository
git clone https://github.com/<your-org>/carbonio-all-in-one.git
cd carbonio-all-in-one

dpkg-deb --build carbonio-bundle

This will create a .deb file in the current directory:
carbonio-bundle.deb

sudo apt update
sudo apt install ./carbonio-bundle.deb

---

##  Unistallation

sudo apt remove carbonio-bundle

To completely remove all Carbonio packages:

sudo apt purge carbonio-*

---

## Repository Structure

carbonio-all-in-one/
├── carbonio-bundle/
│   └── DEBIAN/
│       └── control
└── README.md


