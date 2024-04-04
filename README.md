local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local Window = Rayfield:CreateWindow({
   Name = "kaihub test",
   LoadingTitle = "koihob",
   LoadingSubtitle = "by me",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },
   KeySystem = true, -- Set this to true to use our key system
   KeySettings = {
      Title = "get key from dsc.gg/kairen",
      Subtitle = "dsc.gg/kairen",
      Note = "the key is inside dsc.gg/kairen",
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"https://pastebin.com/raw/GD2UkY3Z"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

local MainTab = Window:CreateTab("cat", 11104447804) -- Title, Image
local Section = Tab:CreateSection("erm")

Rayfield:Notify({
   Title = "cat",
   Content = "cat",
   Duration = 6.5,
   Image = 11104447804,
   Actions = { -- Notification Buttons
      Ignore = {
         Name = "Okay!",
         Callback = function()
         print("your cat is being held hostage lololololol")
      end
   },
},
})

local Button = Tab:CreateButton({
   Name = "cats blessing (inf jump) press r to enable and disable",
   Callback = function()
    -- by isaraw8912
-- Press [R] to turn off and to turn on

_G.infinjump = true
 
local Player = game:GetService("Players").LocalPlayer
local Mouse = Player:GetMouse()
Mouse.KeyDown:connect(function(k)
if _G.infinjump then
if k:byte() == 32 then
Humanoid = game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Humanoid")
Humanoid:ChangeState("Jumping")
wait(0.1)
Humanoid:ChangeState("Seated")
end
end
end)
 
local Player = game:GetService("Players").LocalPlayer
local Mouse = Player:GetMouse()
Mouse.KeyDown:connect(function(k)
k = k:lower()
if k == "r" then
if _G.infinjump == true then
_G.infinjump = false
else
_G.infinjump = true
end
end
end)

local Slider = Tab:CreateSlider({
   Name = "cat speed (walkspeed)",
   Range = {0, 100},
   Increment = 1,
   Suffix = "Bananas",
   CurrentValue = 16,
   Flag = "Slider1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
        game.Players.LocalPlayers.Character.Humanoid.WalkSpeed = (Value)
   end,
})
   end,
})

local Dropdown = MainTab:CreateDropdown({
   Name = "somting",
   Options = {"Option 1","Option 2"},
   CurrentOption = {"Option 1"},
   MultipleOptions = false,
   Flag = "Dropdown1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Option)
   -- The function that takes place when the selected option is changed
   -- The variable (Option) is a table of strings for the current selected options
   end,
})

local Tab = Window:CreateTab("Misc", 8513843575) -- Title, Image

local Button = MiscTab:CreateButton({
   Name = "Hitbox GUI",
   Callback = function()
    local ScreenGui = Instance.new("ScreenGui")
local main = Instance.new("Frame")
local label = Instance.new("TextLabel")
local Hitbox =
Instance.new("TextButton")

ScreenGui.Parent = game.CoreGui

main.Name = "main"
main.Parent = ScreenGui
main.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
main.Position = UDim2.new(0.40427351, 0, 0.34591195, 0)
main.Size = UDim2.new(0, 100, 0, 100)
main.Active = true
main.Draggable = true

label.Name = "label"
label.Parent = main
label.BackgroundColor3 = Color3.fromRGB(139,0,0)
label.Size = UDim2.new(0, 100, 0, 20)
label.Font = Enum.Font.SourceSans
label.Text = "Hitbox Gui"
label.TextColor3 = Color3.fromRGB(0, 0, 0)
label.TextScaled = true
label.TextSize = 5.000
label.TextWrapped = true

Hitbox.Name = "Hitbox"
Hitbox.Parent = main
Hitbox.BackgroundColor3 = Color3.fromRGB(0, 0, 255)
Hitbox.Position = UDim2.new(0.114285722, 0, 0.372448981, 0)
Hitbox.Size = UDim2.new(0, 90, 0, 40)
Hitbox.Font = Enum.Font.SourceSans
Hitbox.Text = "Hitbox"
Hitbox.TextColor3 = Color3.fromRGB(0, 0, 0)
Hitbox.TextSize = 40.000
Hitbox.MouseButton1Down:connect(function()
_G.HeadSize = 20

_G.Disabled = true


game:GetService('RunService').RenderStepped:connect(function()
if _G.Disabled then
for i,v in next, game:GetService('Players'):GetPlayers() do
if v.Name ~= game:GetService('Players').LocalPlayer.Name then
pcall(function()
v.Character.HumanoidRootPart.Size = Vector3.new(_G.HeadSize,_G.HeadSize,_G.HeadSize)
v.Character.HumanoidRootPart.Transparency = 0.7
v.Character.HumanoidRootPart.BrickColor = BrickColor.new("Really black")
v.Character.HumanoidRootPart.Material = "Neon"
v.Character.HumanoidRootPart.CanCollide = false
end)
end
end
end
end)
end)
   end,
})
