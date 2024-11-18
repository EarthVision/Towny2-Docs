# Towny2-Docs (Wip)
New towny Guide :)


## [Town management]
for all /town commands you can use /t as an alias, eg /t create [name], /t claim, /t unclaim etc


#### /town [townname]
Displays information about the player's town or other towns if specifying town name, including the town name, PVP status, board message, mayor, founding date, balance, town size, homeblock, outposts, flag statuses, residents, and trusted players.

#### /town create [name]
Creates a new town with the specified name and claims the current chunk as the homeblock, town creation costs money (configured in the plugin's config).

### /town online [name]
Displays the amount of line players in your town or a specific town.

### Claiming and Unclaiming
#### /town claim
Claims the chunk the player is standing in for their town, can only claim chunks adjacent to an existing claim. (only usable by town mayor)

#### /town unclaim
Unclaims the chunk the player is standing in (only usable by town mayor or plot owner).

#### /town claim outpost 
Claims the chunk the player is standing in as an outpost for their town. you can use this to claim chunks not adjacent to your town (only usable by town mayor)

#### /town autoclaim on/off
Enables or disables the autoclaim feature for the player's town, which automatically claims chunks when the player moves to them. (only usable by town mayor)

#### /town autounclaim on/off
Enables or disables the autounclaim feature for the player's town, which automatically unclaims your towns chunks when the player moves to them. (only usable by town mayor)

### Inviting, leaving and kicking players

#### /town invite/add [player]
Invites a player to the town (only usable by town mayor)

#### /accept [townName]
Accepts an invitation to join the specified town.

#### /town leave
Leaves the player's current town (only usable by town members).

#### /town kick [player]
Kicks the specified player from the player's town (only usable by town mayors).

### Outposts
#### /town outpost [number] 
Teleports the player to the specified outpost.
#### /town outpost list [page] 
Lists the town's outposts, with an optional page number.

### misc (to be organized]
#### /plot set name [name] 
Sets the name of the plot (chunk) the player is standing in.
#### /plot clearname
Removes the custom name from a plot.
#### /town deposit [amount]
Deposits the specified amount of money from the player's balance into the town's balance.
#### /town withdraw [amount]
Withdraws the specified amount of money from the town's balance into the player's balance.


#### /town delete
Initiates the town deletion process and prompts for confirmation.
#### /town delete confirm/deny
Confirms or denys the town deletion process.

#### /town rename [newName]
Renames the player's town to the specified new name.

#### /town set board [message] 
Sets the town's board message.
#### /town set spawn
Sets the town's spawn location to the player's current location.

#### /town set taxes
Sets the town's daily taxes.

#### /town set mapcolor [color]/[hexcode]
Sets the towns color on dynmap, can use built in colors or you can specify your own hexcode for a specific color

## [Modifying permissions in your Town]
heres how you can modify permissions for resident and other custom roles you create in your town

you can use /t perm and /plot perm to easily manage town role permissions and flags with a gui



### Creating and assigning custom roles


#### /town rank create [rolename] 
Creates a new custom role in the town.
#### /town rank assign [player] [role]
Assigns the specified role to the given player in the town.
#### /town rank revoke [player] [role] (not yet implemented)
removes the players role and assigns them resident.
#### /town rank delete [role] 
Deletes the specified role from the town.



### Modifying role permissions
#### you can also perform all the actions inside the /plot perm and /t perm menus with commands



#### /town perm
Opens the permissions menu for the players town, modifies rank perms, flags and trust across the entire town. (usable by town mayor)


#### /plot perm
similer to /town perm menu but only modifies rank perms, flags and trust for that individual chunk (usable by town mayor and plot owner)


#### /town perm add/remove [role] break/build/switch/itemuse
Adds or removes the specified flag permission for the given role in the player's town. (usable by town mayor)

#### /plot perm add/remove [role] break/build/switch/itemuse
Adds or removes the specified flag permission for the given role in the chunk the player is standing in. (usable by town mayor or plot owner)


### allowing roles to perfomr certain commands

#### /town role command add/remove [role] [command]
you can give roles in your town access to certain commands, for example allowing residents to claim land:
`/town add command add resident town_claim` will allow residents to claim land


### Available Command Permissions
 using `/town role command add/remove [role] [command]`:

- TOWN_CLAIM - Allow claiming land for the town
- TOWN_UNCLAIM - Allow unclaiming town land
- TOWN_KICK - Allow kicking residents from the town
- TOWN_DELETE - Allow deleting the town
- TOWN_ROLE_CREATE - Allow creating new ranks
- TOWN_ROLE_ASSIGN - Allow assigning ranks to residents
- TOWN_ROLE_DELETE - Allow deleting ranks
- TOWN_INVITE - Allow inviting new residents
- TOWN_RENAME - Allow renaming the town
- TOWN_WITHDRAW - Allow withdrawing from town bank
- TOWN_TRUST - Allow managing town-wide trust
- TOWN_TOGGLE - Allow toggling town flags
- TOWN_SET_BOARD - Allow setting town board
- TOWN_SET_SPAWN - Allow setting town spawn
- TOWN_SET_HOMEBLOCK - Allow setting town homeblock
- TOWN_SET_TAXES - Allow setting town tax rate
- TOWN_SET_MAPCOLOR - Allow setting town color on dynmap
- PLOT_TOGGLE - Allow toggling plot flags
- PLOT_SET_NAME - Allow setting plot names
- PLOT_TRUST - Allow managing plot trust
- PLOT_PERM - Allow managing plot permissions
- PLOT_EVICT - Allow evicting plot renters

### Modifying town flags
modifying flags like pvp, mobs, explosions across the whole town or individual plot


#### /town toggle pvp/mobs/explosions/fire
Toggles the specified flag (e.g., PVP, MOBS, EXPLOSIONS, FIRE) for the entire town.(usable by town mayor)

#### /plot toggle pvp/mobs/explosions/fire
Toggles the specified flag (e.g., PVP, MOBS, EXPLOSIONS, FIRE) for the chunk the player is standing in.(usable by town mayor and plot owner)


## [Selling, buying and renting plots]
There are 2 ways to sell/rent a plot, private sale and public sale, private sale basically just means only town residents can buy/rent the plot, public sale means anybody, even players without a town can buy/rent the plot.

purchased plots will still be claimed and owned by the plot owner even after the orig town is deleted, rented plots will be deleted with the parent town.

#### /plot claim
Purchases a plot (chunk) that is for sale or rent if the player has enough funds.

#### /plot evict
Evicts the current renter from a plot. Can be used by the town mayor or plot owner.

#### /plot nfs
Removes the plot (chunk) the player is standing in from being for sale. (usable by mayor or plot owner)

### Selling
Sold plots are completely owned by the buyer. The town mayor or seller cant evict you and you can modify all the permissions and flags and add or remove trust in the chunk after purchase.

money from sold plots goes into the town bank if sold by a town, and into your player account if you sell a plot you own



#### /plot fs [price]
Sets the plot (chunk) the player is standing in for sale at the specified price. (usable by town mayor) (only town residents can buy)
#### /plot fsp [price]
Sets the plot (chunk) the player is standing in for sale publicly at the specified price. (usable by town mayor or current plot owner) (anyone can buy, even players without a town)
if you want to sell player owned plots you have to use /plot fsp



### Renting
when renting a plot, mayor or the plot owner can evict you, rent is automatically withdrawn from your player account daily(every 24h). 
If you have no money and rent isnt paid an owing balance will build and after 1 week will be auto evicted if the mayor has set autoevict to true

#### /plot fr [amount]
Sets the plot for rent (only towns residents can rent it)

#### /plot frp [amount]
Sets the plot (chunk) the player is standing in for rent as public(anybody can rent it, even players not in a town). (usable by town mayor or current plot owner).

### etc

#### /town set homeblock
Sets the town's homeblock to the current chunk. The homeblock is the central chunk of your town and cannot be unclaimed. Town spawn must be set within the homeblock.

#### /town set taxes [amount]
Sets the tax rate for town residents. Taxes are collected daily as a percentage of each resident's balance.

#### /town reclaim
If a town has fallen into ruins (due to bankruptcy), the mayor can use this command to reclaim the town once sufficient funds have been deposited.



## [Trust]
you can use trust to easily give players outside your town or owned plot access to your town or owned plots

you can use /town perm and /plot perm to easily view and manage trust permissions in a gui

### basic trust
#### /town trust add/remove [player]
Grants/removes the specified player trust permissions in all chunks of the town. (usable by town mayor)


#### /plot trust add/remove [player]:
Grants/removes the specified player trust permissions in the chunk the player is standing in. (usable by town mayor or current plot owner)

### Advanced trust
you can also give players trust permissions for only specific perms, for example if you want to only allow a player to access chests but not break blocks or build, you can use "/plot trust add [player] switch"

#### /town trust add/remove [player] break/build/switch/itemuse
Grants/removes the specified player's trust permissions for the specified flag in all chunks of the town. (usable by town mayor)


#### /plot trust add/remove [player] break/build/switch/itemuse 
Grants/removes the specified player's permissions for the specified flag in the chunk the player is standing in. (usable by town mayor or current plot renter)

# Nations


#### /nation
Displays information about your current nation, including the nation name, board message, leader, founding date, and bank balance.

#### /nation [nationname]
Displays information about the specified nation.

#### /nation create [name]
Creates a new nation with your town as the capital.

#### /nation list [page]
Lists all nations on the server with their resident counts. Optional page number for pagination.

#### /nation ally (wip)


#### /nation enemy (wip)

