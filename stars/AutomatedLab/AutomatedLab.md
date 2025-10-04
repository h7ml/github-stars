---
project: AutomatedLab
stars: 2126
description: AutomatedLab is a provisioning solution and framework that lets you deploy complex labs on HyperV and Azure with simple PowerShell scripts. It supports all Windows operating systems from 2008 R2 to 2022, some Linux distributions and various products like AD, Exchange, PKI, IIS, etc.
url: https://github.com/AutomatedLab/AutomatedLab
---

AutomatedLab
============

Build

Status

Last Commit

Latest Release

Develop

Master

Project Summary
---------------

AutomatedLab (AL) enables you to setup test and lab environments on Hyper-v or Azure with multiple products or just a single VM in a very short time. There are only two requirements you need to make sure: You need the DVD ISO images and a Hyper-V host or an Azure subscription.

Sponsors
--------

Huge thanks to our regular sponsor @chocolatey! In case you have lived under a rock (or worked mainly on non-Windows systems) for the past decade, Chocolatey is a brilliant package management system with a public binary package gallery as well as self-hosted options complete with enterprise-grade support. Give it a try with a local lab environment - it could not be easier 😊 Start with a Domain Controller and a Certificate Authority to validate not only package distribution, but also digital signatures. Our samples such as the NuGet server or Azure DevOps all include galleries that Chocolatey can use for publishing and downloading packages.

### Requirements

Apart from the module itself your system needs to meet the following requirements:

-   Windows Management Framework 5+ (Windows)
-   .NET 4.7.1 (Windows PowerShell) or .NET Core 2.x (PowerShell 6+)
-   OS
    -   Windows Server 2012 R2+/Windows 8.1+ (Hyper-V, Azure)
    -   Linux (Azure)
    -   macOS (Azure, best-effort support since neither @raandree nor @nyanhp have Apple devices)
-   Recommended OS language is en-us
-   Admin privileges are required on Windows
-   ISO files for all operating systems (Hyper-V only) and roles to be deployed (Hyper-V, Azure)
-   Intel VT-x or AMD/V capable CPU
-   A decent amount of RAM
-   Low-Latency high-throughput storage (No spinning disks please, as there are issues related to them)

#### Windows

-   Windows Management Framework 5+ or ideally PowerShell 7
-   Windows Server 2012 R2+/Windows 8.1+
-   Recommended OS language is en-us
-   Admin privileges are required

#### Linux, macOS

-   Fedora, Ubuntu, Ubuntu WSL & Azure Cloud Shell supported
-   macOS supported on best effort due to lack of Apple devices - feel free to sponsor two though :D
-   Tested on Ubuntu and Fedora. Due to fragmented nature of Linux distributions, we cannot support much else.
-   PowerShell Core 6+
-   SSH or gss-ntlmssp to enable remoting (_mandatory - no remoting, no way for AutomatedLab to do its thing_)
    -   If in doubt, try to `Install-Module PSWSMAN; Install-WSMAN` - no success warranted
-   IP and route commands available
-   **Azure subscription**
    -   At the moment, AutomatedLab only works using Azure when using Linux.
    -   KVM planned for a later date by virtue of libvirt.

### Download AutomatedLab

There are two options installing AutomatedLab:

-   You can use the MSI installer published on GitHub.
-   Or you install from the PowerShell Gallery using the cmdlet Install-Module. Please refer to the wiki for some details.

### 1\. Installation

### 2\. Getting started

### 3\. Contributing

### Version History

### Supported products

This solution supports setting up virtual machines with the following products

-   Windows 7, 2008 R2, 8 / 8.1 and 2012 / 2012 R2, 10 / 2016, 2019, 2022
-   SQL Server 2012, 2014, 2016, 2017, 2019, 2022
-   Visual Studio 2012, 2013, 2015
-   Team Foundation Services 2018, Azure DevOps Server
-   Exchange 2013, 2016, 2019
-   System Center Orchestrator 2012
-   System Center Operations Manager 2019
-   System Center Service Manager 2019
-   Microsoft Endpoint Manager Configuration Manager 1902 (and newer)
-   MDT
-   ProGet (Private PowerShell Gallery)
-   Office 2013, 2016, 2019
-   DSC Pull Server (with SQL Reporting)
-   Dynamics 365
-   Remote Desktop Services including HTML5 web client

### Feature List

-   AutomatedLab (AL) makes the setup of labs extremely easy. Setting up a lab with just a single machine is only 3 lines. And even complex labs can be defined with about 100 lines (see sample scripts).
-   Labs on Azure can be connected to each other or connected to a Hyper-V lab using a single command.
-   AL can be used to setup scenarios to demo a PowerShell Gallery using Inedo ProGet, PowerShell DSC Pull Server scenarios, ADFS or a lab with 3 Active Directory forests trusting each other.
-   Create, restore and remove snapshots of some or all lab machines with one cmdlet (Checkpoint-LabVM, Restore-LabVMSnapshot, Remove-LabVMSnapshot).
-   Install Windows Features on one, some or all lab machines with one line of code (Install-LabWindowsFeature).
-   Install software to a bunch of lab machines with just one cmdlet (Install-LabSoftwarePackages). You only need to know the argument to make the MSI or EXE go into silent installation mode. This can also work in parallel thanks to PowerShell workflows.
-   Run any custom activity (Script or ScriptBlock) on a number of lab machines (Invoke-LabCommand). You do not have to care about credentials or double-hop authentication issues as CredSsp is always enabled and can be used with the UseCredSsp switch.
-   Creating a virtual environment that is connected to the internet was never easier. The only requirements are defining an external facing virtual switch and a machine with two network cards that acts as the router. AL takes care about all the configuration details like setting the gateway on all machines and also the DNS settings (see introduction script 05 Single domain-joined server (internet facing).ps1).
-   AL offers offline patching with a single command. As all machines a based on one disk per OS, it is much more efficient to patch the ISO files that are used to create the base images (Update-LabIsoImage). See script 11 ISO Offline Patching.ps1 for more details.
-   If a lab is no longer required, one command is enough to remove everything to be ready to start from scratch (Remove-Lab)

### Local build

While we frequently release prereleases to the PowerShell Gallery, you might be interested to build the entire module locally yourself.

While the steps remain the same, the prerequisites are slightly different on Windows and Linux

Windows:

-   WiX 3 targets installed properly (!)
-   .NET SDKs 4.6.2 and 6.0 Linux:
-   .NET 6.0

After the prerequisites are satisfied, you can:

-   `./.build/01-prerequisites.ps1`
-   `./.build/02-build.ps1`
-   `./.build/03-validate.ps1` - Optionally validate the built module

The fourth step, publishing, relies on AppVeyor. The built module will be stores in `./publish`, the installer can be found in \`./Install/bin
