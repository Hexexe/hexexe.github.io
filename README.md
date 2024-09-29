# Useful Commands for Fedora linux

Just a list of commands that I occasionally need.

---

## Table of Contents

- [Listing Installed Package Groups](#listing-installed-package-groups)
- [Removing a Package Group](#removing-a-package-group)
- [Removing Packages Individually](#removing-packages-individually)
- [Installing Packages](#installing-packages)
- [Cleaning Up Unused Dependencies](#cleaning-up-unused-dependencies)
- [Managing Services with systemctl](#managing-services-with-systemctl)
- [General Package Management Tips](#general-package-management-tips)
- [Swapping Fedora Release Identity](#swapping-fedora-release-identity)
- [Verifying System Identity](#verifying-system-identity)
- [Reinstalling Fedora Release Package](#reinstalling-fedora-release-package)
- [Reinstalling a Desktop Environment](#reinstalling-a-desktop-environment)

---

## Listing Installed Package Groups

List all installed package groups:

```bash
sudo dnf group list --installed 
```

## Removing a Package Group

Uninstall a group of packages (e.g., desktop environments, development tools):

```bash
sudo dnf groupremove "Group Name"
```


## Removing Packages Individually

Use dnf remove to uninstall specific packages.

```bash
sudo dnf remove package1 package2 package3
```

## Installing Packages

Use dnf install to add new packages to your system.

```bash
sudo dnf install package1 package2 package3
```

## Cleaning Up Unused Dependencies

Remove packages that were installed as dependencies but are no longer needed:

```bash
sudo dnf autoremove
```

## Managing Services with systemctl

Control system services:

* Enable a Service at Boot:

    ```bash
    sudo systemctl enable service-name
    ```
* Disable a Service at Boot:
    ```bash
    sudo systemctl disable service-name
    ```
* Start a Service Immediately:
    ```bash
    sudo systemctl start service-name
    ```
* Stop a Running Service:
    ```bash
    sudo systemctl stop service-name
    ```
* Check Service Status:
    ```bash
    systemctl status service-name
    ```


## General Package Management Tips


* List Installed Packages:

    ```bash
    sudo dnf list installed
    ```
* Search for Packages:
    ```bash
    sudo dnf search keyword
    ```
* Get Package Information:
    ```bash
    sudo dnf info package-name
    ```
* Update All Packages:
    ```bash
    sudo dnf update
    ```
* Clean Cached Data:
    ```bash
    sudo dnf clean all
    ```

## Swapping Fedora Release Identity

Change your system's identity from one Fedora edition or spin to another:

``` bash
sudo dnf swap fedora-release-identity-current fedora-release-identity-target
```
* Replace fedora-release-identity-current with your current release identity package (e.g., fedora-release-identity-workstation).
* Replace fedora-release-identity-target with the desired identity package (e.g., fedora-release-identity-kde, fedora-release-identity-xfce).

## Verifying System Identity

Check your system's release information:

``` bash
cat /etc/fedora-release
```
View detailed operating system identification data:

```bash
cat /etc/os-release
```

## Reinstalling Fedora Release Package

Ensure system identity files are correctly set up:

``` bash
sudo dnf reinstall fedora-release-edition
```
* Replace fedora-release-edition with the appropriate package for your edition or spin (e.g., fedora-release-kde, fedora-release-mate).

## Reinstalling a Desktop Environment

If components of a desktop environment are missing or you need to reinstall them:

``` bash
sudo dnf groupinstall "Desktop Environment Name"
```
* Replace "Desktop Environment Name" with the name of the desktop environment group (e.g., "KDE Plasma Workspaces", "Xfce Desktop", "MATE Desktop").