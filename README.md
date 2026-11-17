# Diamond Framework

The start of a roleplay framework for FiveM (GTA V multiplayer), written in C#.

**Status: abandoned learning project, May 2021.** I worked on it for one week. Most of the plan in [TODO.md](TODO.md) was never built.

## What is in it

- `Diamond.Shared`: characters, an inventory system (player and vehicle inventories) and item base classes (food, drink, alcohol, weapons, ammo, blueprints).
- `Diamond.Client`: character, inventory, money, shop and weapon handlers, and a police tackle.
- `Diamond.Server`: server entry point and a salary handler.
- `Diamond.UserInterface`: the in-game UI as a Blazor WebAssembly app, loaded as the resource's NUI page. Getting Blazor to run inside FiveM was the part I was most pleased with.

There is no database. Data is passed between client and server as JSON and nothing is saved.

## Running it

I have not built it since 2021 and it may not build today.

1. Put the repository in a FiveM server's `resources` folder.
2. Build `Diamond.sln` in Visual Studio or Rider. The client and server projects target .NET Framework 4.5.2; the UI project targets .NET 5. The client project expects `MenuAPI.dll` in `Diamond.Client/References`, which is not in the repository, and one reference in `Diamond.Client.csproj` points at a NuGet path on my old machine that you will need to fix.
3. Publish `Diamond.UserInterface` in Release mode. `fxmanifest.lua` loads the UI from its `publish/wwwroot` folder.
4. Add `ensure Diamond-Framework` to `server.cfg`.
