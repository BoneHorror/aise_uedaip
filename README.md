# AIscript extension for StarCraft Remastered (UEDAIP ver)

This is a plugin that can be used with Samase to improve AI performance and add several new opcodes. It requires this modified version of PyAI https://github.com/neivv/PyMS and as of 2025, mostly the x64 version is tested.

## Usage

To use the plugin, place the compiled dll in ./samase/, where the root directory is your samase archive folder.

## Building

To build aise for regular (x64) use, run the following command:

cargo build --release --target x86_64-pc-windows-msvc

You need to have installed rust tools via whatever meeans and gotten dependencies from Cargo.toml

## UEDAIP features

### rush(mode, label)

Jumps to `label` if the condition specified by `mode` is met. This opcode uses custom scoring logic to evaluate enemy strength and composition. The enemy player is checked based on calling attack_prepare and clearing it instantly, so in principle using rush just before an attack should typically check against whichever player we will attack in Multiplayer. Rush should not be used during an attack.

Modes:
* 0: Enemy has started building their first production structure (Barracks, Pool, Gateway).
* 1: Enemy has low numbers of basic units (early check).
* 2: Enemy has medium numbers of basic units.
* 3: Enemy has high numbers of basic units (all-in).
* 4: Enemy has typical opening push composition.
* 5: Enemy has low ground defense score (can defend scouts).
* 6: Enemy has medium ground defense score (can defend small pushes).
* 7: Enemy has high ground defense score (can defend early timings).
* 8: Enemy has any air defense.
* 9: Enemy can defend against a few air units.
* 10: Enemy can defend against mid-sized air pushes.
* 11: Enemy has potential for cloaked units soon.
* 12: Enemy is actively using cloaked units.
* 13: Enemy has siege units available.
* 14: Enemy has lots of siege units.
* 15: Enemy has any anti-air.
* 16: Enemy has basic anti-air.
* 17: Enemy has lots of anti-air.
* 18: Enemy has any air units.
* 19: Enemy has some air units.
* 20: Enemy has a lot of air units.
