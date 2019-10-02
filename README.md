# Ricer 🍚
![ricer](/ricer.gif)

I made this little script so that I'd be able to quickly switch between visual styles and colorschemes for my desktop.
It functions by substituting markers for color numbers in the base16 theming standard inside of files at `~/.config/ricer/ricertemplates` and copying them into their appropriate locations. It is also capable of using a different set of templates instead to change things other than color, these are stored as the configs that need to be different inside of a profile directory, say that you want the polybar config to be different in a certain profile, you would make a profile directory with the polybar config alone and activate that profile to apply it.

notice: at the moment this script is not able to handle multiple configs with the same filename, this will be fixed eventually.

## Usage

`ricer <colorscheme>` will load and apply a colorscheme in base16 .yaml format in the directory `~/.config/ricer/colors`
`ricer <profile>` will load and apply a profile inside of `~/.config/ricer/profiles`

for each config present in any profile the proper location for the config must be specified inside of `~/.config/ricer/confs` 

## colorschemes
colorschemes must be in base16 .yaml format, stored under `~/.config/ricer/colors` 

## profiles
profiles must be directories with configuration files stored inside of `~/.config/ricer/profiles/` 
