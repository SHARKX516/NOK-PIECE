

local mobs = {} 
getgenv().mob = nil 

-- MOBS
for _,v in pairs(game:GetService("Workspace").Lives:GetChildren()) do
    insert = true 
    for _,v2 in pairs(mobs) do if v2 == v.Name then insert = false end end 
    if insert then table.insert(mobs, v.Name) end 
end
-- CREDIT Kavo Libary

local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("NOK PIECE l SHARK X HUB", "DarkTheme") 

-- auto farm
local Main = Window:NewTab("Main")
local MobFarmSection = Main:NewSection("[ FARM MOB ]")

local mobdropdown = MobFarmSection:NewDropdown("Choose Mob", "Chooses the mob to autofarm", mobs, function(v)
    getgenv().mob = v
end)

MobFarmSection:NewToggle("Start Mob Farm", "Toggles the autofarming of the mobs", function(v)
    getgenv().autofarmmobs = v
    while wait() do
        if getgenv().autofarmmobs == false then return end 
        if getgenv().mob == nil then 
            game.StarterGui:SetCore("SendNotification", {
                Title = "!! FAIL !!", 
                Text = "Please choose your MOBS",
                Icon = "",
                Duration = 2.5
            })
            getgenv().autofarmmobs = false
            return
        end
        local mob = game:GetService("Workspace").Lives:FindFirstChild(getgenv().mob)
        if mob == nil then
            game.StarterGui:SetCore("SendNotification", { 
                Title = "Info!",
                Text = "There is currently no spawned mobs of this type!\nJust wait until they spawn", 
                Icon = "", 
                Duration = 2.5
            })
            while wait() do 
                wait() 
                if getgenv().autofarmmobs == false then return end 
                if game:GetService("Workspace").Lives:FindFirstChild(getgenv().mob) ~= nil then break; end
            end 
        else
            local mob2 = mob
            while wait() do
                mob = game:GetService("Workspace").Lives:FindFirstChild(getgenv().mob)
                if mob ~= mob2 then break; end
                if getgenv().autofarmmobs == false then return end
                if mob ~= nil then
                    if mob:FindFirstChild("Humanoid") then
                        if mob.Humanoid.Health == 0 then wait(0.1) mob:Destroy() break; end 
                    end
                    if mob:FindFirstChild("HumanoidRootPart") then
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = mob.HumanoidRootPart.CFrame * CFrame.new(0,0,2) 
                    end
                end
                wait() 
            end
        end
    end
end)

local Teleport = Window:NewTab("Teleport")
local TeleportSection = Teleport:NewSection("[ TELEPORT ISLAND ]")

TeleportSection:NewButton("RANDOM FRUIT", "Teleport to RANDOM FRUIT", function()
    tweenService, tweenInfo = game:GetService("TweenService"), TweenInfo.new(10, Enum.EasingStyle.Linear)
tween = tweenService:Create(game:GetService("Players")["LocalPlayer"].Character.HumanoidRootPart, tweenInfo, {CFrame = CFrame.new(123.794182, -78.0028839, -588.832275, -0.0349288881, -5.66855783e-16, 0.999389827, -1.07238119e-15, 1, 5.29721911e-16, -0.999389827, -1.05322427e-15, -0.0349288881)})
tween:Play()
end)

TeleportSection:NewButton("FRIST ISLAND", "Teleport to FRIST ISLAND", function()
    tweenService, tweenInfo = game:GetService("TweenService"), TweenInfo.new(10, Enum.EasingStyle.Linear)
tween = tweenService:Create(game:GetService("Players")["LocalPlayer"].Character.HumanoidRootPart, tweenInfo, {CFrame = CFrame.new(201.134583, -53.8900757, -607.288574, 0.994523704, 3.96363582e-08, -0.104510307, -4.07126173e-08, 1, -8.16480128e-09, 0.104510307, 1.23749775e-08, 0.994523704)})
tween:Play()
end)

TeleportSection:NewButton("BUGGY ISLAND", "Teleport to BUGGY ISLAND", function()
    tweenService, tweenInfo = game:GetService("TweenService"), TweenInfo.new(10, Enum.EasingStyle.Linear)
tween = tweenService:Create(game:GetService("Players")["LocalPlayer"].Character.HumanoidRootPart, tweenInfo, {CFrame = CFrame.new(-2512.30859, -74.1154404, 631.249817, 0.999828815, -2.21581278e-11, 0.0185024552, 2.60859528e-10, 1, -1.28986528e-08, -0.0185024552, 1.29012712e-08, 0.999828815)})
tween:Play()
end)

