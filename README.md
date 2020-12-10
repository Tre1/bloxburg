<h2>I am working on a new Bank system</h2>
BankIn: https://github.com/Lucke0051/BankIn/wiki

<br>

<h1>Bank System V2 Documentation</h1>
<div align="center">
    <img src="icon.png" alt="Bank System Logo" height="217" />
</div>

<div>&nbsp;</div>

**This system is outdated and is no longer updated and supported.**

**Bank System** is a free to use and open source module that allows you and your players to easily manage the games economy.
Bank System is distributed under the [CC BY-SA License](https://creativecommons.org/licenses/by-sa/4.0/)

**Support Discord:** [Bank System Discord](https://discord.gg/x7xhKgZ)

<br>

# Resources
- [Bank System loader](https://www.roblox.com/library/4402488644/Bank-System)
- [MainModule](https://www.roblox.com/library/4384860220/BankMainModule)
<br>

# API
## Retrieving the main module
```lua
local bank = require(game:GetService("ServerScriptService"):WaitForChild("BankMainModule"))
```

## Methods
### Server
#### `bank.AddMoney(player,amount)`
Gives the passed player the amount of money passed. Returns true if successful, otherwise it returns nil.

#### `bank.RemoveMoney(player,amount)`
Removes the passed amount of money from the player passed. Returns true if successful, otherwise it returns nil.

#### `bank.GetMoney(player)`
Returns the amount of money the passed player has.

#### `bank.GetBankName()`
Returns the bank's name.

# API Examples
## Money giver pad
Model: https://www.roblox.com/library/4667501888/Money-giver
```lua
local moneyAmountToGive = 500
local cooldownTime = 2

local serverScriptService = game:GetService("ServerScriptService")
local playerService = game:GetService("Players")
local bankModule = require(serverScriptService:WaitForChild("BankMainModule"))

local touchPart = script.Parent:WaitForChild("TouchPart")

local latestHit = tick()

local function touched(hit)
	if hit.Parent then
		local player = playerService:GetPlayerFromCharacter(hit.Parent)
		if player then
			if latestHit + cooldownTime < tick() then
				latestHit = tick()
				bankModule.AddMoney(player,moneyAmountToGive)
			end
		end
	end
end

touchPart.Touched:Connect(touched)
```

# Contact
Contact me at:
- **Discord** - [Bank System Discord](https://discord.gg/x7xhKgZ)
- **Twitter** - [@Luckeeees](https://twitter.com/Luckeeees)
- **DevForum** - [Lucke0051](https://devforum.roblox.com/u/lucke0051)
- **Roblox** - [Lucke0051](https://www.roblox.com/users/126451147/profile)
