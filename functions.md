# Functions
* [sendPacket](#sendpacket)
* [sendPacketRaw](#sendpacketraw)
* [sendVarlist](#sendpacketraw)
* [findPath](#findpath)
* [getLocal](#getlocal)
* [getInventory](#getinventory)
* [getPlayers](#getplayers)
* [getObjects](#getobjects)
* [getTile](#gettile)
* [getTiles](#gettiles)
* [getItemInfo](#getiteminfo)
* [isSolid](#issolid)
* [isSeed](#isseed)
* [canHarvest](#canharvest)
* [placeTile](#placetile)
* [hitTile](#hittile)
* [wrenchTile](#wrenchtile)
* [warp](#warp)
* [setPos](#setpos)
* [say](#say)
* [runThread](#runthread)
* [collectObject](#collectobject)
* [inWorld](#inworld)
* [useDoor](#usedoor)
* [itemExist](#itemexist)
* [isInside](#isinside)
* [log](#log)

## sendPacket
`sendPacket(bool client,string packet, int type)`

Sends text packet with selected type to server .

Example:
```lua
-- Sends respawn packet to server
sendPacket(false,"action|respawn", 2)
```

## sendPacketRaw
`sendPacketRaw(bool client,GamePacket packet,bool client)`

Sends [GamePacket](Structs.md#gamepacket) to server

Example:
```lua
-- Sends wear clothing packet to server
packet = {}
packet.type = 10 
packet.int_data = 48 -- Clothing ID (Jeans)
sendPacketRaw(false,packet)-- Sends to server.
```
## sendVarlist
`sendVarlist(variantlist_t& list)`

Sends [variantlist_t](Structs.md#variantlist_t)

```lua
-- Sends OnConsoleMessage to clients.
varlist = {}
varlist[0] = "OnConsoleMessage"
varlist[1] = "hi!!"
sendVarlist(varlist)
```

## findPath
`findPath(int x, int y)`

Finds path to selected x,y

Example:
```lua
-- Finds path to top left corner of the world
findPath(0, 0)
```

## getLocal
`getLocal()`

Returns local [NetAvatar](#Structs.md#netavatar)

Example:
```lua
-- Logs local players name
me = getLocal()
log(me.name)
```

## getInventory
`getInventory()`

Returns table of [InventoryItems](Structs.md#inventoryitem)

Example:
```lua
-- Logs all item ids in your inventory
for _,cur in pairs(getInventory()) do
log(cur.id)
end
```

## getPlayers
`getPlayers()`

Returns table of [NetAvatar](Structs.md#netavatar)

Example:
```lua
-- Logs current worlds players names
for _,player in pairs(getPlayers()) do
log(player.name)
end
```

## getObjects
`getObjects()`

Returns table of [WorldObjects](Structs.md#worldobject)

Example:
```lua
-- Logs current worlds objects item id's
for _,object in pairs(getObjects()) do
log(object.id)
end
```

## getTile
`getTile(int x, int y)`

Returns world [Tile](Structs.md#tile) in selected position

Example:
```lua
-- Logs top left corners foreground block id
tile = getTile(0, 0)
log(tile.header.fg)
```

## getTiles
`getTiles()`

Returns table of [Tiles](Structs.md#tile)

Example:
```lua
-- Logs current worlds all foreground block id's
for _,tile in pairs(getTiles()) do
log(tile.header.fg)
end
```

## getItemInfo
`getItemInfo(int itemid)`

Returns [ItemInfo](Structs.md#iteminfo) of selected Item ID

Example:
```lua
-- Logs Item ID 2's name (Dirt)
log(getItemInfo(2).name)
```

## isSolid
`isSolid(int x, int y)`

Returns true if block is solid and false if its not

Example:
```lua
if isSolid(0, 0) then
log("Tile 0, 0 is solid")
else
log("Tile 0, 0 is not solid")
end
```

## isSeed
`isSeed(int x, int y)`

Returns true if tile is seed , false if its not

Example:
```lua
if isSeed(0, 0) then
log("Tile 0, 0 is Seed")
else
log("Tile 0, 0 is not Seed")
end
```

## canHarvest
`canHarvest(int x, int y)`
Returns true if tile is harvestable , false if  not

Example:
```lua
if canHarvest(0, 0) then
log("Tile 0, 0 is harvestable")
else
log("Tile 0, 0 is not harvestable")
end
```


## hitTile
`hitTile(int x, int y)`

Send Punch Packet To X,Y

Example:
```lua
---Punch To 0,0
hitTile(0,0)

```

## wrenchTile
`wrenchTile(int x, int y)`

Send Wrench Packet To x,y

Example:
```lua
---Wrench To 0,0

wrenchTile(0,0)

```

## placeTile
`placeTile(int tile,int x,int y,bool client)`

Place Block To x,y

Example:
```lua
---Place Dirt To 0,0
placeTile(2,0,0,false)

```

## warp
`warp(string x)`

warp To x

Example:
```lua
warp("BUYGHC")

```

## setPos
`setPos(int x,int y)`

Example:
```lua
--- Sets bot position
setPos(0,0)
```
## say
`say(string text)`

Example:
```lua
-- Send chat message
say("Hello")
```

## runThread
`runThread(function() 
//code here
end)`

Example:
```lua
runThread(function()
while true do
log("New Thread")
end
end)

while true do
log("Normal Thread")
end
```
## isInside
`isInside(int x,int y,int rad)`

Example:
```lua
if isInside(0, 0,5) then
log("x 0, y 0 is in inside")
else
log("x 0, y 0 is not inside")
end
```

## collectObject
`collectObject(int uid)`

Example:
```lua
-- Collecting Object With UID
collectObject(0)
```
## inWorld
`inWorld()`

Example:
```lua
if inWorld() then
log("in world")
else
log("not in world")
end
```

## itemExist
`itemExist(int itemid)`

Example:
```lua
if itemExist(2) then
log("Dirt Exist In Inventory")
else
log("Dirt Not Exist In Inventory")
end
```

## useDoor
`useDoor(int x,int y)`

Example:
```lua
useDoor(0,0)
```

## log
`log(arg)`

Print to Growtopia console

Example:
```lua
log("hello")
log(111)
log(true)
```
