local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

local Frame = Instance.new("BloodTheme")
Frame.Size = UDim2.new(0, 400, 0, 300)
Frame.Position = UDim2.new(0.5, 0, 0.5, 0)
Frame.AnchorPoint = Vector2.new(0.5, 0.5)
Frame.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
Frame.BorderSizePixel = 0
Frame.Active = true
Frame.Draggable = true
Frame.Parent = ScreenGui

local FrameCorner = Instance.new("UICorner")
FrameCorner.CornerRadius = UDim.new(0, 10)
FrameCorner.Parent = BloodTheme

local Close = Instance.new("BloodTheme")
Close.Size = UDim2.new(0, 40, 0, 40)
Close.Position = UDim2.new(1, -40, 0, 0)
Close.BackgroundTransparency = 1
Close.Text = "×"
Close.TextScaled = true
Close.TextColor3 = Color3.fromRGB(150, 150, 150)
Close.Parent = BloodTheme
Close.MouseButton1Click:Connect(function()
   ScreenGui:Destroy()
end)

local Title = Instance.new("BloodTheme")
Title.Size = UDim2.new(1, 0, 0, 30)
Title.Position = UDim2.new(0, 0, 0.05, 0)
Title.Text = "Z3M Team"
Title.TextSize = 18
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.BackgroundTransparency = 1
Title.Parent = BloodTheme

local Instructions = Instance.new("BloodTheme")
Instructions.Size = UDim2.new(1, 0, 0, 30)
Instructions.Position = UDim2.new(0, 0, 0.2, 0)
Instructions.Text = "المفتاح "
Instructions.TextSize = 13
Instructions.TextColor3 = Color3.fromRGB(150, 150, 150)
Instructions.BackgroundTransparency = 1
Instructions.Parent = BloodTheme

local TextBox = Instance.new("BloodTheme")
TextBox.Size = UDim2.new(0.8, 0, 0.2, 0)
TextBox.Position = UDim2.new(0.1, 0, 0.4, 0)
TextBox.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
TextBox.PlaceholderText = "اضغط هنا "
TextBox.Text = ""
TextBox.TextSize = 18
TextBox.TextColor3 = Color3.fromRGB(255, 255, 255)
TextBox.Parent = BloodTheme

local TextBoxCorner = Instance.new("UICorner")
TextBoxCorner.CornerRadius = UDim.new(0, 5)
TextBoxCorner.Parent = TextBox

local GetKey = Instance.new("BloodTheme")
GetKey.Size = UDim2.new(0.35, 0, 0.15, 0)
GetKey.Position = UDim2.new(0.1, 0, 0.7, 0)
GetKey.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
GetKey.Text = "نسخ المفتاح"
GetKey.TextSize = 18
GetKey.TextColor3 = Color3.fromRGB(150, 150, 150)
GetKey.Parent = Frame

local GetKeyCorner = Instance.new("UICorner")
GetKeyCorner.CornerRadius = UDim.new(0, 5)
GetKeyCorner.Parent = GetKey

local CheckKey = Instance.new("BloodTheme")
CheckKey.Size = UDim2.new(0.35, 0, 0.15, 0)
CheckKey.Position = UDim2.new(0.55, 0, 0.7, 0)
CheckKey.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
CheckKey.Text = "تشغيل"
CheckKey.TextSize = 18
CheckKey.TextColor3 = Color3.fromRGB(150, 150, 150)
CheckKey.Parent = Frame

local CheckKeyCorner = Instance.new("UICorner")
CheckKeyCorner.CornerRadius = UDim.new(0, 5)
CheckKeyCorner.Parent = CheckKey

GetKey.MouseButton1Click:Connect(function()
   setclipboard("Z3M Team")
end)

local function validateKey(key)
    return key == "Z3M Team" -- Replace this with your key
end

