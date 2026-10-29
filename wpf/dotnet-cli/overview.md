---
layout: post
title: Syncfusion .NET CLI Overview for WPF | Syncfusion®
description: Learn to install and use the Syncfusion® .NET CLI (sf) to create WPF apps, manage Syncfusion WPF NuGet packages, and register licenses from the command line.
platform: wpf
control: Syncfusion<sup>®</sup> .NET CLI
documentation: ug
---

# Overview of the Syncfusion<sup>®</sup> .NET CLI for WPF

The Syncfusion<sup style="font-size:70%">&reg;</sup> .NET CLI (`sf`) is a cross-platform command line tool that creates WPF projects, manages Syncfusion<sup style="font-size:70%">&reg;</sup> WPF NuGet packages, and registers licenses from a terminal. After you install the CLI, you can run `sf` with no arguments to open an interactive menu, or run a direct command such as `sf new wpf` for scripted, prompt-free creation.

N> The Syncfusion<sup style="font-size:70%">&reg;</sup> .NET CLI is currently in preview and is installed with the `--prerelease` flag.

You can use the CLI to perform the following actions:

* Create a blank WPF app, or an app containing generated Syncfusion<sup style="font-size:70%">&reg;</sup> control samples. For details, refer to [Create a WPF project](/wpf/dotnet-cli/create-project).
* Add or update Syncfusion<sup style="font-size:70%">&reg;</sup> WPF NuGet package references in an existing project. For details, refer to [Manage packages](/wpf/dotnet-cli/manage-packages).
* Activate Syncfusion<sup style="font-size:70%">&reg;</sup> licenses for the controls used in a sample, and view installed licenses. For details, refer to [License activation](/wpf/dotnet-cli/licensing).
* Configure an official Syncfusion<sup style="font-size:70%">&reg;</sup> Model Context Protocol (MCP) server for AI coding clients. For details, refer to [MCP configuration](/wpf/dotnet-cli/configure-mcp).
* Install official Syncfusion<sup style="font-size:70%">&reg;</sup> component skills for AI agents. For details, refer to [AI skills installation](/wpf/dotnet-cli/install-skills).

This documentation covers the WPF platform.

## Prerequisites

The following software is required before you install and use the CLI:

* [.NET SDK](https://dotnet.microsoft.com/download). The SDK selected through `PATH` takes precedence, with the running .NET installation as a fallback.
* On Windows, the **.NET desktop development** workload for building and running WPF applications. On Linux and macOS, use `--post-action generate` for portable source generation.
* An internet connection so package operations can reach [nuget.org](https://www.nuget.org).
* A Syncfusion<sup style="font-size:70%">&reg;</sup> account to activate licenses. Sign in is performed through the browser during license activation.

N> Syncfusion<sup style="font-size:70%">&reg;</sup> packages resolve from the official nuget.org feed, `https://api.nuget.org/v3/index.json`. The CLI accepts only this source through `--source`.

## Installation

The CLI is published as a .NET global tool with the package ID `Syncfusion.DotNet.CLI`.

1. Open a terminal and run the following command. Add `--prerelease` while only preview versions are available.

    ```bash
    dotnet tool install -g Syncfusion.DotNet.CLI --prerelease
    ```

2. Verify the installation and print the CLI version.

    ```bash
    sf --version
    ```

To update the tool to the latest release, run:

```bash
dotnet tool update -g Syncfusion.DotNet.CLI --prerelease
```

To remove the tool, run:

```bash
dotnet tool uninstall -g Syncfusion.DotNet.CLI
```

## Initialize the CLI

Run `sf` in an interactive terminal to open the main menu. The menu shows the current CLI version and groups the available operations.

![Syncfusion .NET CLI main menu](images/cli-main-menu.png)

| Group | Operation | Command reference |
| --- | --- | --- |
| Project creation | Create a new project | `sf new` |
| Package management | Add a package to an existing project | `sf add` |
| Package management | Update a package in an existing project | `sf update` |
| Discovery | List available packages | `sf list <platform> packages` |
| Discovery | List installed packages in an existing project | `sf list <platform> installed` |
| Discovery | Search for packages | `sf search` |
| AI & Skills | Setup Model Context Protocol (MCP) | `sf mcp init` |
| AI & Skills | Add component skills to AI Agent | `sf skills install` |
| License management | Activate license | `sf license activate` |
| License management | View installed licenses | `sf license view` |
| License management | Sign in to Syncfusion | `sf login` |
| License management | Sign out | `sf logout` |
| Help and information | View CLI information | `sf info` |
| Help and information | Show help | `sf help` |
| Exit | Exit | `Ctrl+C` |

N> The `<platform>` text is a usage placeholder. Use `wpf` for WPF.

Use the following keys to navigate the interactive screens:

| Key | Action |
| --- | --- |
| Up / Down | Move through the options |
| Enter | Choose the focused option, or continue |
| Space | Toggle a checkbox in a multi-selection list |
| Escape | Cancel the current question and return to the menu |
| `Ctrl+C` | Exit the interactive session |

Complete direct commands remain usable without opening the menu. `--no-interactive` disables prompts in any command.

## Available commands

| Command | Purpose | For details, refer to |
| --- | --- | --- |
| `sf new wpf` | Create a new WPF project | [Create a WPF project](/wpf/dotnet-cli/create-project) |
| `sf add wpf <package>` | Add a Syncfusion<sup style="font-size:70%">&reg;</sup> package to an existing project | [Manage packages](/wpf/dotnet-cli/manage-packages) |
| `sf update wpf <package>` | Update a package in an existing project | [Manage packages](/wpf/dotnet-cli/manage-packages) |
| `sf list wpf packages` | List available packages | [Manage packages](/wpf/dotnet-cli/manage-packages) |
| `sf list wpf installed` | List installed packages in an existing project | [Manage packages](/wpf/dotnet-cli/manage-packages) |
| `sf search <text> --framework wpf` | Search the WPF package catalog | [Manage packages](/wpf/dotnet-cli/manage-packages) |
| `sf mcp init wpf` | Configure a project-local Syncfusion<sup style="font-size:70%">&reg;</sup> MCP client | [MCP configuration](/wpf/dotnet-cli/configure-mcp) |
| `sf skills install wpf` | Install Syncfusion<sup style="font-size:70%">&reg;</sup> component skills for AI agents | [AI skills installation](/wpf/dotnet-cli/install-skills) |
| `sf login` | Sign in to Syncfusion through the browser | [License activation](/wpf/dotnet-cli/licensing) |
| `sf logout` | Sign out and clear the local session | [License activation](/wpf/dotnet-cli/licensing) |
| `sf license activate` | Download the license for the project's packages and register it in the project's startup code | [License activation](/wpf/dotnet-cli/licensing) |
| `sf license view` | Show the licenses cached for the project (no network call) | [License activation](/wpf/dotnet-cli/licensing) |
| `sf info` | Show CLI information | |
| `sf help wpf` | Show the WPF command map | |
| `sf --version` | Show the CLI version | |

## See also

* [Syncfusion WPF controls](https://www.syncfusion.com/wpf-ui-controls)
* [WPF system requirements](https://help.syncfusion.com/wpf/system-requirements)
* [Installing WPF NuGet packages](https://help.syncfusion.com/wpf/installation/install-nuget-packages)
* [Syncfusion<sup style="font-size:70%">&reg;</sup> licensing overview](https://help.syncfusion.com/common/essential-studio/licensing/overview)
