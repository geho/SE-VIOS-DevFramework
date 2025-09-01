# Workspace Map (SEFramework)
- Scripts/
  - VIOS-Dev/           (MDK² PB script; entry: Program.cs; output=dist, local=auto)
- Mixins/
  - VIOS/               (MDK² mixin; no direct build output)

## Build
- Windows dev: run "build:all" task or `dotnet build` in a script folder (packs to %APPDATA% via mdk.local.ini).
- CI/Linux: `dotnet build -c Release` produces packed scripts in `dist/`.

## Conventions
- No LINQ allocations in `Main`; budgeting against Runtime.CurrentInstructionCount.
- Shared code lives in Mixins; PB projects consume via MDK² mixin include.
- AI: Only edit under Scripts/* and Mixins/*; never place outputs in repo except /dist.

