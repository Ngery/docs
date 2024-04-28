------------------------------

--------[BOT FUNCTIONS]-------

------------------------------
info = {}
info.user = "user" 
info.pass = "pass" 
info.proxy = "ip:port:user:pass"
info.requestedName = "SmileZero"
info.mac = "mac"
info.rid = "rid"
info.hash = "hash"
info.flag = "us" --flag examples us / id / tr etc.

addBot(info[table]) --adds bot to app
Note: if you don't use info.pass then guest account will be enabled."
------------------------------
updateBot(info[table]) --same table as addBot. This is for updating bot after adding it
------------------------------
removeBot(user[string] or index[integer] or just local bot) --remove target bot from app 

Example Usage;
removeBot() --remove the selected bot
removeBot(getBot():getInfo().user) --remove bot by target username
removeBot(getBot().index) --remove bot by target index
------------------------------
sendPacket(type[integer], text[string]) --sends game packet
Note: app automaticly adds "\n" to packet. If you want to disable "\n" then use sendPacket(2, "action", false)
------------------------------
pkt = {}
pkt.type --0
pkt.netid --4
pkt.flags --12
pkt.int_data --20
pkt.pos_x --24
pkt.pos_y --28
pkt.pos2_x --32
pkt.pos2_y --36
pkt.int_x --44
pkt.int_y --48

sendPacketRaw(pkt[table]) --sends game packet with target table
------------------------------
connect() --sends connect request to game server
------------------------------
disconnect() --sends disconnect to game server
------------------------------
punch(x[integer], y[integer], animation[boolean]) --sends punch to specific x and y

Example Usage;
punch(1, 0) -- Bot will send punch to 1 block right.
punch(-1, 0) -- Bot will send punch to 1 block left.
punch(0, -1) -- Bot will send punch to 1 block up.
punch(0, 1) -- Bot will send punch to 1 block down.
Note: To use animation punch(1, 0, true) --animation is optional and default is false
------------------------------
place(itemid[integer], x[integer], y[integer], animation[boolean]) --send place specific item with specific x and y.

Example Usage;
place(2, 1, 0) -- Bot will place dirt block to 1 block right.
Note: To use animation place(2, 1, 0, true) --animation is optional and default is false
------------------------------
wrench(x[integer], y[integer]) --send wrench to specific x and y (same position style with punch & place)
------------------------------
collect(range[integer], itemid[integer or table], collect or ignore[boolean = false]) --returns true if collect packet is sent and false if it isn't 
collect(1) --collect everything in 1 range
collect(1,112,false) --collect everything except gems in 1 range
collect(1,112,true) --collect only gems in 1 range
Note: You can use array and collect multiple objects or ignore multiple objects for example; collect(1, {2, 3}, true) --only collect dirt block and dirt seed. 
------------------------------
drop(id[integer], count[integer], delay[integer = 1000]) --drop specific item with count & delay (both are optional you dont have to use)
trash(id[integer], count[integer], delay[integer = 1000]) --trash specific item

Example Usage;
drop(2, 0, 2000) --drop all of dirt in inventory with 2 seconds delay
trash(2, 0, 2000) --trash all of dirt in inventory with 2 seconds delay
Note: if you dont use any delay then app gonna use default delay = 1 second(1000ms)
Note: if you want to make bot drop & trash all with optional delay then set count to 0
------------------------------
say(text[string]) --send message to game chat
------------------------------
move(x[integer], y[integer])

Example Usage;
move(1, 0) --bot will move 1 block to right.
move(-1, 0) --bot will move 1 block to left.
move(0, -1) --bot will move 1 block to up.
move(0, 1) --bot will move 1 block to down.
move(0, 0, "left") --bot will turn to left
move(0, 0, "right") --bot will turn to right
------------------------------
wear(itemid[integer]) --sends wear packet with target itemid(type: integer) 
Example Usage;

wear(48) --bot will wear jeans.
wear(242) --bot will transform wls to dl.
------------------------------
warp(world[string]) --sends join packet to target world
------------------------------
isWorn(itemid[integer]) --returns true if the item is already worn and false otherwise

Example Usage;
if isWorn(48) then
	say("Im already wearing jeans!")
else
	say("Im not wearing jeans!")
end
------------------------------
findItem(itemid[integer]) --returns the amount of the target item that bot has in inventory

Example Usage;
say(findItem(112)) --bot will type how many gems that it has
------------------------------
findPath(x[integer], y[integer]) --bot will teleport to target tile if there is available path(returns true if it can and returns false otherwise)

