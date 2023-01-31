# Archer
a simple script that helps you to install and config you'r **packages**, **bootloader**, ...

# features
- debug mode
- configurable
- local pacman packages support `/var/cache/pacman/pkg`

**TODO: i will add all features soon**

# warning
**if you'r not a professionals arch users, please dont use this script**


# options
![alt text](https://github.com/devshashtag/archer/blob/main/screenshots/help.png?raw=true)

# how to load config

i created 3 config examples under `archer/config` folder:

- awesome-pc-config
- default-config
- xfce-pc-config

*this script loads a `xfce-pc-config` by default*

you can change default config permanently in **Archer** script using `config_path` variable 

or use -c option: `./archer -b -c "path/to/file-config"`

