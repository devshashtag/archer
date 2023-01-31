# Archer
a simple script that helps you to install and config you'r **packages**, **bootloader**, ...


# features
- debug mode
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


# how to config
config file uses a bash like syntax that will be converted to bash variables later

1) we have to define options first:

```bash
options = {
  username: "yourName"
  hostname: "yourHostName" 

  lightdm_session: "xfce" # set default session that lightdm can load your desktop or window manager
  default_shell: "fish"   # set default shell for this user

  # local pacman cache 
  cache: "false"          # if you have any pacman packages caches set this option to true
  cache_path: "pkg"       # set packages folder

  # if you set this option to ture archer only displays commands
  # another way is to use -d options like: ./archer -d -b
  debug: "false"


  # if you set this option to ture archer displays commands, and then runs
  display_cmd: "true"
}
```



