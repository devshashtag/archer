# Archer
a simple script that helps you to install and config you'r **packages**, **bootloader**, ...


# features
- debug mode
- local pacman packages support `/var/cache/pacman/pkg`

**TODO: i'll add all features soon**


# warning
- if you'r not a **professional arch user**, please **DO NOT USE** Archer

- you have to create you'r partitions before running Archer


# options
![alt text](https://github.com/devshashtag/archer/blob/main/screenshots/help.png?raw=true)


# how to load config
i created 3 config examples under `archer/config` folder:

- awesome-pc-config
- default-config
- xfce-pc-config

*Archer loads `xfce-pc-config` by default*

you can change default config permanently in **Archer** script using `config_path` variable 

or use `-c` option: `./archer -b -c "path/to/file-config"`


# how to config
config file uses a bash like syntax that will be converted to bash variables later

NOTE: **use comments like you'r using them in bash scripts**

1) Archer, user options:

```bash
options = {
  username: "yourName"
  hostname: "yourHostName" 

  lightdm_session: "xfce" # set default session that lightdm can load you'r desktop or window manager
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


2) partition management:

you have to create you'r partitions before running Archer

and then define you'r partitions here:

```bash
partitions = {
  # defines which partition to install grub on
  grub_install: "/dev/sda"

  # root partition
  root_part: "/dev/sda2"
  root_mount: "/mnt"
  root_fmt: "mkfs.ext4"

  # i dont use home - instead i use a DATA partition
  # home
  # home_part: "/dev/sda5"
  # home_mount: "/mnt/home"
  # home_fmt: "mkfs.ext4"

  # swap
  swap_part: "/dev/sda3"
  swap_fmt: "mkswap"

  # TODO: required uefi support
  # uefi_part: "/dev/sda4"
  # uefi_mount: "/boot/efi"
  # uefi_fmt: "mkfs.vfat -F32"


  # you can add any partition that you want here
  # just follow the syntax and Archer detect you'r new partition here

  # name_part: "/dev/sdaX"  # which partition
  # name_mount: "/mnt/path" # where to mount
  # name_fmt: "mkfs.ext4"   # command for formating this partition
}
```


3) package management:

Archer uses 3 arrays for manage packages:

```
core_packages        - archer install these packages in base section (using pacstrap)
system_packages      - archer install these packages in system section (using pacman)
application_packages - archer install these packages in system section (using pacman)
```

**packages titles** doesn't matter for Archer:

![alt text](https://github.com/devshashtag/archer/blob/main/screenshots/base_packages.png?raw=true)

you can change `editor` to anything you want like: `my_editor`

archer only use these titles to display **packages titles**:

![alt text](https://github.com/devshashtag/archer/blob/main/screenshots/packages.png?raw=true)

and removes spaces inside these arrays.

if you'r `display_cmd` or `debug` options is `true` archer **displays commands** before **running**:

![alt text](https://github.com/devshashtag/archer/blob/main/screenshots/base_packages_display_cmd.png?raw=true)


TODO: **I'LL ADD MORE INFORMATION ABOUT ARCHER LATER**
