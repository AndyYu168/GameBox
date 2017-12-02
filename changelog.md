

--------------------------------------------------
v 1.5.11
- shorter name for long numbers
- fix "Unknown translation key" problem with protocol support
- fix title length check for 1.8 and added new check for DecoderException

v 1.5.10
- fixed wrong language on sound toggle
- shade HikariCP and slf4j for MySQL data storage
- updated comments in configuration file
- fix NPE in TopListPage because of unknown name of OfflinePlayer
- get rid of unnecessary Warnings because of not configured hot bar button materials
- short term changes for 1.x.x release:
  - commented out the shading of MySQL libraries
  - disabled internal MySQL usage and added logging messages to inform used about missing MySQL support 

v 1.5.9
- test whether server can handle long inventory titles instead of simply assuming it for all versions 1.9+

v 1.5.8
- merged #11 (update lang_zh-cn)
- configurable items as hotbar buttons (#13)
- handle players who are still in GUI or game on PlayerQuitEvent (#12)

v 1.5.7
- added flag and checks for too long inventory titles in 1.8
- add option to keep armor on when in GUI or a game #5

v 1.5.6
- remove '.' from huge number formatting when three zeros follow it
- upgrade bstats to 1.2
- mavenized
- fix cut of number formating at 9.223 quintillion (due to max value of long)
  - use CookieClicker 1.0.0 + to use the corrected method only

v 1.5.5
- added title length checks in AGui and in 1.8 nms utils
- fix top list score cut-off at highest integer
- new score type for number formatting "xxx.xxx million/billion..."
- moved NumberUtil to GameBox from CookieClicker

v 1.5.4
- precautionary added gameIDs and names to come for bStats
- updated spanish lang file (thank altrisi)
- Sounds for GUI configurable in config
- some internal restructuring (moved metrics class)

v 1.5.3
- thread safety for invites over chat
- more documentation in the default config for the left/entering GameBox listeners
- cleaned all imports

v1.5.2
- Add plugin metrics by bStats
  - possible opt out in the config
- fix picking up of items when in shop
- fix wrong player drops on death when in shop!
- add option to not close the inventory on damage
- add events called when player opens the GameBox and another event for players who just left the GameBox
  - the config provides the possibility to run commands on these events

v 1.5.1
- add nms for 1.12
- compatible with minecraft 1.12 now

v 1.5.0
- add help message for admin commands listing all the commands
- cleaned up shop system
- clean up GUI system
- cleaned up Settings system and main class
- removed one click action and simplified action processing
- fix NPE when player comes from disabled world and changes his token count
- improved handling of world changes
- add reload command and loading/unloading of registered games on reload


v 1.4.0:
- add option in config to keep items in certain slots in the hot bar
  - solves compatibility issues with plugins that require specific items in the players inventory
- add more options for the shop
  - distinguish between an item that is sold and the item that is displayed
  - sold item can now have custom display name/lore/glow
  - add requirements (player has to have permissions and not have other permissions)
  - dispatch commands when player buys
  - better default tokenShop.yml with examples showcasing all the possibilities
  - option for commands that manipulate the inventory (give commands and similar)
    - use with caution... this closes the inventory before executing the command and then reopens it
    - you have to handle a possibly full inventory yourself
    - better is to sell the item without using a command (build it with custom display name and lore)
- improved gui system
  - you should update games asap since they are using deprecated methods now
- added hook to PlaceholderAPI

v 1.3.1:
- added clickable invitation message
  - the message is configurable in the language files (14! new strings...)
  - click message can be opt out in the configuration file
- doubled the time in default config until an invite runs out
- added comments in the default config for invite timings
- corrected german lang file
- prevent players from picking up items into GUIs or games
  - The items are added to the saved inventory if there is enough space for them.


v 1.3.0:
- a few seconds after starting the plugin will now print messages to the console when no games where registered
- gamebox.admin only gives access to admin commands (use gamebox.* for all permissions)
- strip color on invite input to be compatible with chat color plugins (e.g. https://dev.bukkit.org/projects/chatcolor-s)
- Fixed 'gamebox.gamegui.(*/gameID)' perm with shortcut commands
- Added API
  - give/set/take token with API
  - get Number of tokens with API
- fixed wrong calculation in '/gb takeToken' for offline players
- internal improvements and restructuring of settings (deprecated methods will be removed later and all games have to be updated)
- fixed a bug where GameBox thought that a player was in the main gui after using the 'back to game' button while playing a game
- permission 'gamebox.use' now prevents any usage of the command /gamebox and its aliases and also prevents usage of the hub item
- play permission fixed for multiplayer games
- option to allow accepting of game invitations WITHOUT having the permission to play said game
- improved lang_de.yml
- updated mandarin lang file 'lang_zh-cn.yml'


v 1.2.0:
- printing warning and additional info in console if no NMS found for version
- added missing message to lang_de
- added info messages to lang_en and lang_de
- permission gamebox.info is now a default permission
- list all installed games and give tha shortcut commands for them on /gb info
- added /gbadmin oder /gba
  - permission gamebox.admin needed!
- saving name for UUIDs in data for easier manual management
- admin commands
  - /gba givetoken/taketoken/settoken player count
  - works with offline and online players as long as the player has played on the server before!

v 1.1.2:
- add spanish lang file
- close inventory on damage event!

v 1.1.1:
- improved default lang messages (en)
- player now drop their old inventory contents on death


v 1.0.0:
- removing drops on death if player in game/gui
- restoring inventory if game fails and second player was not in gui before
- added checks for second player being in gui before sending title messages
- added check for GBPlayer being loaded before removing on World change
- cleaned english lang file
- translated new german lang file
- standard message on receiving invitation (to be improved later on)