TeleportSection:NewButton("ARLONG ISLAND", "Teleport to ARLONG ISLAND", function()
    tweenService, tweenInfo = game:GetService("TweenService"), TweenInfo.new(10, Enum.EasingStyle.Linear)
tween = tweenService:Create(game:GetService("Players")["LocalPlayer"].Character.HumanoidRootPart, tweenInfo, {CFrame = CFrame.new(-2606.29395, -84.2315063, -2661.0979, 0.0347572677, -7.42569668e-08, -0.999395609, 7.61554588e-08, 1, -7.16532824e-08, 0.999395609, -7.3619006e-08, 0.0347572677)})
tween:Play()
end)

TeleportSection:NewButton("MARINE ISLAND", "Teleport to MARINE ISLAND", function()
    tweenService, tweenInfo = game:GetService("TweenService"), TweenInfo.new(10, Enum.EasingStyle.Linear)
tween = tweenService:Create(game:GetService("Players")["LocalPlayer"].Character.HumanoidRootPart, tweenInfo, {CFrame = CFrame.new(-53.6844406, -73.7345047, 3469.33618, 0.999949276, 5.83209321e-08, 0.0100664552, -5.89631242e-08, 1, 6.34967918e-08, -0.0100664552, -6.40871249e-08, 0.999949276)})
tween:Play()
end)

TeleportSection:NewButton("baratie", "Teleport to baratie", function()
    tweenService, tweenInfo = game:GetService("TweenService"), TweenInfo.new(10, Enum.EasingStyle.Linear)
tween = tweenService:Create(game:GetService("Players")["LocalPlayer"].Character.HumanoidRootPart, tweenInfo, {CFrame = CFrame.new(-352.093933, -75.8125381, -5712.83105, 0.728784323, 0, -0.684743404, 0, 1, 0, 0.684743404, 0, 0.728784323)})
tween:Play()
end)

TeleportSection:NewButton("PYRAMID ISLAND", "Teleport to PYRAMID ISLAND", function()
    tweenService, tweenInfo = game:GetService("TweenService"), TweenInfo.new(10, Enum.EasingStyle.Linear)
tween = tweenService:Create(game:GetService("Players")["LocalPlayer"].Character.HumanoidRootPart, tweenInfo, {CFrame = CFrame.new(-5240.06201, -67.6391296, 4386.29053, 0.999958515, -2.95429563e-05, -0.00910709053, 2.95056543e-05, 1, -4.23034408e-06, 0.00910709053, 3.96146334e-06, 0.999958515)})
tween:Play()
end)

TeleportSection:NewButton("PYRAMID ISLAND", "Teleport to PYRAMID ISLAND", function()
    tweenService, tweenInfo = game:GetService("TweenService"), TweenInfo.new(10, Enum.EasingStyle.Linear)
tween = tweenService:Create(game:GetService("Players")["LocalPlayer"].Character.HumanoidRootPart, tweenInfo, {CFrame = CFrame.new(-5240.06201, -67.6391296, 4386.29053, 0.999958515, -2.95429563e-05, -0.00910709053, 2.95056543e-05, 1, -4.23034408e-06, 0.00910709053, 3.96146334e-06, 0.999958515)})
tween:Play()
end)

-- UPDATE MOBS

game:GetService("Workspace").Lives.ChildAdded:Connect(function() 
    for _,v2 in pairs(mobs) do table.remove(mobs, _) end
    
    for _,v in pairs(game:GetService("Workspace").Lives:GetChildren()) do
        insert = true 
        for _,v2 in pairs(mobs) do if v2 == v.Name then insert = false end end
        if insert then table.insert(mobs, v.Name) end 
    end
    mobdropdown:Refresh(mobs)
end)

game:GetService("Workspace").Lives.ChildRemoved:Connect(function() 
    for _,v2 in pairs(mobs) do table.remove(mobs, _) end 
    
    for _,v in pairs(game:GetService("Workspace").Lives:GetChildren()) do 
        insert = true 
        for _,v2 in pairs(mobs) do if v2 == v.Name then insert = false end end 
        if insert then table.insert(mobs, v.Name) end 
    end
    mobdropdown:Refresh(mobs)
end)
