---
title: 'How to Install Software on Windows'
date: 2025-04-12T16:40:17+01:00
draft: true
description: 'Installing software on a Windows operating system can be accomplished through various methods, each with its own advantages and limitations. In this guide, we will explore four popular methods: Ninite, Chocolatey, Winget, Microsoft Store, and Manual installation. Follow along to discover how to install, upgrade, and uninstall software using each approach.'
noindex: false
featured: true
pinned: true
# comments: false
series:
  - Automation
categories:
  - Tech
tags:
  - Windows
  - Desktop
images:
  - https://storage.googleapis.com/webdesignledger.pub.network/WDL/6f050e39-windows_10_logoblue.svg-copy_windows.jpg?width=1280&height=620
authors:
  - ahmedaidev
# menu:
#   main:
#     weight: 100
#     params:
#       icon:
#         vendor: bs
#         name: book
#         color: '#e24d0e'
---

## Table of Contents

- [Introduction](#introduction)
- [Ninite](#ninite)
- [Chocolatey](#chocolatey)
  - [Chocolatey: Setup](#chocolatey-setup)
  - [Chocolatey: Install Apps](#chocolatey-install-apps)
  - [Chocolatey: Install Multiple Apps](#chocolatey-install-multiple-apps)
- [Winget](#winget)
  - [Winget: Setup](#winget-setup)
  - [Winget: Install Apps](#winget-install-apps)
- [Microsoft Store](#microsoft-store)
  - [MS Store: Install Apps](#ms-store-install-apps)
  - [MS Store: Auto Update Apps](#ms-store-auto-update-apps)
  - [MS Store: Uninstall Apps](#ms-store-uninstall-apps)
- [Manual Installation](#manual-installation)
  - [Manual: Download Software](#manual-download-software)
  - [Manual: Uninstall Software](#manual-uninstall-software)
- [Conclusion](#conclusion)

## Ninite

You can install most of the popular apps using this GUI tool by going to Ninite [website](https://ninite.com/) then Check your desired apps

1. Choose your desired apps

![Ninite](/images/blog/how-to-install-software-on-windows/apps.png#center)

2. Click on **Get Your Ninite** button to download the installer

![Ninite](/images/blog/how-to-install-software-on-windows/button.png#center)

3. Last double click on the installer to start the process

![Ninite](/images/blog/how-to-install-software-on-windows/installer.png#center)

---

## Chocolatey

Chocolatey is a package manager for Windows that simplifies software installation.To get started, follow these steps:

### Chocolatey: Setup

1. Open Powershell terminal as Administrator

2. Right click on windows start menu > then choose **Terminal (Admin)**

![Terminal](/images/blog/how-to-install-software-on-windows/terminal.png#center)

3. Copy & Paste the following command to install Chocolatey on your system

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

### Chocolatey: Install Apps

> [!TIP]
> Search for apps at [packages](https://community.chocolatey.org/packages)

Execute commands into Powershell terminal

```powershell
# Command usage
choco search|install|upgrade|uninstall <package-name>

# Search for a package
choco search firefox

# Example install
choco install firefox

# Use -y flag to paypass prompt
choco install -y firefox

# Display all options and flags
choco -?
```

### Chocolatey: Install Multiple Apps

> [!TIP]
> You can list all your desired apps inside a `packages.config` file in XML format

1. Open Downloads folder and create a new file named `packages.config`
2. Copy and paste the following and change as you like

```xml
<?xml version="1.0" encoding="utf-8"?>
<packages>
  <package id="7zip" />
  <package id="firefox" />
</packages>
```

3. Then execute this command

```powershell
choco install -y C:\Users\$env:UserName\Downloads\packages.config
```

---

## Winget

Winget is Microsoft's official package manager for Windows. It provides a straightforward way to manage software installations:

### Winget: Setup

> [!NOTE]
> Winget is pre-installed on Windows 10. If not, you can try add it in your path<br />
> Settings > System > About > Advanced System Settings > Environment Variables > System Variables > Path > Add > Replace `C:\Users\<USERNAME>\AppData\Local\Microsoft\WindowsApps`<br />
> Make sure to Replace `<USERNAME>` with your system username

### Winget: Install Apps

> [!TIP]
> Search for apps at the [Official Winget Website](https://winget.run/)

You can also add multiple apps and winget will create a PowerShell file to copy and run directly on your system

![Winget](./winget.png)

Execute commands into Powershell terminal

```powershell
# Command usage
winget install|upgrade|uninstall --id <package_name>

# Search for a package
winget search vlc

# Install package by ID
winget install -e --id VideoLAN.VLC

# Display all options and flags
winget -?
```

---

## Microsoft Store

The Microsoft Store is a user-friendly platform for discovering and installing applications.

### MS Store: Install Apps

> [!Tip]
> Make sure to login with your Microsoft account to save your apps library

1. Open Microsoft Store
2. Choose your desired app
3. Click on **Get**

### MS Store: Auto Update Apps

Click on your profile icon in the Top Right > Click on Settings > Check the Auto-Update Switch

![store-settings](/images/blog/how-to-install-software-on-windows/store-settings.png#center)

### MS Store: Uninstall Apps

Open Settings > Apps > Installed Apps > Click on 3 dots icon for the desired app > Uninstall

![settings](/images/blog/how-to-install-software-on-windows/settings.png#center)

---

## Manual Installation

For software not available through package managers or the Microsoft Store, manual installation is the go-to method. Here's how:

### Manual: Download Software

Visit the official website, locate the download section, and download the installer.

For Example To install DavinCi Resolve Video Editor go to the [Website](https://www.blackmagicdesign.com/products/davinciresolve) and click on **Free Download Now**

Run the downloaded installer and follow the on-screen instructions.

## Conclusion

Installing, upgrading, and uninstalling software on Windows offers various approaches. Whether you prefer the convenience of package managers like Chocolatey and Winget, the user-friendly Microsoft Store, or the manual method for unique software, Windows provides flexibility to meet your needs. Choose the method that suits you best, and streamline your software management experience on the Windows operating system.
