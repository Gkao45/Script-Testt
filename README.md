local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("PORN X HUB", "BloodTheme")
local Tab = Window:NewTab("Main")
local Section = Tab:NewSection("Autofram")
Section:NewToggle("Autofram", "ToggleInfo", function(state)
    _G.AutoFarm_Level = state
    _G.FastAttack = true
     
     
     
     
     
     
     
     
     
    function checklevel()
        local Level = game:GetService("Players").LocalPlayer.Data.Level.Value
        if Level == 10 or Level <= 15 then
            MON = "Bandit [Lv. 5]"
            QUESTTITLE = "Bandit"
            QUESTPOS = CFrame.new(1060.0158691406, 16.424287796021, 1547.9769287109)
            MONPOS = CFrame.new(1148.8698730469, 16.432844161987, 1630.5396728516)
            QUESTNAME = "BanditQuest1"
            QUESTNUMBER = 1
            SPAWNPOINT = "Default"
            SPAWNPOINTPOS = CFrame.new(973.96197509766, 16.273551940918, 1413.2775878906)
        end
    end
    Method = CFrame.new(0,19,0)
     
    spawn(function()
       while wait(3) do
           if Methodnow == 1 then
            Methodnow = 2
            Method = CFrame.new(0,19,0)
            else
            Methodnow = 1
            Method = CFrame.new(0,0,19)
           end
        end
    end)
     
    spawn(function()
       while wait() do
           if _G.WARP then
               game.Players.LocalPlayer.Character.HumanoidRootPart.Anchored = true
            else
                game.Players.LocalPlayer.Character.HumanoidRootPart.Anchored = false
            end
        end
    end)
     
    spawn(function()
        game:GetService("RunService").Heartbeat:Connect(function()
            if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") and _G.AutoFarm_Level then
                setfflag("HumanoidParallelRemoveNoPhysics", "False")
                setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
                game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
            end
        end)
    end)
     
     
    spawn(function()
        while wait() do
            if _G.AutoFarm_Level then
                pcall(function()
                    checklevel()
        
                    if not string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,QUESTTITLE) then
                        local args = {
                            [1] = "AbandonQuest"
                        }
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    end
                    if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
                        
                        if game:GetService("Players").LocalPlayer.Data.SpawnPoint.Value == SPAWNPOINT then
                            local args = {
                                [1] = "SetTeam",
                                [2] = "Pirates"
                            }
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            wait(0.5)
                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = QUESTPOS
                            wait(0.8)
                                local args = {
                                    [1] = "StartQuest",
                                    [2] = QUESTNAME,
                                    [3] = QUESTNUMBER
                                }
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            wait(0.8)
                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = MONPOS
                        else
                            _G.WARP = true
                            repeat 
                                wait()
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = SPAWNPOINTPOS
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                            until game:GetService("Players").LocalPlayer.Data.SpawnPoint.Value == SPAWNPOINT or _G.AutoFarm_Level == false
                            _G.WARP = false
                        end
                    end
                    for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                        for i2,v2 in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                            if v.Name == MON and v2.Name == MON then
                                v2.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame
                                v2.HumanoidRootPart.CanCollide = false
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * Method
                                sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
                            end
                        end
                    end
                end)
            end
        end
    end)
     
     
     
    spawn(function()
       game:GetService("RunService").RenderStepped:Connect(function()
        pcall(function()
            if _G.FastAttack and _G.AutoFarm_Level then
                local Combat = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
                local Cemara = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
                Cemara.CameraShakeInstance.CameraShakeState = {FadingIn = 3, FadingOut = 2, Sustained = 0, Inactive = 1}
                Combat.activeController.timeToNextAttack = 0
                Combat.activeController.hitboxMagnitude = 120
                Combat.activeController.increment = 3
            end
        end)
    end) 
    end)
     
     
    spawn(function()
       game:GetService("RunService").RenderStepped:Connect(function()
        pcall(function()
            if _G.AutoFarm_Level then
                game:GetService'VirtualUser':CaptureController()
                game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
            end
        end)
    end) 
    end)
end)



