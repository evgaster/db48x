# Introduction

This is a very brief preliminary description of the Constants module,
a (partial) implementation of the constants functionality in rpl.

# Installation

The files of the module should be placed in `library/Modules/Constants`.
A section Modules should be added to`config/library.csv`.
In it, the module Constants should be added:
```
"Modules"
        "Constants",    "=/library/Modules/Constants/Initialise.48s"
```

# Activation

To load and initialise the Module Constants:
- 🟦 VAR (H = LIB) or the ```Library``` command,
- 🟨 F2 ( = Modules),
- F1 ( = Constants),

The above reads and evaluates `Initialise.48s`.
That bootstraps the rest of the module.
Eventualy it binds the top menu of the Constants Module to the same key as the regular constants menu,
but in Usermode.

# Use

To activate the top menu:
- 🟨 2 (Y = USER)
- 🟨 STK (I = CONST) 

The calculator shows (the top constants menu):

![Top menu](img/top-menu.png)

The menu is briefly described in the table below.
| Menu item | Description |
| :---: | --- |
| ~Name~ | Search the database for constants with a name that contains a string. Requires a string on the stack. |
| ~Desc~ | Search the database for constants with a (short) description that contains a string. Requires a string on the stack. |
| Astronomy | Activate the astronomy (navigation) (sub)menu. |
| Chemistry | Activate the chemistry section menu. |
| ... | Activate that (sub)menu. |

Suppose you are looking for a particular constant, you don't know its name,
but you know it is associated with the work of Max Planck.
Put "Planck" on the stack and activate the `~Desc~` button.
When the search completes, the calculator shows:

![Plank menu](img/plank-menu.png)

This is a constant selection menu with all the constants in the database which have "Planck" in the (short) description.
You can activate the menu button of any of the constants to work with that particular constant.
How to work with a particular constant is described below for the "NA" constant.

After activating the `Astronomy` menu button, in the top menu, the calculator shows:

![Top menu](img/astronomy-menu.png)

Like the top menu this is a navigation menu.
It shows menu items for several celestial bodies in the solar system and for a black star.
Each such menu item wil activate the menu for the corresponding constant section.

After activating the `Chemistry` menu button, in the top menu, the calculator shows (the chemistry constant section menu):

![Top menu](img/chemistry-menu.png)

The menu is briefly described in the table below.
| Menu item | Description |
| :---: | --- |
| ↓Navigate↓ | Move back down the menu tree (to the previous navigation menu).  |
| NA | Put "NA" on the stack and activate the menu for the NA constant |
| ... | Put the name of the constant on the stack and Activate the menu for that particular constant. |

After activating the `NA` menu button the calculator shows:

![NA menu](img/na-menu.png)

The menu is briefly described in the table below.
| Menu item | Description |
| :---: | --- |
| Descrip | Put the (short) description of the constant on the stack. |
| Help | Display the help information for the constant. |
| Value | Put the value of the constant on the stack.|
| StdUnc | Put the standard uncertainty of the constant on the stack. |
| RelUnc | Put the relative uncertainty of the constant on the stack. |
| ∆Range | Put the value and the standard uncertainty of the constant on the stack as a ∆Range. |
| Object | Put the databse object of the constant on the stack. |

Each of these pop the name of the constant from the stack.
After the action the section menu is shown again.

With "NA" on the stack, after activating the `Object` menu button the calculator shows:

![DataBase Object](img/database-object.png)

A TypeName = "list" object is put on the stack.
It contains the constants name, (short) description, value, standard and relative uncertainty. 

# De-activation

To unload the Module Constants ...

```
UpDirectory
{ ModuleConstant } Purge
```

# Maintenance

Very, very brief ...

To generate a Constants.db file, use Define.48s and Definitions.48s.

To compare the constants in the database with `constants.cc`, use Test.48s.

To modify a Constant, edit Definitions.48s.
Generate a new database and make it available.

To modify a Section, edit Section.db.

To modify a navigation menu, edit Menu.db.