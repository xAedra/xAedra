getgenv().autotap = false;
getgenv().AutoRebirth = false;
getgenv().autoegg = false;


function dotap() 
    spawn(function()
        while autotap == true do
            game:GetService("ReplicatedStorage").Events.Click:FireServer()
            wait()
        end
    end)
end


function autorebirth()
    spawn(function()
        while AutoRebirth == true do
            local args = {[1] = 1}
            game:GetService("ReplicatedStorage").Events.Rebirth:FireServer(unpack(args))
            wait()
        end
    end)
end

function TpTo(placeCFrame)
    local plr = game.Players.LocalPlayer;
    if plr.Character then
        plr.Character.HumanoidRootPart.CFrame = placeCFrame;
    end
end
TpTo(game:GetService("Workspace")["Map 11"]["Frozen Tundra"].CFrame)



local library = loadstring(game:HttpGet(('https://raw.githubusercontent.com/AikaV3rm/UiLib/master/Lib.lua')))()

local w = library:CreateWindow("Aedra gui") 

local b = w:CreateFolder("Chaosit lisiy globus") 

local d = w:CreateFolder("Ura Tleports")

b:DestroyGui()



d:Button("Teleport to Tyndrachuchundra",function()
    TpTo(game:GetService("Workspace")["Map 11"]["Frozen Tundra"].CFrame)
end)

b:Toggle("Auto tap",function(bool)
    getgenv().autotap = bool
    print('Auto Tap is: ', bool);
    if bool then
        dotap();
    end
end)


b:Toggle("Auto rebirth",function(bool)
    getgenv().AutoRebirth = bool
    print(' Auto Rebirth is:', bool);
    if bool then
        autorebirth();
    end
end)

d:Button("Lava Wasteland",function()
    TpTo(game:GetService("Workspace").MapCenters["Lava Wasteland"].CFrame)
end)

d:Button("COVE Tp",function()
    TpTo(game:GetService("Workspace")["Map 12"]["Crystal Cove"].CFrame)
end)

d:Button("Desert TP",function()
    TpTo(game:GetService("Workspace").MapCenters["Decaying Desert"].CFrame)
end)

d:Button("Beach tp",function()
    TpTo(game:GetService("Workspace")["Map 11"]["Frozen Tundra"].CFrame)
end)

d:Button("Spawn tp",function()
    TpTo(game:GetService("Workspace")["Map 11"]["Frozen Tundra"].CFrame)
end)