-----AutoFram2-------
Section:NewToggle("Autofram(2)", "Click For Autofram2...", function(state)
    _G.AutoFarm_Level = state
    _G.FastAttack = true
     
     
     
     
     
     
     
     
     
    function checklevel()
        local Level = game:GetService("Players").LocalPlayer.Data.Level.Value
        if Level == 10 or Level <= 15 then
            MON = "Monkey [Lv. 14]"
            QUESTTITLE = "Monkey"
            QUESTPOS = CFrame.new(-1599.7374267578125, 36.85213851928711, 153.44158935546875)
            MONPOS = CFrame.new(-1582.4119873046875, 22.852102279663086, -28.76823616027832)
            QUESTNAME = "JungleQuest"
            QUESTNUMBER = 1
            SPAWNPOINT = "Jungle"
            SPAWNPOINTPOS = CFrame.new(-1336.28955078125, 11.852882385253906, 496.2724609375)
        end
    end
    Method = CFrame.new(0,19,0)
     
    spawn(function()
       while wait(3) do
           if Methodnow == 1 then
            Methodnow = 2
            Method = CFrame.new(0,19,0)
            else
            Methodnow = 1
            Method = CFrame.new(0,0,19)
           end
        end
    end)
     
    spawn(function()
       while wait() do
           if _G.WARP then
               game.Players.LocalPlayer.Character.HumanoidRootPart.Anchored = true
            else
                game.Players.LocalPlayer.Character.HumanoidRootPart.Anchored = false
            end
        end
    end)
     
    spawn(function()
        game:GetService("RunService").Heartbeat:Connect(function()
            if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") and _G.AutoFarm_Level then
                setfflag("HumanoidParallelRemoveNoPhysics", "False")
                setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
                game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
            end
        end)
    end)
     
     
    spawn(function()
        while wait() do
            if _G.AutoFarm_Level then
                pcall(function()
                    checklevel()
        
                    if not string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,QUESTTITLE) then
                        local args = {
                            [1] = "AbandonQuest"
                        }
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    end
                    if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
                        
                        if game:GetService("Players").LocalPlayer.Data.SpawnPoint.Value == SPAWNPOINT then
                            local args = {
                                [1] = "SetTeam",
                                [2] = "Pirates"
                            }
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            wait(0.5)
                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = QUESTPOS
                            wait(0.8)
                                local args = {
                                    [1] = "StartQuest",
                                    [2] = QUESTNAME,
                                    [3] = QUESTNUMBER
                                }
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            wait(0.8)
                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = MONPOS
                        else
                            _G.WARP = true
                            repeat 
                                wait()
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = SPAWNPOINTPOS
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                            until game:GetService("Players").LocalPlayer.Data.SpawnPoint.Value == SPAWNPOINT or _G.AutoFarm_Level == false
                            _G.WARP = false
                        end
                    end
                    for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                        for i2,v2 in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                            if v.Name == MON and v2.Name == MON then
                                v2.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame
                                v2.HumanoidRootPart.CanCollide = false
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * Method
                                sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
                            end
                        end
                    end
                end)
            end
        end
    end)
     
     
     
    spawn(function()
       game:GetService("RunService").RenderStepped:Connect(function()
        pcall(function()
            if _G.FastAttack and _G.AutoFarm_Level then
                local Combat = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
                local Cemara = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
                Cemara.CameraShakeInstance.CameraShakeState = {FadingIn = 3, FadingOut = 2, Sustained = 0, Inactive = 1}
                Combat.activeController.timeToNextAttack = 0
                Combat.activeController.hitboxMagnitude = 120
                Combat.activeController.increment = 3
            end
        end)
    end) 
    end)
     
     
    spawn(function()
       game:GetService("RunService").RenderStepped:Connect(function()
        pcall(function()
            if _G.AutoFarm_Level then
                game:GetService'VirtualUser':CaptureController()
                game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
            end
        end)
    end) 
    end)
end)




