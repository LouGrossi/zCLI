# zCLI :: a CLI framework written in zsh

```text
           .d8888b. 888      8888888 
         d88P  Y88b 888        888   
         888    888 888        888   
 .d88b.  888        888        888   
d8P  Y8b 888        888        888   
88888888 888    888 888        888   
Y8b.     Y88b  d88P 888        888   
 "Y8888   "Y8888P"  88888888 8888888 
                                                                       
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

## Help Files

Upon error the cli will look for a file named `help-${VERB}` in the resource directory.
If it can't find one it will then look for `help` in that directory.
If it can't find that it will move backwards through the directory structure looking for the filename `help` and display that before exiting.

## Configuration Files
###  ..WiP.. 

The main configuration file is `config.yaml`.  It is currently setup to include anything in the `conf.d` directory.  This can be modified as needed.  It is recommended to put all customized configurations into `conf.d` instead of modifying the main config.yaml file.

## Contributing

**First, please contribute.**

**Here are the basics:**

- NEVER put any credentials or API keys into the repo
  - make use of the .gitignore file
  - if you hae something you need to put in you can make a template (see config.yaml example)
- each feature should have have a branch
- you should submit pull requests to merge into main
- follow the format, the executable at the end of the arguments does a single thing
  - for example: ./ecli google groups list # only lists the groups
  - we would pipe or use that output to perform the next action
  - keeping it modular helps a lot with reusability
- your executable can be in any language
  - if it can be assigned executable status, as long as it can be run directly form the terminal
- make sure to `chmod +x` your file before commiting
  - git will preserve that permission, and it will work when someone pulls the repo
  - if you forgot you'll get a "permission denied" error when you execute the command
