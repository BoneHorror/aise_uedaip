# AIscript extension for StarCraft Remastered (UEDAIP ver)

This is a plugin that can be used with Samase to improve AI performance and add several new opcodes. It requires this modified version of PyAI https://github.com/neivv/PyMS and as of 2025, mostly the x64 version is tested.

## Usage

To use the plugin, place the compiled dll in ./samase/, where the root directory is your samase archive folder.

## Building

To build aise for regular (x64) use, run the following command:

cargo build --release --target x86_64-pc-windows-msvc

You need to have installed rust tools via whatever meeans and gotten dependencies from Cargo.toml

## UEDAIP features (todo)

I plan on implementing a custom rush scoring system that uses modded units for now.
