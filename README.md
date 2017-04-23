# solus-wine-gaming-nine

This intends to be a `wine-staging` patched up just like the `wine-gaming-nine` provided in arch's [AUR](https://aur.archlinux.org/packages/wine-gaming-nine/).

## Why?

`wine-staging` provides certain enhancements that make it possible to run some games. One example of this is `Doom 2016`.
Other patches included in `wine-gaming-nine` provide better compatibility for steam and performance improvements (not `gallium-nine` related).

## For Whom?

`Gallium-nine` will only work if the game runs on `d3d9` and can only be used with open source drivers. So, this is for:


+ Solus Linux users.

+ Those wanting to run `directx9` games on wine.

+ Those using open source drivers 

    More useful for `radeon`/`amdgpu` users though, `nouveau` users will probably get more performance with proprietary drivers and `wine-staging`

### Disclaimer

You use this at your own risk.
I do not have the knowledge nor the time to make a perfect adaptation of the `wine-gaming-nine` package, so you may find errors. All contributions are welcome.

### How to install

You should know that, at least for now, this packages will **replace** your system wine. You shouldn't worry about that as it should be easy to rever (check `How to uninstall` section).

There are actually 3 ways to install this package:

##### Download and install packages from `releases` section

Get the packages from [here](https://github.com/phinicota/solus-wine-gaming-nine/releases) and then:

    sudo eopkg it ~/Downloads/wine*.eopkg

**Note: you need to use relative dirs.


##### Compile it yourself

You will probably need to install `system.devel` doing: `sudo eopkg it -c system.devel`

    git clone https://github.com/phinicota/solus-wine-gaming-nine --depth 1
    cd solus-wine-gaming-nine
    ykpg package.yml
    sudo eopkg it wine*.eopkg
    
##### Compile it yourself - without cloning -
###### *not working yet, possible fixes welcome*

    sudo eopkg bi --ignore-safety https://github.com/phinicota/solus-wine-gaming-nine/blob/master/pspec_x86_64.xml

### How to uninstall

You need to uninstall `wine` package:

    sudo eopkg remove wine

Afterwards, if you want to fallback to Solus repository version of wine:

    sudo eopkg it wine