Example Usage;
findPath(25,20) --bot will move to target tile with x:25 y:20
------------------------------
canFindPath(x[integer], y[integer]) --returns boolean if bot can findPath to target position then true otherwise false
------------------------------
getPlayers() --returns the table of players in world

player.name
player.netid
player.userid
player.country
player.isLocal --returns true if its local bot
player.x
player.y

Example Usage;
for _, player in ipairs(getPlayers()) do
	if player.name == "user" then
		print("Player user has been found in world!")
	end
end
------------------------------
getInventory() --returns the table of bot's inventory

inventory.slots
inventory.emptySlots
inventory.items --returns the inventory item's table

item.id
item.count

Example Usage;
for _, item in ipairs(getInventory().items) do
	print("id: "..item.id.." count: "..item.count)
end
------------------------------
getObjects() --returns the table of floating items in world

object.id --item id of object
object.x --position x of object
object.y --position y of object
object.count --item amount of object
object.oid --id of object

Example Usage;
for _, object in ipairs(getObjects()) do
	print("id: "..object.id.." count: "..object.count)
end
------------------------------
getTile(x[integer], y[integer]) --returns the table of target tile

tile.fg --returns the foreground of target tile
tile.bg --returns the background of target tile
tile.x --returns the x position of target tile
tile.y --returns the y position of target tile
tile.flags_1 --returns the first flag of tile
tile.flags_2 --returns the flag of tile(for water / fire etc check)
tile.isReady() [boolean] --returns true if tile is ready to harvest

tile.getExtra() [table] -- --returns the table of tile's extra data
extra.label --get the text from doors / signs etc
extra.isActive --for jammer / lamp etc check
extra.fruitCount --tree's fruit amount
extra.itemid --get item id inside of vend
extra.price --get vend price etc

Example Usage;
if getTile(10,23).isReady() then
	print("You can harvest target tile!")
end
------------------------------
getTiles() --returns the table of all tiles in world

tile.fg --returns the foreground of tile
tile.bg --returns the background of tile
tile.x --returns the x position of tile
tile.y --returns the y position of tile
tile.flags_1 --returns the first flag of tile
tile.flags_2 --returns the flag of tile(for water / fire etc check)
tile.isReady() [boolean] --returns true if tile is ready to harvest
tile.getExtra() [table] --returns the table of tile's extra data

Example Usages;
for _, tile in ipairs(getTiles()) do
	if tile.fg == 242 then
		print("Found world lock at: "..tile.x..","..tile.y)
	end
end
------------------------------
getInfo() --returns the informations of bot as [table]
info.user [string]
info.proxy [string] --returns only ip without port & user & pass for protection.
info.mac [string]
info.rid [string]
info.hash [string]
info.flag [string]
info.netid [integer]
info.level [integer]
------------------------------
getStatus() --returns the status of bot as [string]
------------------------------
getWorld() --returns the status of bot as [string]
------------------------------
getPos() --returns the position of bot as [table]
pos.x
pos.y
pos.tileX --simply tileX = x / 32
pos.tileY --simply tileY = y / 32
------------------------------
getPing() --returns the ping value of bot as [integer]
------------------------------
getBot() --returns the the table of selected bot
getBot(user[string]) --returns the the table of target bot with username
getBot(index[integer]) --returns the the table of target bot with index
getBot().index --returns the the index target bot

Note: you can use all of botting functions with getBot()
Example usage;
getBot():say("hello") --selected bot sends message to game chat
------------------------------

-----[EXTERNAL FUNCTIONS]-----

------------------------------
sleep(delay[integer]) --pause the code for a specific delay in milliseconds.
------------------------------
itemInfo(itemid[integer]) --returns the table of target item from database

item.name [string]
item.rarity [integer]
item.collisionType [integer]
------------------------------
request(type[string], url[string], headers[table = optional], proxy[string = optional]) --sends request to target website and returns the table of result
-- you can use as request(type, url) or request(type, url, headers) or request(type, url, proxy)

request.text
request.status
request.error

Example usage;
headers = {}
headers["User-Agent"] = ""

res = request("GET", "https://website", headers, "ip:port:user:pass")
if res.status == 0 then
	print("request failed| "..res.error)
end
if res.status == 200 then
	print("success| "..res.text)
end
------------------------------
wh = {}
wh.url -- your discord webhook url
wh.username
wh.content
wh.embed
wh.edit --boolean(true & false)(sends PATCH if true)

webhook(wh) --sends discord webhook
------------------------------
