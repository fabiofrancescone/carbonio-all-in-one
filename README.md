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

### Fork the repository

Before cloning, **create your own fork** of the official GitHub repository to ensure you can manage updates, make changes, or contribute back if needed.

1. Go to the official repository page on GitHub.  
2. Click **“Fork”** to create your personal copy under your own account or organization.  
3. Then, clone **your forked repository** on the server:

```bash
git clone https://github.com/<your-username>/carbonio-all-in-one.git
cd carbonio-all-in-one
```

###  Build the package
```bash
dpkg-deb --build carbonio-bundle
```

This will create a .deb file in the current directory:
carbonio-bundle.deb

```bash
apt update
```

##  Install Carbonio

```bash
apt install ./carbonio-bundle.deb
```

## Default Domain Configuration

During installation, **Carbonio will automatically set the default domain** based on the server’s **fully qualified domain name (FQDN)**.

For example:  
If your server hostname is:
```bash
srv-01.example.com
```
then the default Carbonio domain will be automatically configured as:
```bash
example.com
```


##  Unistallation

```bash
apt remove carbonio-bundle
```

To completely remove all Carbonio packages:

```bash
apt purge carbonio-*
```
