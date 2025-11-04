#  Carbonio All-in-One Meta Package

The **Carbonio All-in-One** repository provides a lightweight Debian meta-package designed to install the complete **Zextras Carbonio Community Edition (CE)** stack on an Ubuntu server with a single command.

##  Overview

The `carbonio-bundle` package simplifies the installation process of Carbonio CE by automatically pulling and installing all required components and dependencies from the configured APT repositories.


##  IMPORTANT PREREQUISITE


> Before installing this package, make sure the following conditions are met:
>
>    **PostgreSQL 16** must be installed on the server.  
>    Ensure that the PostgreSQL repository is correctly configured, then install it with:
>    ```bash
>    sudo apt install postgresql-16
>    ```
>
>    The **Carbonio repository** must be added to your APT sources list, along with its **corresponding GPG key**.  
>    Make sure that repository configuration and key import are completed successfully before proceeding with the installation.


##  Building the Package

You can build the meta-package locally with standard Debian packaging tools.

###  Clone the repository
```bash
git clone https://github.com/<your-org>/carbonio-all-in-one.git
cd carbonio-all-in-one
```

###  Build the package
```bash
dpkg-deb --build carbonio-bundle
```

This will create a .deb file in the current directory:
carbonio-bundle.deb

```bash
sudo apt update
sudo apt install ./carbonio-bundle.deb
```

##  Unistallation

```bash
sudo apt remove carbonio-bundle
```

To completely remove all Carbonio packages:

```bash
sudo apt purge carbonio-*
```
|       └── postinst
│       └── control
└── README.md
```
