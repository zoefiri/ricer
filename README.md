# Ricer 🍚
![ricer](/ricer.gif)

I made this little script so that I'd be able to quickly switch between visual styles and colorschemes for my desktop.
It functions by substituting markers for color numbers in the base16 theming standard inside of files at `~/.config/ricer/ricertemplates` and copying them into their appropriate locations. It is also capable of using a different set of templates instead to change things other than color, these are stored as the configs that need to be different inside of a profile directory, say that you want the polybar config to be different in a certain profile, you would make a profile directory with the polybar config alone and activate that profile to apply it.

notice 1: backup your configs before using this, I take no responsibility if you accidentally lose them. This script WILL overwrite specified configuration files.

notice 2: at the moment this script is not able to handle multiple configs with the same filename, this will be fixed eventually but at the moment I have personally found that it is rarely an issue.

## Features
colorschemes + templates - ricer can use a colorscheme in the base16 .yaml format and apply it to special templates for configurations where instead of the actual colors being present, placeholders for colors are used

profiles - Color's not everything to the appearance of your desktop, so alternate profiles of configuration templates can quickly be swapped in and out and mixed and matched with colorschemes.

## Usage
`ricer <colorscheme>` will load and apply a colorscheme in base16 .yaml format in the directory `~/.config/ricer/colors`, you can find these at https://github.com/chriskempson/base16 

`ricer <profile>` will load and apply a profile inside of `~/.config/ricer/profiles`

for each config present in any profile the proper location for the config must be specified inside of `~/.config/ricer/confs` 

## colorschemes
colorschemes must be in base16 .yaml format, stored under `~/.config/ricer/colors`

before this script works 1 colorscheme and 1 profile must be loaded first, errors will be produced from this initially.

## profiles
profiles must be directories with configuration files stored inside of `~/.config/ricer/profiles/` 

before ricer copies them into place it will substitute @@C# with the according base16 colors, # being the base16 color number.

color 1 has a special marker to distinguish it from colors 10 thru 16, @@C1@@ 

## post commands
`~/.config/ricer/post` is an executable file, place commands to execute after running the script. e.x. reloading your window manager and other themed applications

## ricer configuration directory example
`ricer
├── colors
│  ├── mochamod.yaml
│  ├── pumpkin.yaml
│  ├── snazzycoal.yaml
│  ├── summercamp.yaml
│  └── summerd.yaml
├── confs
├── profiles
│  ├── halloween
│  │  ├── compton.conf
│  │  ├── config
│  │  ├── current
│  │  ├── current.yaml
│  │  ├── custom.rasi
│  │  ├── herbstluftwm
│  │  │  ├── autostart
│  │  │  ├── binds
│  │  │  ├── oldstart
│  │  │  ├── start
│  │  │  └── theme
│  │  ├── lemon
│  │  ├── oomox
│  │  ├── palcolors
│  │  ├── testc
│  │  └── userChrome.css
│  └── roundHalloween
│     ├── compton.conf
│     ├── config
│     ├── current
│     ├── current.yaml
│     ├── custom.rasi
│     ├── herbstluftwm
│     │  ├── autostart
│     │  ├── binds
│     │  ├── oldstart
│     │  ├── start
│     │  └── theme
│     ├── lemon
│     ├── oomox
│     ├── palcolors
│     ├── testc
│     └── userChrome.css
└── ricertemplates
   ├── colors
   │  ├── base0
   │  ├── base1
   │  ├── base2
   │  ├── base3
   │  ├── base4
   │  ├── base5
   │  ├── base6
   │  ├── base7
   │  ├── base8
   │  ├── base9
   │  ├── base10
   │  ├── base11
   │  ├── base12
   │  ├── base13
   │  ├── base14
   │  └── base15
   ├── compton.conf
   ├── config
   ├── herbstluftwm
   │  ├── autostart
   │  ├── binds
   │  ├── oldstart
   │  ├── start
   │  └── theme
   ├── lemon
   └── userChrome.css
` 