CheckKey.MouseButton1Click:Connect(function()
    local enteredKey = TextBox.Text
    if validateKey(enteredKey) then
        TextBox.PlaceholderText = "يتم التحميل"
        TextBox.Text = ""
        wait(1)
        ScreenGui:Destroy()


loadstring(game:HttpGet(("https://raw.githubusercontent.com/REDzHUB/LibraryV2/main/redzLib")))()
MakeWindow({
  Hub = {
    Title = "Z3M Team MM2 V4 ",
    Animation = "by Z3M Team يتم تحميل"
  },
  Key = {
    KeySystem = false,
    Title = "Key System",
    Description = "",
    KeyLink = "",
    Keys = {"1234"},
    Notifi = {
      Notifications = true,
      CorrectKey = "Running the Script...",
      Incorrectkey = "The key is incorrect",
      CopyKeyLink = "Copied to Clipboard"
    }
  }
})


MinimizeButton({
  Image = "",
  Size = {40, 40},
  Color = Color3.fromRGB(10, 10, 10),
  Corner = true,
  Stroke = false,
  StrokeColor = Color3.fromRGB(255, 0, 0)
})

local Main = MakeTab({Name = "المميزات"})

local section = AddSection(Main, {"طرد"})


local Part = Instance.new("Part", workspace)
Part.Name = "Running Part"
Part.Position = Vector3.new(0, 1000, 0)
Part.Anchored = true
Part.CanCollide = true
Part.Size = Vector3.new(5, 1, 5)

local Plr = game:GetService("Players").LocalPlayer

local vim = game:GetService("VirtualInputManager")

function GetMurderer()
 for i, v in game:GetService("Players"):GetChildren() do
  if v.Backpack:FindFirstChild"Knife" or v.Character and v.Character:FindFirstChild("Knife") then return v.Character end
 end
 return nil
end

AddButton(Main, {
  Name = "قتل الجميع",
  Callback = function()
    for i, v in game:GetService("Players"):GetChildren() do
  if Plr.Backpack:FindFirstChild("Knife") then Plr.Backpack.Knife.Parent = Plr.Character end
   Plr.Character.HumanoidRootPart.CFrame = v.Character.HumanoidRootPart.CFrame
   vim:SendMouseButtonEvent(0,0,0,true,game,false,0)
   task.wait()
   vim:SendMouseButtonEvent(0,0,0,false,game,false,0)
   task.wait(.75)
  end
  end
})

AddButton(Main, {
  Name = "طيران للجميع",
  Callback = function()
local Targets = {"All"} -- "All", "Target Name", "arian_was_here"

local Players = game:GetService("Players")
local Player = Players.LocalPlayer

local AllBool = false

local GetPlayer = function(Name)
    Name = Name:lower()
    if Name == "الكل" or Name == "others" then
        AllBool = true
        return
    elseif Name == "عشوائي" then
        local GetPlayers = Players:GetPlayers()
        if table.find(GetPlayers,Player) then table.remove(GetPlayers,table.find(GetPlayers,Player)) end
        return GetPlayers[math.random(#GetPlayers)]
    elseif Name ~= "random" and Name ~= "all" and Name ~= "others" then
        for _,x in next, Players:GetPlayers() do
            if x ~= Player then
                if x.Name:lower():match("^"..Name) then
                    return x;
                elseif x.DisplayName:lower():match("^"..Name) then
                    return x;
                end
            end
        end
    else
        return
    end
end

local Message = function(_Title, _Text, Time)
    game:GetService("StarterGui"):SetCore("SendNotification", {Title = _Title, Text = _Text, Duration = Time})
end

local SkidFling = function(TargetPlayer)
    local Character = Player.Character
    local Humanoid = Character and Character:FindFirstChildOfClass("Humanoid")
    local RootPart = Humanoid and Humanoid.RootPart

    local TCharacter = TargetPlayer.Character
    local THumanoid
    local TRootPart
    local THead
    local Accessory
    local Handle

    if TCharacter:FindFirstChildOfClass("Humanoid") then
        THumanoid = TCharacter:FindFirstChildOfClass("Humanoid")
    end
    if THumanoid and THumanoid.RootPart then
        TRootPart = THumanoid.RootPart
    end
    if TCharacter:FindFirstChild("Head") then
        THead = TCharacter.Head
    end
    if TCharacter:FindFirstChildOfClass("Accessory") then
        Accessory = TCharacter:FindFirstChildOfClass("Accessory")
    end
    if Accessoy and Accessory:FindFirstChild("Handle") then
        Handle = Accessory.Handle
    end

    if Character and Humanoid and RootPart then
        if RootPart.Velocity.Magnitude < 50 then
            getgenv().OldPos = RootPart.CFrame
        end
        if THumanoid and THumanoid.Sit and not AllBool then
            return Message("Error Occurred", "Targeting is sitting", 5) -- u can remove dis part if u want lol
        end
        if THead then
            workspace.CurrentCamera.CameraSubject = THead
        elseif not THead and Handle then
            workspace.CurrentCamera.CameraSubject = Handle
        elseif THumanoid and TRootPart then
            workspace.CurrentCamera.CameraSubject = THumanoid
        end
        if not TCharacter:FindFirstChildWhichIsA("BasePart") then
            return
        end
        
        local FPos = function(BasePart, Pos, Ang)
            RootPart.CFrame = CFrame.new(BasePart.Position) * Pos * Ang
            Character:SetPrimaryPartCFrame(CFrame.new(BasePart.Position) * Pos * Ang)
            RootPart.Velocity = Vector3.new(9e7, 9e7 * 10, 9e7)
            RootPart.RotVelocity = Vector3.new(9e8, 9e8, 9e8)
        end
        
        local SFBasePart = function(BasePart)
            local TimeToWait = 2
            local Time = tick()
            local Angle = 0

            repeat
                if RootPart and THumanoid then
                    if BasePart.Velocity.Magnitude < 50 then
                        Angle = Angle + 100

                        FPos(BasePart, CFrame.new(0, 1.5, 0) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle),0 ,0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(2.25, 1.5, -2.25) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(-2.25, -1.5, 2.25) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, 1.5, 0) + THumanoid.MoveDirection,CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0) + THumanoid.MoveDirection,CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()
                    else
                        FPos(BasePart, CFrame.new(0, 1.5, THumanoid.WalkSpeed), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, -THumanoid.WalkSpeed), CFrame.Angles(0, 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, 1.5, THumanoid.WalkSpeed), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()
                        
                        FPos(BasePart, CFrame.new(0, 1.5, TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, -TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(0, 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, 1.5, TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(0, 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5 ,0), CFrame.Angles(math.rad(-90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(0, 0, 0))
                        task.wait()
                    end
                else
                    break
                end
            until BasePart.Velocity.Magnitude > 500 or BasePart.Parent ~= TargetPlayer.Character or TargetPlayer.Parent ~= Players or not TargetPlayer.Character == TCharacter or THumanoid.Sit or Humanoid.Health <= 0 or tick() > Time + TimeToWait
        end
        
        workspace.FallenPartsDestroyHeight = 0/0
        
        local BV = Instance.new("BodyVelocity")
        BV.Name = "ايفكس فيل"
        BV.Parent = RootPart
        BV.Velocity = Vector3.new(9e8, 9e8, 9e8)
        BV.MaxForce = Vector3.new(1/0, 1/0, 1/0)
        
        Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, false)
        
        if TRootPart and THead then
            if (TRootPart.CFrame.p - THead.CFrame.p).Magnitude > 5 then
                SFBasePart(THead)
            else
                SFBasePart(TRootPart)
            end
        elseif TRootPart and not THead then
            SFBasePart(TRootPart)
        elseif not TRootPart and THead then
            SFBasePart(THead)
        elseif not TRootPart and not THead and Accessory and Handle then
            SFBasePart(Handle)
        else
            return Message("Error Occurred", "Target is missing everything", 5)
        end
        
        BV:Destroy()
        Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, true)
        workspace.CurrentCamera.CameraSubject = Humanoid
        
        repeat
            RootPart.CFrame = getgenv().OldPos * CFrame.new(0, .5, 0)
            Character:SetPrimaryPartCFrame(getgenv().OldPos * CFrame.new(0, .5, 0))
            Humanoid:ChangeState("GettingUp")
            table.foreach(Character:GetChildren(), function(_, x)
                if x:IsA("BasePart") then
                    x.Velocity, x.RotVelocity = Vector3.new(), Vector3.new()
                end
            end)
            task.wait()
        until (RootPart.Position - getgenv().OldPos.p).Magnitude < 25
        workspace.FallenPartsDestroyHeight = getgenv().FPDH
    else
        return Message("Error Occurred", "Random error", 5)
    end
end

if not Welcome then Message("Success ez", "Enjoy!", 5) end
getgenv().Welcome = true
if Targets[1] then for _,x in next, Targets do GetPlayer(x) end else return end

if AllBool then
    for _,x in next, Players:GetPlayers() do
        SkidFling(x)
    end
end

for _,x in next, Targets do
    if GetPlayer(x) and GetPlayer(x) ~= Player then
        if GetPlayer(x).UserId ~= 1414978355 then
            local TPlayer = GetPlayer(x)
            if TPlayer then
                SkidFling(TPlayer)
            end
        else
            Message("حدث خطا", "This user is whitelisted! (Owner)", 5)
        end
    elseif not GetPlayer(x) and not AllBool then
        Message("Error Occurred", "Username Invalid", 5)
    end
end
 end
})

local section = AddSection(Main, {"Note antireport player"})


AddButton(Main, {
  Name = "لذهاب للبداية ",
  Callback = function()
    Plr.Character.HumanoidRootPart.CFrame = workspace.Lobby.Spawns.Spawn.CFrame
  end
})




AddButton(Main, {
  Name = "تاخذ المسدس",
  Callback = function()
    Plr.Character.HumanoidRootPart.CFrame = workspace.GunDrop.CFrame
  end
})


local section = AddSection(Main, {"طقطقه"})

AddToggle(Main, {
  Name = "هروب من القاتل تلقائيا ",
  Callback = function(state)
AE = state
 end
})



AddToggle(Main, {
  Name = "قتل القاتل تلقائيا ",
  Callback = function(state)
ASM = state
 end
})




AddToggle(Main, {
  Name = "تاخذ المسدس تلقائيا ",
  Callback = function(state)
ATG = state
 end
})

local Main = MakeTab({Name = "المميزات"})

workspace.ChildAdded:Connect(function(child)
task.delay(.25, function()
if child.Name == "الفوز تلقائيآ " and ATG then
local c = Plr.Character.HumanoidRootPart.CFrame
Plr.Character.HumanoidRootPart.CFrame = child.CFrame
Plr.Character.HumanoidRootPart.CFrame = c
end
end)
end)
function MurdererLoop()
 if ASM and Plr.Character and GetMurderer() and Plr.Character:FindFirstChild("Gun") or Plr.Backpack:FindFirstChild("Gun") then
  if Plr.Backpack:FindFirstChild("Gun") then Plr.Backpack.Gun.Parent = Plr.Character end
  local Murd = GetMurderer()
  Plr.Character.HumanoidRootPart.CFrame = Murd.HumanoidRootPart.CFrame + Vector3.new(11, 0, 0)
  Plr.Character.Gun.KnifeServer.ShootGun:InvokeServer(1, Murd.HumanoidRootPart.Position, "AH")
 end
 task.wait(.5)
end
function SecondLoop()
 if GetMurderer() == Plr.Character or GetMurderer() == nil or not AE then return end
 if (GetMurderer().HumanoidRootPart.Position-Plr.Character.HumanoidRootPart.Position).magnitude < 11 then
  Plr.Character.HumanoidRootPart.CFrame = Part.CFrame + Vector3.new(0, 3, 0)
 end
end




getgenv().God = false
AddToggle(Main, {
  Name = "عدم الموت",
  Callback = function(value)
getgenv().God = value
if getgenv().God == true then
while getgenv().God == true do
wait()
game:GetService("Players").LocalPlayer.Character.Humanoid.Health = 100
end
end
 end
})

getgenv().Autofarm = false
AddToggle(Main, {
  Name = "الفوز تلقائياً ",
  Callback = function(value)
getgenv().Autofarm = value
 
if getgenv().Autofarm == true then
while getgenv().Autofarm == true do
wait()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(0, 14, 0)
end
end
 end
})



local Main = MakeTab({Name = "مميزات اخرى"})

local section = AddSection(Main, {"Player"})



AddToggle(Main, {
  Name = "اختراق جدران",
  Callback = function(s)
getgenv().Noclip = s
    game:GetService("RunService").Heartbeat:Connect(function()
        if Noclip == true then
            game:GetService("RunService").Stepped:wait()
            game.Players.LocalPlayer.Character.Head.CanCollide = false
            game.Players.LocalPlayer.Character.Torso.CanCollide = false
        end
    end)
 end
})

 
AddToggle(Main, {
  Name = "قفز لنهائي ",
  Callback = function(s)
getgenv().InfJ = s
    game:GetService("UserInputService").JumpRequest:connect(function()
        if InfJ == true then
            game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")
        end
    end)
 end
})


local section = AddSection(Main, {"الايم"})



AddToggle(Main, {
  Name = "ايم بوت مسدس",
  Callback = function(s)
local Players = game.Players
local LocalPlayer = Players.LocalPlayer
local GetPlayers = Players.GetPlayers
local Camera = workspace.CurrentCamera
local WTSP = Camera.WorldToScreenPoint
local FindFirstChild = game.FindFirstChild
local Vector2_new = Vector2.new
local Mouse = LocalPlayer.GetMouse(LocalPlayer)
function ClosestChar()
    local Max, Close = math.huge
    for I,V in pairs(GetPlayers(Players)) do
        if V ~= LocalPlayer and V.Team ~= LocalPlayer.Team and V.Character then
            local Head = FindFirstChild(V.Character, "Head")
            if Head then
                local Pos, OnScreen = WTSP(Camera, Head.Position)
                if OnScreen then
                    local Dist = (Vector2_new(Pos.X, Pos.Y) - Vector2_new(Mouse.X, Mouse.Y)).Magnitude
                    if Dist < Max then
                        Max = Dist
                        Close = V.Character
                    end
                end
            end
        end
    end
    return Close
end

local MT = getrawmetatable(game)
local __namecall = MT.__namecall
setreadonly(MT, false)
MT.__namecall = newcclosure(function(self, ...)
    local Method = getnamecallmethod()
    if Method == "FindPartOnRay" and not checkcaller() and tostring(getfenv(0).script) == "GunInterface" then
        local Character = ClosestChar()
        if Character then
            return Character.Head, Character.Head.Position
        end
    end

    return __namecall(self, ...)
end)
setreadonly(MT, true)
 end
})



AddToggle(Main, {
  Name = "ايم بوت سكين",
  Callback = function(s)
local Players = game.Players
local LocalPlayer = Players.LocalPlayer
local GetPlayers = Players.GetPlayers
local Camera = workspace.CurrentCamera
local WTSP = Camera.WorldToScreenPoint
local FindFirstChild = game.FindFirstChild
local Vector2_new = Vector2.new
local Mouse = LocalPlayer.GetMouse(LocalPlayer)
function ClosestChar()
    local Max, Close = math.huge
    for I,V in pairs(GetPlayers(Players)) do
        if V ~= LocalPlayer and V.Team ~= LocalPlayer.Team and V.Character then
            local Head = FindFirstChild(V.Character, "Head")
            if Head then
                local Pos, OnScreen = WTSP(Camera, Head.Position)
                if OnScreen then
                    local Dist = (Vector2_new(Pos.X, Pos.Y) - Vector2_new(Mouse.X, Mouse.Y)).Magnitude
                    if Dist < Max then
                        Max = Dist
                        Close = V.Character
                    end
                end
            end
        end
    end
    return Close
end

local MT = getrawmetatable(game)
local __namecall = MT.__namecall
setreadonly(MT, false)
MT.__namecall = newcclosure(function(self, ...)
    local Method = getnamecallmethod()
    if Method == "FindPartOnRay" and not checkcaller() and tostring(getfenv(0).script) == "GunInterface" then
        local Character = ClosestChar()
        if Character then
            return Character.Head, Character.Head.Position
        end
    end

    return __namecall(self, ...)
end)
setreadonly(MT, true)
 end
})


AddButton(Main, {
  Name = "هيت بوكس",
  Callback = function()
function getplrsname()
for i,v in pairs(game:GetChildren()) do
if v.ClassName == "Players" then
return v.Name
end
end
end
local players = getplrsname()
local plr = game[players].LocalPlayer
coroutine.resume(coroutine.create(function()
while  wait(1) do
coroutine.resume(coroutine.create(function()
for _,v in pairs(game[players]:GetPlayers()) do
if v.Name ~= plr.Name and v.Character then
v.Character.LowerTorso.CanCollide = false
v.Character.LowerTorso.Material = "Neon"
v.Character.LowerTorso.Size = Vector3.new(5,5,5)
v.Character.HumanoidRootPart.Size = Vector3.new(5,5,5)
end
end
end))
end
end))
 end
})

AddButton(Main, {
  Name = "مسدس ملون",
  Callback = function(s)
local c = 1 function zigzag(X)  return math.acos(math.cos(X * math.pi)) / math.pi end game:GetService("RunService").RenderStepped:Connect(function()  if game.Workspace.Camera:FindFirstChild('Arms') then   for i,v in pairs(game.Workspace.Camera.Arms:GetDescendants()) do    if v.ClassName == 'MeshPart' then      v.Color = Color3.fromHSV(zigzag(c),1,1)     c = c + .0001    end   end  end end)
net = true 
notify = true
 end
})

AddButton(Main, {
  Name = "مسجل مجانى",
  Callback = function(s)
_G.boomboxb = game:GetObjects('rbxassetid://740618400')[1]
_G.boomboxb.Parent = game:GetService'Players'.LocalPlayer.Backpack
loadstring(_G.boomboxb.Client.Source)() 
loadstring(_G.boomboxb.Server.Source)()
 end
})

AddButton(Main, {
  Name = "سكن مزيف",
  Callback = function(s)
local WeaponOwnRange = {
min=1,
max=5
}

local DataBase, PlayerData = getrenv()._G.Database, getrenv()._G.PlayerData

local newOwned = {}

for i,v in next, DataBase.Item do
newOwned[i] = math.random(WeaponOwnRange.min, WeaponOwnRange.max) -- newOwned[Weapon]: ItemCount
end

local PlayerWeapons = PlayerData.Weapons

game:GetService("تشغيل الخدمة"):BindToRenderStep("InventoryUpdate", 0, function()
PlayerWeapons.Owned = newOwned
end)

game.Players.LocalPlayer.Character.Humanoid.Health = 0
end
})

local Main = MakeTab({Name = "الاعب"})

local Slider = AddSlider(Main, {
  Name = "سرعه",
  MinValue = 25,
  MaxValue = 300,
  Default = 0,
  Increase = 1,
  Callback = function(value)
    getgenv().Walkspeed = value
    pcall(function() game:GetService("Players").LocalPlayer.Character.Humanoid.WalkSpeed = value
    end)
  end
})


AddToggle(Main, {
  Name = "سرعة التلقائى",
  Callback = function(state)
getgenv().loopW = state
    game:GetService("RunService").Heartbeat:Connect(function()
        if loopW == true then
            pcall(function()
                game:GetService("Players").LocalPlayer.Character.Humanoid.WalkSpeed = Walkspeed
            end)
        end
    end)
 end
})

local Slider = AddSlider(Main, {
  Name = "قفز",
  MinValue = 25,
  MaxValue = 300,
  Default = 0,
  Increase = 1,
  Callback = function(value)
    getgenv().Jumppower = value
    pcall(function()
        game:GetService("Players").LocalPlayer.Character.Humanoid.JumpPower = value
    end)
  end
})

AddToggle(Main, {
  Name = "قفز تلقائي",
  Callback = function(state)
getgenv().loopJ = state
    game:GetService("RunService").Heartbeat:Connect(function()
        if loopJ == true then
            pcall(function()
                game:GetService("الاشخاص").LocalPlayer.Character.Humanoid.JumpPower = Jumppower
            end)
        end
    end)
 end
})
local section = AddSection(Main, {"تجميد الاعي"})


AddButton(Main, {
  Name = "تجميد الكل",
  Callback = function()
for i, v in game:GetService("Players"):GetChildren() do
  if v ~= Plr and not v.Backpack:FindFirstChild("Knife") or v.Character and not v.Character:FindFirstChild("Knife") then
  if Plr.Backpack:FindFirstChild("Knife") then Plr.Backpack.Knife.Parent = Plr.Character end
   Plr.Character.HumanoidRootPart.CFrame = v.Character.HumanoidRootPart.CFrame
   vim:SendMouseButtonEvent(0,0,0,true,game,false,0)
   task.wait()
   vim:SendMouseButtonEvent(0,0,0,false,game,false,0)
   task.wait(.75)
  end
 end
end
})

AddButton(Main, {
  Name = "الغاء التجميد الكل",
  Callback = function(state)
for i, v in game:GetService("Players"):GetChildren() do
  if v ~= Plr and not v.Backpack:FindFirstChild("Knife") or v.Character and not v.Character:FindFirstChild("Knife") then
   Plr.Character.HumanoidRootPart.CFrame = v.Character.HumanoidRootPart.CFrame
   task.wait(.75)
  end
 end
end
})

game:GetService("RunService").Heartbeat:Connect(MurdererLoop)
game:GetService("RunService").Heartbeat:Connect(SecondLoop)

local section = AddSection(Main, {"نقل عن بعد"})

local plrs = game.Players

-- Fetch all player names
local playerNames = {}
local players = plrs:GetPlayers()

for _, player in ipairs(players) do
    table.insert(playerNames, player.Name)
end

local Dropdown = AddDropdown(Main, {
  Name = playerNames[1] or "No Players",
  Options = playerNames,
  Default = "2",
  Callback = function(selectedplrName)
    plrs:FindFirstChild(selectedplrName)
        local targetPlayer = plrs:FindFirstChild(selectedplrName)
        if targetPlayer and targetPlayer.Character and targetPlayer.Character:FindFirstChild("HumanoidRootPart") then
            -- Teleporting your character to the selected player's position
            local targetPosition = targetPlayer.Character.HumanoidRootPart.Position
            local localPlayerRoot = plrs.LocalPlayer.Character:FindFirstChild("HumanoidRootPart")
            
            if localPlayerRoot then
                localPlayerRoot.CFrame = CFrame.new(targetPosition)
            end
        end
        print(selectedplrName)

  end
})



local Main = MakeTab({Name = "الخورافي"})


local section = AddSection(Main, {"Esp highlight"})



AddButton(Main, {
  Name = "هروب من القاتل تلقائي ",
  Callback = function()
loadstring(game:HttpGet('https://raw.githubusercontent.com/kelve123/Ken_Murder_Mystery_esp/main/Ken%20Murder%20Mystery%202%20Esp'))()
end
})

AddButton(Main, {
  Name = "هروب من الجميع تلقائي",
  Callback = function()
local FillColor = Color3.fromRGB(65,255,0)
local DepthMode = "فوق"
local FillTransparency = 0.5
local OutlineColor = Color3.fromRGB(255,255,255)
local OutlineTransparency = 0

local CoreGui = game:FindService("CoreGui")
local Players = game:FindService("Players")
local lp = Players.LocalPlayer
local connections = {}

local Storage = Instance.new("Folder")
Storage.Parent = CoreGui
Storage.Name = "Highlight_Storage"

local function Highlight(plr)
    local Highlight = Instance.new("بقعة بيضاء")
    Highlight.Name = plr.Name
    Highlight.FillColor = FillColor
    Highlight.DepthMode = DepthMode
    Highlight.FillTransparency = FillTransparency
    Highlight.OutlineColor = OutlineColor
    Highlight.OutlineTransparency = 0
    Highlight.Parent = Storage
    
    local plrchar = plr.Character
    if plrchar then
        Highlight.Adornee = plrchar
    end

    connections[plr] = plr.CharacterAdded:Connect(function(char)
        Highlight.Adornee = char
    end)
end

Players.PlayerAdded:Connect(Highlight)
for i,v in next, Players:GetPlayers() do
    Highlight(v)
end

Players.PlayerRemoving:Connect(function(plr)
    local plrname = plr.Name
    if Storage[plrname] then
        Storage[plrname]:Destroy()
    end
    if connections[plr] then
        connections[plr]:Disconnect()
    end
end)
end
})

local section = AddSection(Main, {"Esp player"})

AddButton(Main, {
  Name = "صندوق",
  Callback = function()
local Player = game:GetService("الاشخاص").LocalPlayer
local Camera = game:GetService("Workspace").CurrentCamera
local Mouse = Player:GetMouse()

local function DrawESP(plr)
    local Box = Drawing.new("Quad")
    Box.Visible = false
    Box.PointA = Vector2.new(0, 0)
    Box.PointB = Vector2.new(0, 0)
    Box.PointC = Vector2.new(0, 0)
    Box.PointD = Vector2.new(0, 0)
    Box.Color = Color3.fromRGB(255, 255, 255)
    Box.Thickness = 1
    Box.Transparency = 1

    local function Update()
        local c
        c = game:GetService("RunService").RenderStepped:Connect(function()
            if plr.Character ~= nil and plr.Character:FindFirstChildOfClass("Humanoid") ~= nil and plr.Character.PrimaryPart ~= nil and plr.Character:FindFirstChildOfClass("Humanoid").Health > 0 then
                local pos, vis = Camera:WorldToViewportPoint(plr.Character.PrimaryPart.Position)
                if vis then 
                    local points = {}
                    local c = 0
                    for _,v in pairs(plr.Character:GetChildren()) do
                        if v:IsA("BasePart") then
                            c = c + 1
                            local p, vis = Camera:WorldToViewportPoint(v.Position)
                            if v == plr.Character.PrimaryPart then
                                p, vis = Camera:WorldToViewportPoint((v.CFrame * CFrame.new(0, 0, -v.Size.Z)).p)
                            elseif v.Name == "راس" then
                                p, vis = Camera:WorldToViewportPoint((v.CFrame * CFrame.new(0, v.Size.Y/2, v.Size.Z/1.25)).p)
                            elseif string.match(v.Name, "Left") then
                                p, vis = Camera:WorldToViewportPoint((v.CFrame * CFrame.new(-v.Size.X/2, 0, 0)).p)
                            elseif string.match(v.Name, "Right") then
                                p, vis = Camera:WorldToViewportPoint((v.CFrame * CFrame.new(v.Size.X/2, 0, 0)).p)
                            end
                            points[c] = {p, vis}
                        end
                    end

                    local TopY = math.huge
                    local DownY = -math.huge
                    local LeftX = math.huge
                    local RightX = -math.huge

                    local Left
                    local Right
                    local Top
                    local Bottom

                    local closest = nil
                    for _,v in pairs(points) do
                        if v[2] == true then
                            local p = v[1]
                            if p.Y < TopY then
                                Top = p
                                TopY = p.Y
                            end
                            if p.Y > DownY then
                                Bottom = p
                                DownY = p.Y
                            end
                            if p.X > RightX then
                                Right = p
                                RightX = p.X
                            end
                            if p.X < LeftX then
                                Left = p
                                LeftX = p.X
                            end
                        end
                    end

                    if Left ~= nil and Right ~= nil and Top ~= nil and Bottom ~= nil then
                        Box.PointA = Vector2.new(Right.X, Top.Y)
                        Box.PointB = Vector2.new(Left.X, Top.Y)
                        Box.PointC = Vector2.new(Left.X, Bottom.Y)
                        Box.PointD = Vector2.new(Right.X, Bottom.Y)

                        Box.Visible = true
                    else 
                        Box.Visible = false
                    end
                else 
                    Box.Visible = false
                end
            else
                Box.Visible = false
                if game.Players:FindFirstChild(plr.Name) == nil then
                    c:Disconnect()
                end
            end
        end)
    end
    coroutine.wrap(Update)()
end

for _,v in pairs(game:GetService("Players"):GetChildren()) do
    if v.Name ~= Player.Name then 
        DrawESP(v)
    end
end

game:GetService("Players").PlayerAdded:Connect(function(v)
    DrawESP(v)
end)
end
})


AddButton(Main, {
  Name = "Esp name",
  Callback = function()
local c = workspace.CurrentCamera
local ps = game:GetService("Players")
local lp = ps.LocalPlayer
local rs = game:GetService("RunService")

local function esp(p,cr)
	local h = cr:WaitForChild("Humanoid")
	local hrp = cr:WaitForChild("Head")

	local text = Drawing.new("Text")
	text.Visible = false
	text.Center = true
	text.Outline = false 
	text.Font = 3
	text.Size = 16.16
	text.Color = Color3.new(170,170,170)

	local conection
	local conection2
	local conection3

	local function dc()
		text.Visible = false
		text:Remove()
		if conection then
			conection:Disconnect()
			conection = nil 
		end
		if conection2 then
			conection2:Disconnect()
			conection2 = nil 
		end
		if conection3 then
			conection3:Disconnect()
			conection3 = nil 
		end
	end

	conection2 = cr.AncestryChanged:Connect(function(_,parent)
		if not parent then
			dc()
		end
	end)

	conection3 = h.HealthChanged:Connect(function(v)
		if (v<=0) or (h:GetState() == Enum.HumanoidStateType.Dead) then
			dc()
		end
	end)

	conection = rs.RenderStepped:Connect(function()
		local hrp_pos,hrp_onscreen = c:WorldToViewportPoint(hrp.Position)
		if hrp_onscreen then
			text.Position = Vector2.new(hrp_pos.X, hrp_pos.Y - 27)
			text.Text = "[ "..p.Name.." ]"
			text.Visible = true
		else
			text.Visible = false
		end
	end)
end

local function p_added(p)
	if p.Character then
		esp(p,p.Character)
	end
	p.CharacterAdded:Connect(function(cr)
		esp(p,cr)
	end)
end

for i,p in next, ps:GetPlayers() do 
	if p ~= lp then
		p_added(p)
	end
end

ps.PlayerAdded:Connect(p_added)
 end
})

local Main = MakeTab({Name = "الانميشن"})

local section = AddSection(Main, {"شات سبام"})


function SpamChat()
			while autochat == true do
				local ohString1 = "Tbao Hub On Top"
				local ohString2 = "All"	game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer(ohString1, ohString2)
				wait(1)
			end
		end

AddToggle(Main, {
  Name = "Spam chat",
  Callback = function(Value)
autochat = Value
				SpamChat()
 end
})


local section = AddSection(Main, {"Sever"})

AddButton(Main, {
  Name = "Sever hop",
  Callback = function()
local Http = game:GetService("HttpService")
local TPS = game:GetService("TeleportService")
local Api = "https://games.roblox.com/v1/games/"
local _place = game.PlaceId
local _servers = Api.._place.."/servers/Public?sortOrder=Asc&limit=100"
function ListServers(cursor)
   local Raw = game:HttpGet(_servers .. ((cursor and "&cursor="..cursor) or ""))
   return Http:JSONDecode(Raw)
end
local Server, Next; repeat
   local Servers = ListServers(Next)
   Server = Servers.data[1]
   Next = Servers.nextPageCursor
until Server
TPS:TeleportToPlaceInstance(_place,Server.id,game.Players.LocalPlayer)
end
})


AddButton(Main, {
  Name = "انضم",
  Callback = function()
local ts = game:GetService("TeleportService")
local p = game:GetService("Players").LocalPlayer
ts:Teleport(game.PlaceId, p)
end
})


local section = AddSection(Main, {"Fps"})

AddButton(Main, {
  Name = "تحسين فرويمات",
  Callback = function()
local ToDisable = {
	Textures = false,
	VisualEffects = true,
	Parts = true,
	Particles = true,
	Sky = true
}

local ToEnable = {
	FullBright = false
}

local Stuff = {}

for _, v in next, game:GetDescendants() do
	if ToDisable.Parts then
		if v:IsA("Part") or v:IsA("Union") or v:IsA("BasePart") then
			v.Material = Enum.Material.SmoothPlastic
			table.insert(Stuff, 1, v)
		end
	end
	
	if ToDisable.Particles then
		if v:IsA("ParticleEmitter") or v:IsA("Smoke") or v:IsA("Explosion") or v:IsA("Sparkles") or v:IsA("Fire") then
			v.Enabled = false
			table.insert(Stuff, 1, v)
		end
	end
	
	if ToDisable.VisualEffects then
		if v:IsA("BloomEffect") or v:IsA("BlurEffect") or v:IsA("DepthOfFieldEffect") or v:IsA("SunRaysEffect") then
			v.Enabled = false
			table.insert(Stuff, 1, v)
		end
	end
	
	if ToDisable.Textures then
		if v:IsA("Decal") or v:IsA("Texture") then
			v.Texture = ""
			table.insert(Stuff, 1, v)
		end
	end
	
	if ToDisable.Sky then
		if v:IsA("Sky") then
			v.Parent = nil
			table.insert(Stuff, 1, v)
		end
	end
end
end
})

local Main = MakeTab({Name = "المطورين"})

local section = AddSection(Main, {"By Z3M Team"})

local section = AddSection(Main, {"https://discord.gg/azc"})

local section = AddSection(Main, {"رابط سيرفر فوق"})

local player = game.Players.LocalPlayer
local chattedConnection = player.Chatted:Connect(function(message)
local keyword = "" -- 
if string.sub(message, 1, #keyword) == keyword then
local ply = game.Players.LocalPlayer
    local chr = ply.Character
    chr.RightLowerLeg.MeshId = "902942093"
    chr.RightLowerLeg.Transparency = "1"
    chr.RightUpperLeg.MeshId = "http://www.roblox.com/asset/?id=902942096"
    chr.RightUpperLeg.TextureID = "http://roblox.com/asset/?id=902843398"
    chr.RightFoot.MeshId = "902942089"
    chr.RightFoot.Transparency = "1"
print("")
-- نهايه
end
end)

local player = game.Players.LocalPlayer
local chattedConnection = player.Chatted:Connect(function(message)
local keyword = "العم N7R" -- 
if string.sub(message, 1, #keyword) == keyword then
game.Players.LocalPlayer.Character.Head.Transparency = 1
    game.Players.LocalPlayer.Character.Head.Transparency = 1
    for i,v in pairs(game.Players.LocalPlayer.Character.Head:GetChildren()) do
        if (v:IsA("Decal")) then
            v.Transparency = 1
        end
game.Players.LocalPlayer.Character.Head.Transparency = 1 game.Players.LocalPlayer.Character.Head.Transparency = 1 for i,v in pairs(game.Players.LocalPlayer.Character.Head:GetChildren()) do if (v:IsA("Decal")) then v.Transparency = 1
 end
end
end
print("")
-- نهايه
end
end)

local args = {
    [1] = "\216\167\217\132\216\185\217\133 VR7 ",
    [2] = "All"
}

game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer(unpack(args))

local player = game.Players.LocalPlayer
local chattedConnection = player.Chatted:Connect(function(message)
local keyword = "!تعليق السيرفر" -- 
if string.sub(message, 1, #keyword) == keyword then
local lp = game:FindService("Players").LocalPlayer
game:GetService("CoreGui").PurchasePrompt.Enabled = true
_G.Lag = true
while _G.Lag do
for i,v in pairs(workspace:GetDescendants()) do
            if v:IsA("ClickDetector") then
                fireclickdetector(v)
            end
end
        wait(1)
        end
print("تم تشغيل الامر")
-- نهايه
end
end)

local function sendSystemMessage()
    game.StarterGui:SetCore("ChatMakeSystemMessage", {
    Text = "[System🔥] : استمتع 😉 N7R ! "; -- 
        Font = Enum.Font; --font
        Color = Color3.new(252, 250, 255); -- 
        FontSize = Enum.FontSize.Size96 --size
    })
end

sendSystemMessage()

local player = game.Players.LocalPlayer
local chattedConnection = player.Chatted:Connect(function(message)
local keyword = "!سحب" -- 
if string.sub(message, 1, #keyword) == keyword then
local plrs=game:FindFirstChildOfClass("Players")
local lp=plrs.LocalPlayer
local ws=game:FindFirstChildOfClass("Workspace")
local uis=game:FindFirstChildOfClass("UserInputService")
local rs=game:FindFirstChildOfClass("RunService")
local heartbeat=rs.Heartbeat
local renderstepped=rs.RenderStepped
local angles=CFrame.Angles
local cf=CFrame.new
local v3=Vector3.new
local v3_010=v3(0,1,0)
local v3_0=v3(0,0,0)
local osclock=os.clock
local twait=task.wait
local slower=string.lower
local ssub=string.sub

local speeding=32
local maxspeed=75
local off=angles(-1.5707963267948966,0,0)

local function gp(p,n,cl)
	if typeof(p)=="Instance" then
		local c=p:GetChildren()
		for i=1,#c do
			local v=c[i]
			if (v.Name==n) and v:IsA(cl) then
				return v
			end
		end
	end
	return nil
end

local i=Instance.new 
local v2=Vector2.new 
local bc=BrickColor.new 
local c3=Color3.new 
local u2=UDim2.new 
local sc,mr=string.char,math.random 
local function rs(l) 
	l=l or mr(8,15) 
	local s="" 
	for i=1,l do 
		if mr(1,2)==1 then 
			s=s..sc(mr(65,90)) 
		else 
			s=s..sc(mr(97,122)) 
		end 
	end 
	return s 
end 
local e=Enum 
local i1=i("Frame") 
local i2=i("TextLabel") 
local i3=i("Frame") 
local i4=i("TextBox") 
local i5=i("TextButton") 
local i6=i("TextLabel") 
local i7=i("TextLabel") 
local i8=i("ScreenGui") 
i1.AnchorPoint=v2(0.5,0.5) 
i1.BackgroundColor=bc(149) 
i1.BackgroundColor3=c3(0.129412,0.129412,0.129412) 
i1.BorderColor=bc(1003) 
i1.BorderColor3=c3(0,0,0) 
i1.BorderSizePixel=0 
i1.Position=u2(0.5,0,0.5,0) 
i1.Size=u2(0,250,0,140) 
i1.Name=rs() 
i1.Parent=i8 
i2.Font=e.Font.SourceSans 
i2.FontSize=e.FontSize.Size24 
i2.Text="By VR7" 
i2.TextColor=bc(1002) 
i2.TextColor3=c3(0.815686,0.815686,0.815686) 
i2.TextSize=20 
i2.BackgroundColor=bc(1001) 
i2.BackgroundColor3=c3(1,1,1) 
i2.BackgroundTransparency=1 
i2.BorderColor=bc(1003) 
i2.BorderColor3=c3(0,0,0) 
i2.BorderSizePixel=0 
i2.Size=u2(1,0,0,25) 
i2.Name=rs() 
i2.Parent=i1 
i3.BackgroundColor=bc(26) 
i3.BackgroundColor3=c3(0.192157,0.192157,0.192157) 
i3.BorderColor=bc(1003) 
i3.BorderColor3=c3(0,0,0) 
i3.BorderSizePixel=0 
i3.ClipsDescendants=true 
i3.Position=u2(0,5,0,25) 
i3.Size=u2(1,-10,1,-30) 
i3.Name=rs() 
i3.Parent=i1 
i4.CursorPosition=-1 
i4.Font=e.Font.SourceSans 
i4.FontSize=e.FontSize.Size24 
i4.PlaceholderColor3=c3(0.509804,0.509804,0.509804) 
i4.PlaceholderText="اكتب اسم الاعب هنا" 
i4.Text="" 
i4.TextColor=bc(1) 
i4.TextColor3=c3(0.952941,0.952941,0.952941) 
i4.TextSize=20 
i4.TextWrap=true 
i4.AnchorPoint=v2(0.5,0) 
i4.BackgroundColor=bc(364) 
i4.BackgroundColor3=c3(0.266667,0.266667,0.266667) 
i4.BorderColor=bc(1003) 
i4.BorderColor3=c3(0,0,0) 
i4.BorderSizePixel=0 
i4.ClipsDescendants=true 
i4.Position=u2(0.5,0,0,13) 
i4.Size=u2(1,-30,0,32) 
i4.Name=rs() 
i4.Parent=i3 
i5.AnchorPoint=v2(0.5,0) 
i5.BackgroundColor=bc(364) 
i5.BackgroundColor3=c3(0.266667,0.266667,0.266667) 
i5.BorderColor=bc(1003) 
i5.BorderColor3=c3(0,0,0) 
i5.BorderSizePixel=0 
i5.Position=u2(0.5,0,0,64) 
i5.Size=u2(1,-30,0,32) 
i5.Name=rs() 
i5.Parent=i3 
i5.Font=e.Font.FredokaOne 
i5.FontSize=e.FontSize.Size24 
i5.Text="سحب" 
i5.TextColor3=c3(0.55,0.55,0.55) 
i5.TextSize=23 
i6.Font=e.Font.SourceSans 
i6.FontSize=e.FontSize.Size14 
i6.Text= "ملاحظه لازم الاعب يكون مايتحرك" 
i6.TextColor=bc(2) 
i6.TextColor3=c3(0.635294,0.635294,0.635294) 
i6.AnchorPoint=v2(1,1) 
i6.AutomaticSize=e.AutomaticSize.XY 
i6.BackgroundColor=bc(1001) 
i6.BackgroundColor3=c3(1,1,1) 
i6.BackgroundTransparency=1 
i6.BorderColor=bc(1003) 
i6.BorderColor3=c3(0,0,0) 
i6.BorderSizePixel=0 
i6.Position=u2(1,0,1,0) 
i6.Name=rs() 
i6.Parent=i3 
i7.Font=e.Font.SourceSans 
i7.FontSize=e.FontSize.Size14 
i7.Text="" 
i7.TextColor=bc(2) 
i7.TextColor3=c3(0.635294,0.635294,0.635294) 
i7.AnchorPoint=v2(0.5,0) 
i7.AutomaticSize=e.AutomaticSize.XY 
i7.BackgroundColor=bc(1001) 
i7.BackgroundColor3=c3(1,1,1) 
i7.BackgroundTransparency=1 
i7.BorderColor=bc(1003) 
i7.BorderColor3=c3(0,0,0) 
i7.BorderSizePixel=0 
i7.Position=u2(0.5,0,0,47) 
i7.Name=rs() 
i7.Parent=i3 
i8.ZIndexBehavior=e.ZIndexBehavior.Sibling 
i8.Name=rs() 

local function Draggable(window,obj)
	local MB1enum = e.UserInputType.MouseButton1
	local TOUCHenum = e.UserInputType.Touch
	obj = obj or window
	local activeEntered = 0
	local mouseStart = nil
	local dragStart = nil
	local inputbegancon = nil
	local rendersteppedcon = nil
	local inputendedcon = nil
	local function inputendedf(a)
		a=a.UserInputType
		if (a==MB1enum) or (a==TOUCHenum) then
			rendersteppedcon:Disconnect()
			inputendedcon:Disconnect()
		end
	end
	local function rendersteppedf()
		local off = uis:GetMouseLocation()-mouseStart
		window.Position=dragStart+u2(0,off.X,0,off.Y)
	end
	local function inputbeganf(a)
		a=a.UserInputType
		if ((a==MB1enum) or (a==TOUCHenum)) and (activeEntered==0) and not uis:GetFocusedTextBox() then
			mouseStart=uis:GetMouseLocation()
			dragStart=window.Position
			if rendersteppedcon then rendersteppedcon:Disconnect() end
			rendersteppedcon = renderstepped:Connect(rendersteppedf)
			if inputendedcon then inputendedcon:Disconnect() end
			inputendedcon = uis.InputEnded:Connect(inputendedf)
		end
	end
	obj.MouseEnter:Connect(function()
		if inputbegancon then inputbegancon:Disconnect() end
		inputbegancon = uis.InputBegan:Connect(inputbeganf)
	end)
	obj.MouseLeave:Connect(function()
		inputbegancon:Disconnect()
	end)
	local function ondes(d)
		if d:IsA("GuiObject") then
			local thisEntered = false
			local thisAdded = false
			local con0 = d.MouseEnter:Connect(function()
				thisEntered = true
				if (not thisAdded) and d.Active then
					activeEntered = activeEntered + 1
					thisAdded = true
				end
			end)
			local con1 = d.MouseLeave:Connect(function()
				thisEntered = false
				if thisAdded then
					activeEntered = activeEntered - 1
					thisAdded = false
				end
			end)
			local con2 = d:GetPropertyChangedSignal("Active"):Connect(function()
				if thisEntered then
					if thisAdded and not d.Active then
						activeEntered = activeEntered - 1
						thisAdded = false
					elseif d.Active and not thisAdded then
						activeEntered = activeEntered + 1
						thisAdded = true
					end
				end
			end)
			local con3 = nil
			con3 = d.AncestryChanged:Connect(function()
				if not d:IsDescendantOf(window) then
					if thisEntered then
						activeEntered = activeEntered - 1
					end
					con0:Disconnect()
					con1:Disconnect()
					con2:Disconnect()
					con3:Disconnect()
				end
			end)
		end
	end
	window.DescendantAdded:Connect(ondes)
	local des=window:GetDescendants()
	for i=1,#des do 
		ondes(des[i])
	end
end
Draggable(i1)

local others={}
for i,v in pairs(plrs:GetPlayers()) do
	if v~=lp then
		others[v]=true
	end
end
plrs.PlayerAdded:Connect(function(plr)
	others[plr]=true
end)
local function findplr(txt)
	if txt=="" then
		return nil
	end
	for v,_ in pairs(others) do
		if v.DisplayName==txt then
			return v
		end
	end
	for v,_ in pairs(others) do
		if v.Name==txt then
			return v
		end
	end
	local lower=slower(txt)
	for v,_ in pairs(others) do
		if slower(v.DisplayName)==lower then
			return v
		end
	end
	for v,_ in pairs(others) do
		if slower(v.Name)==lower then
			return v
		end
	end
	local l=#txt
	for v,_ in pairs(others) do
		if ssub(v.DisplayName,l,l)==txt then
			return v
		end
	end
	for v,_ in pairs(others) do
		if ssub(v.Name,l,l)==txt then
			return v
		end
	end
	for v,_ in pairs(others) do
		if slower(ssub(v.DisplayName,l,l))==lower then
			return v
		end
	end
	for v,_ in pairs(others) do
		if slower(ssub(v.Name,l,l))==lower then
			return v
		end
	end
	return nil
end
local target=nil
i4:GetPropertyChangedSignal("Text"):Connect(function()
	local txt=i4.Text
	target=findplr(txt)
	if target then
		if (target.DisplayName) and (target.DisplayName~="") and (target.DisplayName~=target.Name) then
			i7.Text=target.DisplayName.." @"..target.Name
		else
			i7.Text="@"..target.Name
		end
		i5.TextColor3=c3(0.301961,1,0) 
	else
		i7.Text=""
		i5.TextColor3=c3(0.55,0.55,0.55) 
	end
end)
plrs.PlayerRemoving:Connect(function(plr)
	others[plr]=nil
	if plr==target then
		target=nil
		i7.Text=""
		i5.TextColor3=c3(0.55,0.55,0.55) 
	end
end)
local notifyid=0
local function notify(txt)
	notifyid=notifyid+1
	local thisid=notifyid
	i6.Text=txt
	twait(2)
	if notifyid==thisid then
		i6.Text="ملاحظه لازم الاعب مايتحرك"
	end
end
local bringing=false
i5.MouseButton1Click:Connect(function()
	if bringing then
		bringing=false
		i5.Text="BRING"
		return
	end
	if not target then
		return
	end
	local c=lp.Character
	local c1=target.Character
	if not (c and c1) then
		return notify("no character")
	end
	if not (c:IsDescendantOf(ws) and c1:IsDescendantOf(ws)) then
		return notify("character not in workspace")
	end
	local hrp=gp(c,"HumanoidRootPart","BasePart")
	local hrp1=gp(c1,"HumanoidRootPart","BasePart")
	if not (hrp and hrp1) then
		return notify("no humanoidrootpart")
	end
	bringing=true
	i5.Text="تم السحب" 
	local from=hrp1.CFrame
	local fromP=from.Position
	local to=hrp.CFrame
	local toP=to.Position
	local mag=(fromP-toP).Magnitude-3
	local lv=cf(fromP,toP).LookVector
	local vel=0
	local pos=from.Position-v3_010*2
	toP=toP-v3_010*2

	local sine=osclock()
	local lastsine=sine
	local way=0
	local reachedmaxspeed=false
	while bringing and c:IsDescendantOf(ws) and c1:IsDescendantOf(ws) do
		sine=osclock()
		local deltaTime=sine-lastsine
		lastsine=sine
		if reachedmaxspeed then
			if mag-way<reachedmaxspeed then
				vel=vel-deltaTime*speeding
				if vel<0 then
					break
				end
			end
		else
			if way>mag/2 then
				vel=vel-deltaTime*speeding
				if vel<0 then
					break
				end
			else
				vel=vel+deltaTime*speeding
				if vel>maxspeed then
					reachedmaxspeed=way
					vel=maxspeed
				end
			end
		end
		way=way+vel*deltaTime
		if not hrp:IsGrounded() then
			hrp.CFrame=cf(pos+lv*way,toP)*off
			hrp.Velocity=lv*(vel+1)
			hrp.RotVelocity=v3_0
		end
		twait()
	end
	hrp.CFrame=to
	hrp.Velocity=v3_0
	hrp.RotVelocity=v3_0
	bringing=false
	i5.Text="سحب"
end)
local iscg,_=pcall(function()
	i8.Parent=game:FindFirstChildOfClass("CoreGui")
end)
if not iscg then
	i8.Parent=lp:FindFirstChildOfClass("PlayerGui")
end

game.StarterGui:SetCore("SendNotification",  {
 Title = "فعل ميزة محد يقدر يدفك";
 Text = "Enjoy(:";
 Icon = "";
 Duration = 5;
 Callback = NotificationBindable;
})

print("تم تشغيل الامر")
-- نهايه
end
end)

local player = game.Players.LocalPlayer
local chattedConnection = player.Chatted:Connect(function(message)
local keyword = "!فلينق" -- 
if string.sub(message, 1, #keyword) == keyword then
loadstring(game:HttpGet("https://raw.githubusercontent.com/0Ben1/fe./main/Fling%20GUI"))()
print("تم تشغيل الامر")
-- نهايه
end
end)

game.StarterGui:SetCore("SendNotification",  {
 Title = "العم N7R";
 Text = "تم تشغل السكربت";
 Icon = "";
 Duration = 5;
 Callback = NotificationBindable;
})
			
coroutine.wrap(QNWNII_fake_script)()

    else
        TextBox.PlaceholderText = "غلط يامطي "
        TextBox.Text = ""
        wait(1)
        TextBox.PlaceholderText = "حط مفتاح"
        TextBox.Text = ""
    end
end)
