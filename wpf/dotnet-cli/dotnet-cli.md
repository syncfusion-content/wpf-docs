---
layout: post
title: Syncfusion .NET CLI Overview for WPF | Syncfusion®
description: Learn to install and use the Syncfusion® .NET CLI (sf) to create WPF apps, manage Syncfusion WPF NuGet packages, and register licenses from the command line.
platform: wpf
control: Syncfusion<sup>®</sup> .NET CLI
documentation: ug
---

# Overview of the Syncfusion® .NET CLI for WPF

The Syncfusion<sup style="font-size:70%">&reg;</sup> .NET CLI (`sf`) is a cross-platform command line tool that creates WPF projects, manages Syncfusion<sup style="font-size:70%">&reg;</sup> WPF NuGet packages, and registers licenses from a terminal. After you install the CLI, you can run `sf` with no arguments to open an interactive menu, or run a direct command such as `sf new wpf` for scripted, prompt-free creation.

N> The Syncfusion<sup style="font-size:70%">&reg;</sup> .NET CLI is currently in preview and is installed with the `--prerelease` flag.

You can use the CLI to perform the following actions:

* Create a blank WPF app, or an app containing generated Syncfusion<sup style="font-size:70%">&reg;</sup> control samples.
* Add or update Syncfusion<sup style="font-size:70%">&reg;</sup> WPF NuGet package references in an existing project.
* List available and installed packages, and search the package catalog.
* Activate Syncfusion<sup style="font-size:70%">&reg;</sup> licenses for the controls used in a sample, and view installed licenses.
* Apply a Syncfusion theme such as Windows11 (Light) or Material3 (Dark) to a new project.
* Generate projects for .NET MAUI, Blazor, WPF, WinForms, and WinUI 3.

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

| Command | Purpose |
| --- | --- |
| `sf new wpf` | Create a new WPF project |
| `sf add wpf <package>` | Add a Syncfusion<sup style="font-size:70%">&reg;</sup> package to an existing project |
| `sf update wpf <package>` | Update a package in an existing project |
| `sf list wpf packages` | List available packages |
| `sf list wpf installed` | List installed packages in an existing project |
| `sf search <text> --framework wpf` | Search the WPF package catalog |
| `sf login` | Sign in to Syncfusion through the browser |
| `sf logout` | Sign out and clear the local session |
| `sf license activate` | Download the license for the project's packages and register it in the project's startup code |
| `sf license view` | Show the licenses cached for the project (no network call) |
| `sf info` | Show CLI information |
| `sf help wpf` | Show the WPF command map |
| `sf --version` | Show the CLI version |

## Create a WPF project

You can create a WPF project through the interactive wizard or a direct command.

### Create a project using the interactive wizard

Run `sf new`, or select **Create a new project** from the main menu. The WPF creation flow is:

1. **Platform:** Select **WPF**.
2. **Language:** Select **C#** or **VB**. C# is the default for direct commands.
3. **Target framework:** Select the .NET version.

    * .NET 10 (`net10.0`), the default
    * .NET 9 (`net9.0`)
    * .NET 8 (`net8.0`)
    * .NET Framework 4.8 (`net48`)
    * .NET Framework 4.7 (`net47`)
    * .NET Framework 4.6.2 (`net462`)

4. **Project location and name:** Enter the parent directory and the project name. The default locations are `%USERPROFILE%\source\repos` on Windows and `~/Projects` on Linux and macOS. The suggested name is `SyncfusionWpfApp`, and the first available numeric suffix is used when the destination name collides.

    ![Project creation in the Syncfusion .NET CLI](images/cli-create-new-project.png)

5. **Setup:** Select **Empty project** or **Project with Syncfusion controls**.

6. **Controls:** When you include controls, choose one or more controls from the list. Use the arrow keys to navigate, Space to toggle, and Enter to continue. At least one selection is required.

