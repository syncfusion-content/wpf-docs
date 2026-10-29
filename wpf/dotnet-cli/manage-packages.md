---
layout: post
title: Manage Syncfusion WPF NuGet Packages using .NET CLI | Syncfusion®
description: Learn here about how to add, update, list, and search Syncfusion® WPF NuGet packages in an existing project using the Syncfusion® .NET CLI (sf).
platform: wpf
control: Syncfusion<sup>®</sup> .NET CLI
documentation: ug
---

# Manage packages in an existing project

Package operations change NuGet references only. They do not generate control files. In a CLI-generated project, supported package aliases also integrate their samples. In an ordinary project, the same command adds the package reference only, and the CLI reports that no sample was generated.

## Add a package using the alias

To add a Syncfusion<sup style="font-size:70%">&reg;</sup> package to an existing project using its canonical package alias:

{% tabs %}
{% highlight bash %}

sf add wpf datagrid --path ./MyApp

{% endhighlight %}
{% endtabs %}

## Add a package using the package ID

To add a package using its exact NuGet package identifier:

{% tabs %}
{% highlight bash %}

sf add wpf Syncfusion.SfGrid.WPF --path ./MyApp

{% endhighlight %}
{% endtabs %}

`<package>` accepts a canonical package alias, a canonical package ID, or an exact unambiguous package display name.

## Update a package

To update a package in an existing project to a specific version:

{% tabs %}
{% highlight bash %}

sf update wpf chart --path ./MyApp --version 35.1.40

{% endhighlight %}
{% endtabs %}

## List available packages

To list the Syncfusion<sup style="font-size:70%">&reg;</sup> WPF packages available in the catalog:

{% tabs %}
{% highlight bash %}

sf list wpf packages

{% endhighlight %}
{% endtabs %}

![List of available WPF packages in the Syncfusion .NET CLI](images/cli-list-of-available-packages.png)

## List installed packages

To list the Syncfusion<sup style="font-size:70%">&reg;</sup> packages already installed in an existing project:

{% tabs %}
{% highlight bash %}

sf list wpf installed --path ./MyApp

{% endhighlight %}
{% endtabs %}

## Search packages

To search the WPF package catalog:

{% tabs %}
{% highlight bash %}

sf search chart --framework wpf

{% endhighlight %}
{% endtabs %}

Existing-project commands accept `-p/--path` with a project file, a project directory, or a supported subdirectory. Discovery stops at the nearest project or repository boundary. `--json` emits one JSON document for script use.

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

## FAQs

**Does `sf add wpf datagrid` generate the DataGrid sample?**

In a CLI-generated project, yes. In an ordinary project, the command adds the NuGet package reference only, and the CLI reports that no sample was generated.

**Can I install a package that is not in the catalog?**

No. The CLI resolves packages from the official nuget.org feed, `https://api.nuget.org/v3/index.json`, and accepts only this source through `--source`.

## See also

* [Create a WPF project](/wpf/dotnet-cli/create-project)
* [License activation](/wpf/dotnet-cli/licensing)
* [Installing WPF NuGet packages](https://help.syncfusion.com/wpf/installation/install-nuget-packages)
