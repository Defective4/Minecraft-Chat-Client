# Another Minecraft Chat Client
![license](https://img.shields.io/github/license/Defective4/Minecraft-Chat-Client)
![version](https://img.shields.io/github/v/release/Defective4/Minecraft-Chat-Client)
![lastCommit](https://img.shields.io/github/last-commit/Defective4/Minecraft-Chat-Client)
![version](https://img.shields.io/badge/latest_version-1.16.5-success)


AMCC is a GUI application that lets you join a Minecraft server and chat freely without opening your Minecraft game.

## Main features
* 📖 Complete GUI with Minecraft styled server list, in-game player list with skins and a tabbed pane allowing you to chat on multiple clients.
* 🎨 Minecraft style UI elements, such as chat font (Minecraftia), configurable buttons and text fields.
* 📋 Tray support.
* ⚙️ My own lightweight implementation of Minecraft protocol, supporting versions 1.8 to 1.16.5.
* 📦 Basic inventory handling and item using.

## 📙 My goals
This project is my take on implementing Minecraft's protocol from scratch.<br>
It started as a simple command line chat client and was quickly wrapped in a GUI.<br>
Now my main goal is to implement as many features from Minecraft's original protocol as I can
without using any other third-party libraries.

## 📦 Inventory handling
⚠️ **Caution** If you have a `mcc.prefs` file from version v1.1.0 or older and you want to use inventory handling make sure to first enable it in settings!<br><br>
Inventory handling is an experimental, yet useful feature, that allows you to manage items in your/remote inventory.
It was added in pre-release v1.1.0

### 🔌 What you can do with it
* Interact with server through a GUI. For example if server you connect to is a lobby server, and it opens a
  window for you to choose a game mode, you can simply click on an item in window like in normal Minecraft client.
* Use your own inventory, that includes:
    * Using items in hotbar (eating food, potions, using shield, etc.)
    * Organizing items by shift-clicking them (with second hand support)
    * Wearing armor
    * Dropping items
 
### ❓ How to use
When you are in a window opened by server, you have 3 options:
  * You can simply click on an item. It will act as a normal left click performed by client.<br>
    Be cautious, as if you click an item in NORMAL opened inventory (enderchest for example), it will be DROPPED when you close that inventory!<br><br>
  * Right click on item and select "Shift click". It will perform shift-click on selected item, and when done in normal window, it will take
    clicked item to your inventory.<br><br>
  * Right click and select "Drop". This will instantly drop selected item.

In your player inventory you have more control over items:
  * After left-clicking on an item in hotbar, client will change its hand to selected slot and will try to use item in it.
  * Right-click menu allows you to do the following things:<br><br>
   **In the whole inventory**:<br>
   * "Shift click" - performs a shift-click on selected item
   * "Drop" - will drop the item instantly<br><br>
   **In hotbar (the last 9 slots on the bottom)**:<br>
   * "Set slot" - will change client's held slot to selected item
   * "Use" - will chane client's held slot and use selected item. For example if you select food, it will be eaten.
   * "Stop using" - will stop client from using current item. For example you charged a bow, it will be shot.
   * "Swap items in hand" - will swap items in selected slot and your second hand.
   
### 🔥 Bugs
These are bugs I that are to be solved in future releases:
  * Items in versions higher than 1.12.2 may not always display properly. They will have names and textures of other item.<br>
    I am not sure what causes this yet<br><br>
  * Every "shift click" and "drop" action relies on Confirm Transaction packets sent from server.<br>
    If server responds to client's action, affected item will be updated in GUI, otherwise it won't.<br>
    It is to ensure that client's inventory stays in sync with server version of it, but ironically it may cause sync issues if server does  
    NOT send Confirm Transaction packets.<br>
    In case you notice that your inventory is not synchronized with server, try to reconnect your client.<br>
    
If you encounter a bug that disconnects your client or breaks it in a way that it is hard to use, you can disable inventory handling system in settings.

## 📓 Translations
Since v1.2.0 most of client's GUI and messages can now be translated to other languages.

### 📖 I want to translate!
If you want to translate AMCC to your own language, take [this file](https://raw.githubusercontent.com/Defective4/Another-Minecraft-Chat-Client/master/src/resources/lang/EN.properties), translate every line in it (or at least most of them), rename it to match the code of your language (for example PL.properties), open a new issue with label `translation`, and attach your file in it.<br>
If you done everything correctly, your translation will probably be added in next release, and I will give you a credit in section below.

### Current translations
  * English - Defective4
  * Polish - Defective4

## ⬇️ Downloads
You can download latest executable version [Here](https://github.com/Defective4/Minecraft-Chat-Client/releases)

## ✔️ List to do
- [x] Player list support
  - [x] Player skins
  - [ ] Exporting player skins
- [x] LAN games
- [x] Basic player actions (sneaking, sprinting)
- [x] Health updates and automatical respawning
- [x] Appearance settings
- [x] Movement
- [x] Statistics (1.8 - 1.12.2)
- [x] Inventory handling (experimental)
- [ ] Tab completion
- [ ] Usage statistics
- [ ] Graphical map with entity rendering
- [ ] Plugins
