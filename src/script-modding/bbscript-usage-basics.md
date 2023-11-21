# Script Modding with BBScript

## Basic Setup

To get started with character script modding, you will need [BBScript](https://github.com/super-continent/bbscript).
BBScript is a tool that can disassemble and reassemble the ArcSys character script bytecode.

Download a binary from the releases and put it somewhere either in the working directory where you will store your scripts, or somewhere that will register it to your systems `PATH`. Note that if you do put it in the systems `PATH`, you may need to specify a custom game config directory in either the `BBSCRIPT_DB_DIR` environment variable or using the `-c` flag.

## Using the Right Game Config

To find a current list of all the games supported by the BBScript release you downloaded, you can take a look at the `static_db` folder provided with the binary. the name of each config is what you will replace the `<GAME>` argument with in the following examples. For example, to parse a Guilty Gear Xrd Rev2 script, we use the config `ggrev2`.

## Parsing Scripts

To parse a script with BBScript, simply execute the `bbscript` binary in a command line (e.g. CMD, Powershell, Nushell) with the `parse` subcommand and then specify the game name, input file, and output file. Like this:

```
bbscript parse <GAME> bbscript_file.bbscript readable_bbscript.rbs
```

The `.rbs` extension is recommended for readable bbscript output to differentiate it from the bbscript bytecode files. But this is not necessary, they are just plaintext files.

## Rebuilding Scripts

To rebuild a readable BBScript file into a usable piece of script bytecode, use the `rebuild` subcommand in BBScript.
Like this:

```
bbscript rebuild <GAME> readable_bbscript.rbs rebuilt_script.bbscript
```

---

That's all you need to know to get started with using BBScript! The next sections will cover the readable BBScript language and what you should know when modifying game scripts.