------Autofram3------
Section:NewToggle("Autofram(3)", "Click For Autofram3", function(state)
    _G.AutoFarm_Level = state
    _G.FastAttack = true
     
     
     
     
     
     
     
     
     
    function checklevel()
        local Level = game:GetService("Players").LocalPlayer.Data.Level.Value
        if Level == 15 or Level <= 35 then
            MON = "Gorilla [Lv. 20]"
            QUESTTITLE = "Gorilla"
            QUESTPOS = CFrame.new(-1599.4398193359375, 36.85213851928711, 153.53672790527344)
            MONPOS = CFrame.new(-1218.9427490234375, 6.220604419708252, -461.67633056640625)
            QUESTNAME = "JungleQuest"
            QUESTNUMBER = 2
            SPAWNPOINT = "Jungle"
            SPAWNPOINTPOS = CFrame.new(-1336.28955078125, 11.852882385253906, 496.2724609375)
        end
    end
    Method = CFrame.new(0,19,0)
     
    spawn(function()
       while wait(3) do
           if Methodnow == 1 then
            Methodnow = 2
            Method = CFrame.new(0,19,0)
            else
            Methodnow = 1
            Method = CFrame.new(0,0,19)
           end
        end
    end)
     
    spawn(function()
       while wait() do
           if _G.WARP then
               game.Players.LocalPlayer.Character.HumanoidRootPart.Anchored = true
            else
                game.Players.LocalPlayer.Character.HumanoidRootPart.Anchored = false
            end
        end
    end)
     
    spawn(function()
        game:GetService("RunService").Heartbeat:Connect(function()
            if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") and _G.AutoFarm_Level then
                setfflag("HumanoidParallelRemoveNoPhysics", "False")
                setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
                game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
            end
        end)
    end)
     
     
    spawn(function()
        while wait() do
            if _G.AutoFarm_Level then
                pcall(function()
                    checklevel()
        
                    if not string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,QUESTTITLE) then
                        local args = {
                            [1] = "AbandonQuest"
                        }
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    end
                    if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
                        
                        if game:GetService("Players").LocalPlayer.Data.SpawnPoint.Value == SPAWNPOINT then
                            local args = {
                                [1] = "SetTeam",
                                [2] = "Pirates"
                            }
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            wait(0.5)
                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = QUESTPOS
                            wait(0.8)
                                local args = {
                                    [1] = "StartQuest",
                                    [2] = QUESTNAME,
                                    [3] = QUESTNUMBER
                                }
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            wait(0.8)
                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = MONPOS
                        else
                            _G.WARP = true
                            repeat 
                                wait()
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = SPAWNPOINTPOS
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                            until game:GetService("Players").LocalPlayer.Data.SpawnPoint.Value == SPAWNPOINT or _G.AutoFarm_Level == false
                            _G.WARP = false
                        end
                    end
                    for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                        for i2,v2 in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                            if v.Name == MON and v2.Name == MON then
                                v2.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame
                                v2.HumanoidRootPart.CanCollide = false
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * Method
                                sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
                            end
                        end
                    end
                end)
            end
        end
    end)
     
     
     
    spawn(function()
       game:GetService("RunService").RenderStepped:Connect(function()
        pcall(function()
            if _G.FastAttack and _G.AutoFarm_Level then
                local Combat = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
                local Cemara = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
                Cemara.CameraShakeInstance.CameraShakeState = {FadingIn = 3, FadingOut = 2, Sustained = 0, Inactive = 1}
                Combat.activeController.timeToNextAttack = 0
                Combat.activeController.hitboxMagnitude = 120
                Combat.activeController.increment = 3
            end
        end)
    end) 
    end)
     
     
    spawn(function()
       game:GetService("RunService").RenderStepped:Connect(function()
        pcall(function()
            if _G.AutoFarm_Level then
                game:GetService'VirtualUser':CaptureController()
                game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
            end
        end)
    end) 
    end)
end)

