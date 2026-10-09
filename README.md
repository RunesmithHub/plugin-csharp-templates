# C# templates for Runesmith

The official C# templates plugin for [Runesmith](https://github.com/RunesmithHub/Runesmith), `runesmith.csharp-templates`. It lists the
project templates of every .NET SDK Runesmith finds, and of every template package you installed with `dotnet new install`, in
**File › New Project**:

- C#, F# and Visual Basic project templates, each shown once with a **Language** choice;
- the template's parameters as options: drop-downs, check boxes, number and text fields, and **Target framework**;
- **Create** runs `dotnet new` with the .NET SDK you picked, in a folder of its own next to a `.slnx` solution that lists the project.

It reads the template packages without unpacking them. The
[templates documentation](https://runesmithhub.github.io/Runesmith/plugins/csharp#templates) describes where it looks and which templates
it lists.

## Capabilities

| Capability | Why |
| --- | --- |
| `process` | Runs `dotnet new` to create your projects. |
| `filesystem` | Reads the template packages of your .NET SDKs and the ones you installed. |
| `environment` | Finds your .NET SDK and template packages through `PATH`, `DOTNET_ROOT` and your home folder. |

## Install

Install **C# templates** from Runesmith's plugin manager (**Tools › Plugins**), or from its page on the plugin hub,
https://hub.runesmith.dev. It needs the [.NET SDK](https://dot.net), which the C# plugin can also download in **File › SDKs...**.

## Build and test

You need the .NET SDK version in `global.json`. The Runesmith packages come from the plugin hub's feed, which `nuget.config` sets up.

```sh
dotnet build plugin-csharp-templates.slnx -warnaserror
dotnet format plugin-csharp-templates.slnx --verify-no-changes
dotnet test --solution plugin-csharp-templates.slnx
```

`dotnet build src/Runesmith.CSharp.Templates -t:InstallPlugin` installs your build into Runesmith's plugins folder; restart Runesmith to
load it.

## Documentation

Runesmith's documentation, including how plugins work and how to write one, is at https://runesmithhub.github.io/Runesmith/.

## License

Apache-2.0. See [LICENSE](LICENSE) and [NOTICE](NOTICE).
