## Archipelago Plugin Template for BepInEx 5

This is a plugin template for starting to make an Archipelago plugin using BepInEx 5 with the very basics already set up.
It includes a small GUI to allow you to enter connection info and some building configuration already done.

## Using This Template

### Setting up BepInEx

Follow the [normal steps for installing BepInEx](https://docs.bepinex.dev/v5.4.16/articles/user_guide/installation/index.html)
for your game. I recommend using the
[MonoMod HookGenPatcher](https://github.com/harbingerofme/Bepinex.Monomod.HookGenPatcher/releases) and using monomod
hooks over Harmony Patching, but this is up to personal preference

### Installation

You will need [.NET 6 or newer](https://dotnet.microsoft.com/download) to install and use the template.

The template can be installed with the following command:
```
dotnet new install alwaysintreble.Archipelago.BepinEx
```

Then, to create a new project using the template, you can either select the template when creating a new project 
from within your IDE, or
```
dotnet new apbepin5 -n <MyPluginName> -T <TFM> -U <UnityVersion> -P <MyProjectName>
```

Template options:
```
-T, --TargetFramework <TargetFramework>  The target framework for the project
                                         Required: *true*
                                         Type: text
                                         Default: net35
-U, --UnityVersion <UnityVersion>        Unity version to use when developing the plugin
                                         Required: *true*
                                         Type: text
                                         Default: Example Archipelago Plugin
-P, --ProjectName <ProjectName>          Name of the project
                                         Required: *true*
                                         Type: text
-D, --Description <Description>          Plugin description
                                         Type: text
                                         Default: Example Archipelago Plugin
-V, --Version <Version>                  Plugin version
                                         Type: text
                                         Default: 1.0.0
-G, --Game <Game>                        Name of the game this plugin is for
                                         Type: text
                                         Default: My Game
-Pa, --Path <Path>                       File path to the game executable. Passing this will set up debug output to the plugins folder
                                         Type: text
                                         Default: C:\My Game
```

To determine your unity version and which framework you should be targeting you can refer to
https://docs.bepinex.dev/articles/dev_guide/plugin_tutorial/2_plugin_start.html.
If you are targeting .net 3.5 you may need to modify a few methods as the `#if` don't work very well in templates.
