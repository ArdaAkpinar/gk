game:GetService("StarterGui"):SetCore("SendNotification",{
    Title = "quracik",
    Text = "Made By quracik",
    Icon = "rbxassetid://57254792";
Duration = 5;
})

local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("GK Qura W Pyth", "Sentinel")

    -- MAIN
    local Main = Window:NewTab("Auto Save")
    local MainSection = Main:NewSection("Auto Save")

MainSection:NewToggle("Auto Save", "otomatik kurtarıs (her yerde kurtarır)", function(arg)
if arg then
TouchedGKBallBox = game.Workspace.TPSSystem.TPS.Touched:Connect(function(HRP)
    if HRP == game.Players.LocalPlayer.Character.HumanoidRootPart then
        for i,v in pairs(game.Workspace:GetDescendants()) do
    if v.Name == "TPS" and v:IsA("Part") then
    if game.Players.LocalPlayer.Character.Humanoid.RigType == Enum.HumanoidRigType.R6 then
    AnimationId = "304581045"
local Anim = Instance.new("Animation")
Anim.AnimationId = "rbxassetid://"..AnimationId
local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
k:Play()
wait(SaveDelay)

local A_1 = game:GetService("Workspace").TPSSystem.TPS
local A_2 = game.Players.LocalPlayer.Character["Right Leg"]
local Event = game:GetService("Workspace").FE.Actions.SaveRL
Event:FireServer(A_1, A_2)

local Events2 = game:GetService("Workspace").FE.Kick.RemoteEvent2
Events2:FireServer()
else
AnimationId = "3008336125"
local Anim = Instance.new("Animation")
Anim.AnimationId = "rbxassetid://"..AnimationId
local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
k:Play()
wait(SaveDelay)

local A_1 = game:GetService("Workspace").TPSSystem.TPS
local A_2 = game.Players.LocalPlayer.Character["HumanoidRootPart"]
local Event = game:GetService("Workspace").FE.Actions.SaveT
Event:FireServer(A_1, A_2)

local Events3 = game:GetService("Workspace").FE.Kick.RemoteEvent2
Events3:FireServer()
end
end
end
end
end)
    else
TouchedGKBallBox:Disconnect()
end
end)

local Main1 = Window:NewTab("Auto Jump")
    local Main1Section = Main1:NewSection("Auto Jump")

Main1Section:NewToggle("Auto Jump", "Auto Jump For The Ball", function(s)
if s then
_G.JUMP = true
    while _G.JUMP do
    wait()
    
for i,v in pairs(game.Workspace:GetDescendants()) do
    if v.Name == "TPS" and v:IsA("Part") then
    local a = Vector3.new(0, v.Position.Y, 0)
    local b = Vector3.new(0, game.Players.LocalPlayer.Character.Head.Position.Y, 0)
    if (a - b).Magnitude >= 5 then
    if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Position).Magnitude <= DistanceJump then
    game.Players.LocalPlayer.Character.Humanoid.Jump = true
end
end
end
end
end
    else
if _G.JUMP == true then
_G.JUMP = false
else
_G.JUMP = true
end
end
end)

Main1Section:NewSlider("Jump Distance", "bunu fullemeniz lazım", 50, 0, function(s) -- 500 (MaxValue) | 0 (MinValue)
    DistanceJump = s
end)

local Main2 = Window:NewTab("Auto Walkside")
    local Main2Section = Main2:NewSection("Auto Walkside")

Main2Section:NewToggle("Auto Walk Sideways ", "otomatik sag, sol hareket eder", function(s)
if s then
_G.SIDEM = true
    while _G.SIDEM do
    wait(0.8)
       if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - game.Workspace.TPSSystem.TPS.Position).Magnitude <= DistanceSide then
game.Players.LocalPlayer.Character.Humanoid:MoveTo(game.Players.LocalPlayer.Character.HumanoidRootPart.Position + Vector3.new(game.Workspace.TPSSystem.TPS.Position.X, 0, 0))
wait(0.8)
game.Players.LocalPlayer.Character.Humanoid:MoveTo(game.Players.LocalPlayer.Character.HumanoidRootPart.Position + Vector3.new(-game.Workspace.TPSSystem.TPS.Position.X, 0, 0))
end
end
    else
if _G.SIDEM == true then
_G.SIDEM = false
else
_G.SIDEM = true
end
end
end)

Main2Section:NewSlider("Walkdistance", "fullemeniz lazım", 300, 0, function(s) -- 500 (MaxValue) | 0 (MinValue)
    DistanceSide = s
end)