------Autofram4-------
Section:NewToggle("Autofram(4)", "Click For Autofram4", function(state)
    _G.AutoFarm_Level = state
    _G.FastAttack = true
     
     
     
     
     
     
     
     
     
    function checklevel()
        local Level = game:GetService("Players").LocalPlayer.Data.Level.Value
        if Level == 25 or Level <= 40 then
            MON = "Pirate [Lv. 35]"
            QUESTTITLE = "Pirate"
            QUESTPOS = CFrame.new(-1140.4827880859375, 4.752061367034912, 3829.623291015625)
            MONPOS = CFrame.new(-1198.0413818359375, 4.752061367034912, 3914.32177734375)
            QUESTNAME = "BuggyQuest1"
            QUESTNUMBER = 1
            SPAWNPOINT = "Pirate"
            SPAWNPOINTPOS = CFrame.new(-1188.3966064453125, 4.751573085784912, 3815.531494140625)
        end
    end
    Method = CFrame.new(0,19,0)
     
    spawn(function()
       while wait(3) do
           if Methodnow == 1 then
            Methodnow = 2
            Method = CFrame.new(0,19,0)
            else
            Methodnow = 1
            Method = CFrame.new(0,0,19)
           end
        end
    end)
     
    spawn(function()
       while wait() do
           if _G.WARP then
               game.Players.LocalPlayer.Character.HumanoidRootPart.Anchored = true
            else
                game.Players.LocalPlayer.Character.HumanoidRootPart.Anchored = false
            end
        end
    end)
     
    spawn(function()
        game:GetService("RunService").Heartbeat:Connect(function()
            if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") and _G.AutoFarm_Level then
                setfflag("HumanoidParallelRemoveNoPhysics", "False")
                setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
                game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
            end
        end)
    end)
     
     
    spawn(function()
        while wait() do
            if _G.AutoFarm_Level then
                pcall(function()
                    checklevel()
        
                    if not string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,QUESTTITLE) then
                        local args = {
                            [1] = "AbandonQuest"
                        }
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    end
                    if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
                        
                        if game:GetService("Players").LocalPlayer.Data.SpawnPoint.Value == SPAWNPOINT then
                            local args = {
                                [1] = "SetTeam",
                                [2] = "Pirates"
                            }
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            wait(0.5)
                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = QUESTPOS
                            wait(0.8)
                                local args = {
                                    [1] = "StartQuest",
                                    [2] = QUESTNAME,
                                    [3] = QUESTNUMBER
                                }
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            wait(0.8)
                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = MONPOS
                        else
                            _G.WARP = true
                            repeat 
                                wait()
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = SPAWNPOINTPOS
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                            until game:GetService("Players").LocalPlayer.Data.SpawnPoint.Value == SPAWNPOINT or _G.AutoFarm_Level == false
                            _G.WARP = false
                        end
                    end
                    for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                        for i2,v2 in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                            if v.Name == MON and v2.Name == MON then
                                v2.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame
                                v2.HumanoidRootPart.CanCollide = false
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * Method
                                sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
                            end
                        end
                    end
                end)
            end
        end
    end)
     
     
     
    spawn(function()
       game:GetService("RunService").RenderStepped:Connect(function()
        pcall(function()
            if _G.FastAttack and _G.AutoFarm_Level then
                local Combat = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
                local Cemara = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
                Cemara.CameraShakeInstance.CameraShakeState = {FadingIn = 3, FadingOut = 2, Sustained = 0, Inactive = 1}
                Combat.activeController.timeToNextAttack = 0
                Combat.activeController.hitboxMagnitude = 120
                Combat.activeController.increment = 3
            end
        end)
    end) 
    end)
     
     
    spawn(function()
       game:GetService("RunService").RenderStepped:Connect(function()
        pcall(function()
            if _G.AutoFarm_Level then
                game:GetService'VirtualUser':CaptureController()
                game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
            end
        end)
    end) 
    end)
end)



--------Teleport----------
local Tab = Window:NewTab("Teleport")
local Teleport = Tab:NewSection("Teleport")
Teleport:NewButton("Windmill", "Click For Tp", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(882.782104, 16.5144901, 1428.34473, -0.0472464859, 1.09926091e-07, 0.998883247, -1.12407896e-08, 1, -1.10580665e-07, -0.998883247, -1.6452784e-08, -0.0472464859)
end)

------Teleport2-------
Teleport:NewButton("Town", "Click For TP", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-646.266113, 7.85223341, 1572.86658, 0.295276791, -3.65355959e-08, -0.955411732, 1.08935872e-07, 1, -4.57327376e-09, 0.955411732, -1.02728237e-07, 0.295276791)
end)

------Teleport3--------
Teleport:NewButton("Jungle", "Click For Tp", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1612.81726, 32.200058, 164.844666, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
end)

-------Teleport4-----
Teleport:NewButton("Pirate", "Click For TP", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1191.05994, 2.25620151, 3905.40845, 0.989284515, 0.000104441031, -0.146000534, -0.000146340171, 0.99999994, -0.000276238978, 0.14600049, 0.000294644677, 0.989284456)
end)


--------Misc-------
local Tab = Window:NewTab("Misc")
local Misc = Tab:NewSection("FastAttack")
Misc:NewToggle("FastAttack", "Click to use FastAttack", function(state)
local Fast = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
local CameraShaker = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
_G.Fastattack = state -- true\false
game:GetService("RunService").RenderStepped:Connect(function()
    pcall(function()
        if _G.Fastattack then
Fast.activeController.timeToNextAttack = 0
Fast.activeController.hitboxMagnitude = 50
game:GetService'VirtualUser':CaptureController()
game:GetService'VirtualUser':Button1Down(Vector2.new(686, 352))
CameraShaker.CameraShakeInstance.CameraShakeState = {FadingIn = 3, FadingOut = 2, Sustained = 0, Inactive = 1}
end
end)
end)
end)

-------Misc2---------

