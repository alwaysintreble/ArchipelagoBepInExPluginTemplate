## Archipelago Plugin Template for BepInEx 5

This is a plugin template for starting to make an Archipelago plugin using BepInEx 5 with the very basics already set up.
It includes a small GUI to allow you to enter connection info and some building configuration already done.

## Using This Template

### Setting up BepInEx

Follow the [normal steps for installing BepInEx](https://docs.bepinex.dev/v5.4.16/articles/user_guide/installation/index.html)
for your game. I personally recommend using the
[MonoMod HookGenPatcher](https://github.com/harbingerofme/Bepinex.Monomod.HookGenPatcher/releases) and using monomod
hooks over Harmony Patching. With this patcher you can package BepInEx, the patcher, and your mod all together in a
single archive to help with ease of installation.

### Renaming the Project

To rename the project, first open the solution in your IDE, then right click the solution, select edit solution,
and rename the project name as well as the csproj's filename that the solution should be looking for.

![img](/docs/solution%20rename.png)

Next, close your IDE, navigate to the folder containing the solution in your file browser, and rename the solution and
project to your desired name. If present, delete /bin/ and /obj/. Open the solution in your IDE and confirm that
everything loads. If it fails to load, confirm that the names your solution is looking for is correct and reload your IDE.

### Setting build paths

This template is already set up to strip unnecessary file packaging. There are also commands for the output paths where
you would like to build, simply edit the csproj in your IDE and change the XML under the debug and release builds to
your desired paths.
