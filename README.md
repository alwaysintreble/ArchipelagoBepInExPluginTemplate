## Archipelago Plugin Template for BepInEx 5 and 6

This is a plugin template for starting to make an Archipelago plugin using BepInEx 5 and BepInEx 6, with the very basics
already set up. It includes a small GUI to allow you to enter connection info and some building configuration already
done.

## Using These Templates

### Setting up BepInEx

Follow the [normal steps for installing BepInEx](https://docs.bepinex.dev/v5.4.16/articles/user_guide/installation/index.html)
for your game. I recommend using the
[MonoMod HookGenPatcher](https://github.com/harbingerofme/Bepinex.Monomod.HookGenPatcher/releases) and using monomod
hooks over Harmony Patching, but this is up to personal preference

### Installation

You will need [.NET 6 or newer](https://dotnet.microsoft.com/download) to install and use the template.

The templates can be installed with the following command:
```
dotnet new install alwaysintreble.Archipelago.BepinEx
```
and will install the following templates:

| Template Name                           | Short Name        | Language | Tags                                 |
|-----------------------------------------|-------------------|----------|--------------------------------------|
| Archipelago BepinEx 5 Plugin            | apbepin5          | [C#]     | Archipelago/BepInEx/BepInEx 5/Plugin |
| ArchipelagoBepin6Template.Net.CoreCLR   | apbepin6core      | [C#]     | Archipelago/BepInEx/BepInEx 6/Plugin |
| ArchipelagoBepin6Template.NET.Framework | apbepin6framework | [C#]     | Archipelago/BepInEx/BepInEx 6/Plugin |
| ArchipelagoBepin6Template.Unity.IL2Cpp  | apbepin6il2cpp    | [C#]     | Archipelago/BepInEx/BepInEx 6/Plugin |
| ArchipelagoBepin6Template.Unity.Mono    | apbepin6mono      | [C#]     | Archipelago/BepInEx/BepInEx 6/Plugin |

Then, to create a new project using the template, you can either select the template when creating a new project 
from within your IDE, or
```
dotnet new apbepin5 -n <MyPluginName> -T <TFM> -U <UnityVersion> -P <MyProjectName>
```

Template options:
```
  -T, --TargetFramework <TargetFramework>             The target framework for the project
                                                      Required: *true* (this is only required for the 5 and mono templates)
                                                      Type: text
                                                      Default: net35
  -U, --UnityVersion <UnityVersion>                   Unity version to use when developing the plugin
                                                      Required: *true*
                                                      Type: text
                                                      Default: 5.6.0
  -P, --ProjectName <ProjectName>                     Name of the project
                                                      Required: *true*
                                                      Type: text
  -D, --Description <Description>                     Plugin description
                                                      Type: text
                                                      Default: Example Archipelago Plugin
  -V, --Version <Version>                             Plugin version
                                                      Type: text
                                                      Default: 1.0.0
  -G, --Game <Game>                                   Name of the game this plugin is for
                                                      Type: text
                                                      Default: My Game
  -Pa, --Path <Path>                                  File path to the game executable. Passing this will set up debug output to the plugins folder
                                                      Type: text
                                                      Default: C:\My Game
  -I, --ItemsHandlingFlags <NoItems|RemoteItems|...>  Whether and which item packets this client should receive from the server. For more info see
                                                      https://archipelagomw.github.io/Archipelago.MultiClient.Net/api/Archipelago.MultiClient.Net.Enums.ItemsHandlingFlags.html
                                                      Type: choice
                                                        NoItems                   Don't get any ReceivedItems packets from the server.
                                                        RemoteItems               Get ReceivedItems packets for items being granted to you by others.
                                                        IncludeOwnItems           Get ReceivedItems packets for items which you picked up in your own world.
                                                                                  Automatically includes RemoteItems option as it is required to set this.
                                                        IncludeStartingInventory  Get ReceivedItems packets for your starting inventory.
                                                                                  Automatically includes RemoteItems option as it is required to set this.
                                                        AllItems                  Get ReceivedItems packets for all remote items, items in your world,
                                                                                  and starting inventory granted to you.
```

To determine your unity version and which framework you should be targeting you can refer to
https://docs.bepinex.dev/articles/dev_guide/plugin_tutorial/2_plugin_start.html.
If you are targeting .net 3.5 you may need to modify a few methods as the `#if` don't work very well in templates.
