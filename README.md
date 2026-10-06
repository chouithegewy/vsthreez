# vsthreez

A container repository for the Threez audio plug-ins. Each plug-in lives in its
own repository and is linked here as a Git submodule.

| Repository | Description |
| --- | --- |
| [phatbooty](https://github.com/chouithegewy/phatbooty) | A VST3 bass synth with a tempo-synced groove generator. |
| [threezpoly](https://github.com/chouithegewy/threezpoly) | A polyphonic subtractive synth in Rust, available as CLAP and VST3. |

## Clone

```sh
git clone --recurse-submodules https://github.com/chouithegewy/vsthreez.git
cd vsthreez
```

If you already cloned the container without its submodules:

```sh
git submodule update --init --recursive
```

## Build

See each project's instructions:

- [Phat Booty build instructions](phatbooty/README.md#building)
- [Threez Poly build instructions](threezpoly/README.md#building)

Phat Booty expects the VST 3 SDK alongside its repository. From the container's
root, clone it if it is not already present:

```sh
git clone --recursive https://github.com/steinbergmedia/vst3sdk.git vst3sdk
```

The SDK is a local dependency and is ignored by this container repository.

## Working with the plug-ins

Commit and push plug-in changes inside the corresponding submodule, then record
the updated commit in this container:

```sh
git add phatbooty threezpoly
git commit -m "Update plug-in revisions"
git push
```

After pulling changes to the container, check out its recorded plug-in revisions:

```sh
git submodule update --init --recursive
```