Misc:NewLabel("Bringmob")
Misc:NewToggle("bringmob", "Click to use bringmob", function(state)
_G.bringmob = state
while _G.bringmob do wait()
    pcall(function()
for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
for x,y in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
if v.Name == "Monkey [Lv. 14], " then
    if y.Name == "Monkey [Lv. 14]" then
   v.HumanoidRootPart.CFrame = y.HumanoidRootPart.CFrame
   v.HumanoidRootPart.Size = Vector3.new(60,60,60)
   y.HumanoidRootPart.Size = Vector3.new(60,60,60)
   v.HumanoidRootPart.Transparency = 1
   v.HumanoidRootPart.CanCollide = false
   y.HumanoidRootPart.CanCollide = false
   v.Humanoid.WalkSpeed = 0
   y.Humanoid.WalkSpeed = 0
   v.Humanoid.JumpPower = 0
   y.Humanoid.JumpPower = 0
   if sethiddenproperty then
     sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
end
end
end
end
end
end)
end
end)
Misc:NewKeybind("KeybindText", "KeybindInfo", Enum.KeyCode.RightControl, function()
	Library:ToggleUI()
end)

-------Misc3--------
local Misc = Tab:NewSection("Auto Equip")

local Weaponlist = {}
local Weapon = nil

for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
    table.insert(Weaponlist,v.Name)
end

Misc:NewDropdown("select weapon", " ", Weaponlist, function(currentOption)
    Weapon = currentOption
end)

Misc:NewToggle("Auto Equip", " ", function(a)
AutoEquiped = a
end)

spawn(function()
while wait() do
if AutoEquiped then
pcall(function()
game.Players.LocalPlayer.Character.Humanoid:EquipTool(game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(Weapon))
end)
end
end
end)

--------ESP-RAID---------
local Tab = Window:NewTab("ESP-RAID")
local GG = Tab:NewSection("ESP-RAID")
GG:NewToggle("Kill Aura", "Click To Kill Aura", function(state)
    for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
        if v.ClassName == "Model" then
            v.Humanoid.Health = die
        end
        end
end)

--------ESP-------
local PQ = Tab:NewSection("ESP Players")
PQ:NewToggle("ESP", "Click For Esp Players", function(state)
    while wait() do
        pcall(function()
          for i,v in pairs(game.Players:GetChildren()) do
               if not v.Character.Head:FindFirstChild("ESP") then
                   local BillboardGui = Instance.new("BillboardGui")
                   local TextLabel = Instance.new("TextLabel")
                   BillboardGui.Parent = v.Character.Head
                   BillboardGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
                   BillboardGui.Active = true
                   BillboardGui.Name = "ESP"
                   BillboardGui.AlwaysOnTop = true
                   BillboardGui.LightInfluence = 1.000
                   BillboardGui.Size = UDim2.new(0, 200, 0, 50)
                   BillboardGui.StudsOffset = Vector3.new(0, 2.5, 0)
                   TextLabel.Parent = BillboardGui
                   TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                   TextLabel.BackgroundTransparency = 1.000
                   TextLabel.Size = UDim2.new(0, 200, 0, 50)
                   TextLabel.Font = Enum.Font.GothamBold
                   TextLabel.Text = v.Name
                   TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
                   TextLabel.TextScaled = true
                   TextLabel.TextSize = 14.000
                   TextLabel.TextStrokeTransparency = 0.000
                   TextLabel.TextWrapped = true
               end
           end
       end) 
   end
end)

------ESP Devilfruit------
PQ:NewToggle("ESP-Devilfruit", "ToggleInfo", function(state)
    while wait() do
        pcall(function()
          for i,v in pairs(game:GetService("Workspace")["_WorldOrigin"].FruitSpawns:GetChildren()) do
               if not v.Character.Head:FindFirstChild("ESP") then
                   local BillboardGui = Instance.new("BillboardGui")
                   local TextLabel = Instance.new("TextLabel")
                   BillboardGui.Parent = v.Character.Head
                   BillboardGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
                   BillboardGui.Active = true
                   BillboardGui.Name = "ESP"
                   BillboardGui.AlwaysOnTop = true
                   BillboardGui.LightInfluence = 1.000
                   BillboardGui.Size = UDim2.new(0, 200, 0, 50)
                   BillboardGui.StudsOffset = Vector3.new(0, 2.5, 0)
                   TextLabel.Parent = BillboardGui
                   TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                   TextLabel.BackgroundTransparency = 1.000
                   TextLabel.Size = UDim2.new(0, 200, 0, 50)
                   TextLabel.Font = Enum.Font.GothamBold
                   TextLabel.Text = v.Name
                   TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
                   TextLabel.TextScaled = true
                   TextLabel.TextSize = 14.000
                   TextLabel.TextStrokeTransparency = 0.000
                   TextLabel.TextWrapped = true
               end
           end
       end) 
   end
end)
