# zCLI :: a CLI framework written in zsh

```text
 ________  ________  ___       ___     
|\_____  \|\   ____\|\  \     |\  \    
 \|___/  /\ \  \___|\ \  \    \ \  \   
     /  / /\ \  \    \ \  \    \ \  \  
    /  /_/__\ \  \____\ \  \____\ \  \ 
   |\________\ \_______\ \_______\ \__\
    \|_______|\|_______|\|_______|\|__|
```

## This is a work in progress and should receive regular updates

Please feel free to create pull requests with  your ideas and/or modifications!

## What is zCLI

zCLI is a framework that provides an easy way to build out your CLI using any language.  The framework itself is written scripted in zsh, but any executable file, or file that can be made executable with `chmod +x` can fit into it.

## How does it work

Basically, anything inside of the directory structure `./resources` run.  An example has been provided, but the format can be modified as needed.

### Example

The example provides has the following directory/file structure:
`./resources/dependencies/init`

The corresponding zCLI command would be:
`./zcli dependencies init`

The cli traverses the directory strucuture and the last parameter is the executable.

You can modify this, but it is recommended that you follow the format of:
`.zcli RESOURCE VERB`
Where RESOURCE is a diredtory and VERB is an executable file or script.  Any number of VERBS (scripts) can be placed into the RESOURCE directory.

### Help Files

Upon error the cli will look for a file named `help-${VERB}` in the resource directory.
If it can't find one it will then look for `help` in that directory.
If it can't find that it will move backwards through the directory structure looking for the filename `help` and display that before exiting.

## Configuration Files

The main configuration file is `config.yaml`.  It is currently setup to include anything in the `conf.d` directory.  This can be modified as needed.  It is recommended to put all customized configurations into `conf.d` instead of modifying the main config.yaml file.