7. **Theme:** When the project includes controls, select one of the Syncfusion themes:

    | Theme | Option value |
    | --- | --- |
    | Windows11 (Light) | `Windows11Light` |
    | Windows11 (Dark) | `Windows11Dark` |
    | Material3 (Light) | `Material3Light` |
    | Material3 (Dark) | `Material3Dark` |
    | Office2019 (Colorful) | `Office2019Colorful` |

    The theme applies to the generated app through [SkinManager](https://help.syncfusion.com/wpf/themes/skin-manager). An empty project uses the `Windows11Light` default without prompting.

    ![Configured WPF options in the Syncfusion .NET CLI](images/cli-configured-wpf-options.png)

8. **Post-create:** Select **Generate only** or **Build project**.
9. **Confirmation:** Review the selected values and confirm to create the project.

N> A complete direct command does not open the wizard. When a name is missing in an interactive terminal, the wizard supplies a default and collects the remaining unspecified inputs. Missing required values in scripts produce an error.

### Available controls

The following controls are available in a new WPF project:

| Control | Control ID |
| --- | --- |
| AI AssistView | `ai-assist-view` |
| Chart | `chart` |
| DataGrid | `datagrid` |
| Diagram | `diagram` |
| DockingManager | `docking-manager` |
| Gantt | `gantt` |
| Kanban | `kanban` |
| NavigationDrawer | `navigation-drawer` |
| Ribbon | `ribbon` |
| Scheduler | `scheduler` |
| TreeGrid | `treegrid` |

### Create a project using direct commands

To create a blank project without the wizard:

```bash
sf new wpf --name MyApp
```

To create a project containing Syncfusion<sup style="font-size:70%">&reg;</sup> control samples:

```bash
sf new wpf --name MyApp --control datagrid
sf new wpf --name MyApp --control datagrid scheduler
sf new wpf --name ReportsVB --language VB --target-framework net48
sf new wpf --name Reports --language C# --target-framework net10.0 --theme Windows11Dark --control chart --control datagrid --post-action build
```

A generated project places each control sample in a `TabControl` tab with a Welcome page. The [SkinManager](https://help.syncfusion.com/wpf/themes/skin-manager) applies the selected theme through `SfSkinManager.SetTheme`.

![Generated WPF project with control samples in the Syncfusion .NET CLI](images/cli-sample-generated.png)

N> A complete direct command does not open the wizard. Neither `--force` nor confirmation authorizes overwriting an existing project destination.

## Run the created project

On Windows, build and run the generated project:

```bash
dotnet run --project ./MyApp/MyApp.csproj
```

On Linux and macOS, use `--post-action generate` when creating the project. The CLI explains that building and running WPF applications requires a supported Windows environment, and file generation remains available.

N> Modern WPF projects (`net8.0` and later) use `EnableWindowsTargeting`, so restore works on other hosts, but building and launching require Windows. .NET Framework projects (`net462`, `net47`, `net48`) require Visual Studio MSBuild with the .NET desktop workload.

## Manage packages in an existing project

Package operations change NuGet references only. They do not generate control files.

`<package>` accepts a canonical package alias, a canonical package ID, or an exact unambiguous package display name:

```bash
sf add wpf datagrid
sf add wpf Syncfusion.SfGrid.WPF
sf update wpf chart --path ./MyApp --version 35.1.40
```

To list the available WPF packages:

```bash
sf list wpf packages
```

![List of available WPF packages in the Syncfusion .NET CLI](images/cli-list-of-available-packages.png)

To list the installed packages in an existing project, and to search the catalog:

```bash
sf list wpf installed --path ./MyApp
sf search chart --framework wpf
```

Existing-project commands accept `-p/--path` with a project file, a project directory, or a supported subdirectory. Discovery stops at the nearest project or repository boundary. `--json` emits one JSON document for script use. Use `--details` or `--verbose` to see package descriptions and whether a generated sample is available.

## Activate Syncfusion<sup style="font-size:70%">&reg;</sup> licenses

The CLI detects the Syncfusion<sup style="font-size:70%">&reg;</sup> controls used in a project, downloads the matching license keys from your Syncfusion<sup style="font-size:70%">&reg;</sup> account, and registers the keys in the project's startup code. For example, when a sample is created with the Chart control, the CLI registers the license for `Syncfusion.SfChart.WPF` in `App.xaml.cs` so the build runs without a license warning.

N> Open the Command Prompt or Terminal in the target sample's project directory before running the license activation command. The license operation is project-specific, and the command path must point to the intended sample.

### How license activation works

1. The CLI scans the project at the current directory or at the path you pass through `--path`. It identifies the platform from the project file (`.csproj`) and detects all Syncfusion<sup style="font-size:70%">&reg;</sup> `PackageReference` entries whose IDs start with `Syncfusion.`.
2. It checks your Syncfusion<sup style="font-size:70%">&reg;</sup> account for entitlements that cover each detected package. When a paid or trial entitlement is available, the matching license keys are downloaded.
3. The keys are cached in `syncfusion-license.txt` and metadata in `.syncfusion/license-meta.json` inside the project directory.
4. The CLI inserts `SyncfusionLicenseProvider.RegisterLicense(...)` into the platform-specific startup file. For WPF, the block is added to `App.xaml.cs` inside the `App` constructor. The block is idempotent, so re-running the command refreshes the keys without duplicating the call.
5. If a control in the project is not covered by a paid entitlement, the CLI prompts you to accept the Syncfusion<sup style="font-size:70%">&reg;</sup> trial EULA and download a trial key for the missing packages. Pass `--yes` to accept the prompt automatically.

### Activate a license through the interactive menu

1. Open the Command Prompt or Terminal in the target sample's project directory.

    ```bash
    cd D:\CLI\NetWpfSample
    ```

2. Run `sf` to open the main menu.

    ```bash
    sf
    ```

3. Under **License management**, select **Activate license**. The CLI focuses the **Activate License** entry and shows the navigation hint at the bottom of the screen.

    ![Activate license option in the Syncfusion .NET CLI](images/cli-activate-license-menu.png)

4. If you are not signed in, the CLI opens your default browser to the Syncfusion<sup style="font-size:70%">&reg;</sup> sign-in page. Complete sign in with your Syncfusion<sup style="font-size:70%">&reg;</sup> account.

    ![Syncfusion sign-in page in the browser](images/cli-license-sign-in.png)

5. After sign in, the CLI checks your entitlements, downloads the matching keys for the Syncfusion<sup style="font-size:70%">&reg;</sup> controls in the sample, and registers the keys in `App.xaml.cs`.

    ![License registered successfully in the Syncfusion .NET CLI](images/cli-license-registered.png)

6. Rebuild the application so the newly registered license is applied. The CLI prints the following reminder at the end of the activation output.

    > Note: Rebuild the application so the newly registered license is applied.

### Activate a license using a direct command

Run the activation command from the sample's project directory:

```bash
sf license activate
```

Pass `--path` to point the CLI at a specific project directory or `.csproj` file:

```bash
sf license activate --path ./MyApp
sf license activate --path ./MyApp/MyApp.csproj
```

Use `--yes` to accept the trial EULA prompt without asking:

```bash
sf license activate --yes
```

Use `--file` to activate from an existing key file. With no value, the CLI reads `./syncfusion-license.txt` from the project directory. With an absolute path, the CLI uses the specified file instead:

```bash
sf license activate --file
sf license activate --file C:\keys\syncfusion-license.txt
```

N> When a license key is supplied through `--file`, the CLI skips sign in and download and registers the keys already in the file. The file path must be absolute.

### View installed licenses

To see the licenses cached for the current project, run:

```bash
sf license view
```

The command reads the cached metadata, lists each product, the license type, the status, and the expiry date, and warns when a Syncfusion<sup style="font-size:70%">&reg;</sup> package in the project is not covered.

![View installed licenses in the Syncfusion .NET CLI](images/cli-view-installed-license-menu.png)

The cached output reports the registered email, platform, major version, and one row per product.

![Installed license details in the Syncfusion .NET CLI](images/cli-view-installed-license.png)

### License operation notes

* License activation is project-specific. The command path must point to the intended sample, because each project is detected through its `.csproj` and scanned independently.
* The CLI writes `syncfusion-license.txt` and `.syncfusion/license-meta.json` to the project directory.
* The startup file the CLI modifies by platform is `MauiProgram.cs` for .NET MAUI, `Program.cs` for Blazor, `App.xaml.cs` for WPF, `App.xaml.cs` for WinUI, and `Program.cs` (or `Application.xaml.vb` for VB) for WinForms.
* Use `sf logout` to clear the local sign-in session. Use `sf login` to sign in again without running activation.

## Help

To show the concise command map and the WPF command map:

```bash
sf help
sf help wpf
```

![Show help in the Syncfusion .NET CLI](images/cli-show-help.png)

## Options reference

### Creation options

| Option | Description |
| --- | --- |
| `-n`, `--name` | Project name. Required when prompting is unavailable |
| `-p`, `--path` | Parent directory. Defaults to the current directory |
| `-t`, `--target-framework` | The .NET target framework, such as `net10.0` or `net48` |
| `--language` | Project language: `C#` or `VB`. Defaults to C# |
| `--theme` | The Syncfusion theme, such as `Windows11Dark`. Defaults to `Windows11Light` |
| `--control` | One or more control IDs, or `empty`. Omit to create an empty project |
| `--post-action` | Post-create action: `generate` or `build`. Defaults to `build` for direct commands |
| `--dry-run` | Preview the action without making changes |
| `--force` | Allow supported overwrites. Edited control samples remain protected |
| `--no-restore` | Skip `dotnet restore` after the action |
| `--no-build` | Skip `dotnet build` after the action |
| `--no-interactive` | Disable interactive prompts |
| `--json` | Emit a JSON document instead of table output |

N> `--post-action build` conflicts with `--no-build`. Failed creation, restore, or build rolls back the owned project directory.

### Package operation options

| Option | Description |
| --- | --- |
| `-p`, `--path` | The project directory, `.csproj` file, or a supported subdirectory |
| `-v`, `--version` | The Syncfusion<sup style="font-size:70%">&reg;</sup> NuGet package version |
| `--source` | Package source; Syncfusion<sup style="font-size:70%">&reg;</sup> packages require `https://api.nuget.org/v3/index.json` |
| `--configfile` | The NuGet configuration file to use |
| `--dry-run` | Preview the action without making changes |
| `--force` | Allow supported overwrites |
| `--no-restore` | Skip `dotnet restore` after the action |
| `--json` | Emit one JSON document |

### License options

| Option | Description |
| --- | --- |
| `-p`, `--path` | The project directory or `.csproj`/`.vbproj` to scan for Syncfusion<sup style="font-size:70%">&reg;</sup> packages. Defaults to the current directory |
| `-y`, `--yes` | Accept the trial EULA prompt automatically during activation |
| `--file` | Activate from an existing key file. With no value, the CLI reads `./syncfusion-license.txt` from the project directory. With an absolute path, the CLI uses the specified file |
| `--json` | Emit one JSON document instead of table output |

## FAQs

**Does the CLI register a license?** Yes. `sf license activate` scans the project for Syncfusion<sup style="font-size:70%">&reg;</sup> `PackageReference` entries, downloads the matching license keys from your Syncfusion<sup style="font-size:70%">&reg;</sup> account, and inserts `SyncfusionLicenseProvider.RegisterLicense(...)` into `App.xaml.cs` (or the platform-specific startup file). The CLI signs you in through the browser the first time, or you can sign in ahead with `sf login`. For background information on Syncfusion<sup style="font-size:70%">&reg;</sup> licensing, refer to the [licensing overview](https://help.syncfusion.com/common/essential-studio/licensing/overview).

**Does `sf add wpf datagrid` generate the DataGrid sample?** In a CLI-generated project, yes. In an ordinary project, the command adds the NuGet package reference only and reports that no sample was generated.

**Where does the CLI register the license for WPF?** In `App.xaml.cs`, inside the `App` constructor. For .NET MAUI, Blazor, WinUI, and WinForms, the CLI targets `MauiProgram.cs`, `Program.cs`, `App.xaml.cs`, and `Program.cs` respectively.

**Can I use my own key file?** Yes. Run `sf license activate --file C:\keys\syncfusion-license.txt` with an absolute path. The CLI reads the keys from the file and registers them in the project's startup code without contacting the license service.

**Which .NET versions are supported?** .NET 10 (`net10.0`), .NET 9 (`net9.0`), .NET 8 (`net8.0`), .NET Framework 4.8 (`net48`), 4.7 (`net47`), and 4.6.2 (`net462`).

**Which platforms does the CLI support?** .NET MAUI, Blazor, WPF, WinForms, and WinUI 3. This documentation covers WPF.

## See also

* [Syncfusion WPF controls](https://www.syncfusion.com/wpf-ui-controls)
* [WPF system requirements](https://help.syncfusion.com/wpf/system-requirements)
* [Installing WPF NuGet packages](https://help.syncfusion.com/wpf/installation/install-nuget-packages)
* [SkinManager theme overview](https://help.syncfusion.com/wpf/themes/skin-manager)
* [Syncfusion<sup style="font-size:70%">&reg;</sup> licensing overview](https://help.syncfusion.com/common/essential-studio/licensing/overview)