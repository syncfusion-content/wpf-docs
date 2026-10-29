---
layout: post
title: Manage Syncfusion WPF NuGet Packages using .NET CLI | Syncfusion®
description: Learn here about how to add, update, list, and search Syncfusion® WPF NuGet packages in an existing project using the Syncfusion® .NET CLI (sf).
platform: wpf
control: Syncfusion<sup>®</sup> .NET CLI
documentation: ug
---

# Manage packages in an existing project

Package operations change NuGet references only. They do not generate control files.

`<package>` accepts a canonical package alias, a canonical package ID, or an exact unambiguous package display name:

```bash
sf add wpf datagrid
sf add wpf Syncfusion.SfGrid.WPF
sf update wpf chart --path ./MyApp --version 35.1.40
```

In a CLI-generated project, supported package aliases also integrate their samples. In an ordinary project, the same command adds the package reference only, and the CLI reports that no sample was generated.

## List packages

To list the available WPF packages:

```bash
sf list wpf packages
```

![List of available WPF packages in the Syncfusion .NET CLI](images/cli-list-of-available-packages.png)

To list the installed packages in an existing project:

```bash
sf list wpf installed --path ./MyApp
```

## Search packages

To search the WPF package catalog:

```bash
sf search chart --framework wpf
```

Existing-project commands accept `-p/--path` with a project file, a project directory, or a supported subdirectory. Discovery stops at the nearest project or repository boundary. `--json` emits one JSON document for script use. Use `--details` or `--verbose` to see package descriptions and whether a generated sample is available.

## Package operation options

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

## See also

* [Create a WPF project](/wpf/dotnet-cli/create-project)
* [License activation](/wpf/dotnet-cli/licensing)
* [Installing WPF NuGet packages](https://help.syncfusion.com/wpf/installation/install-nuget-packages)
