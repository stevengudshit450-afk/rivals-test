local UIS = game:GetService("UserInputService")
local camera = game.Workspace.CurrentCamera

-- get the closest player
function getClosest()
    local closestDistance = math.huge
    local closestPlayer = nil
    for i, v in pairs(game.Players:GetChildren()) do
        if v ~= game.Players.LocalPlayer and v.Team ~= game.Players.LocalPlayer.Team then
            local distance = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v.Character.HumanoidRootPart.Position).magnitude
            if distance < closestDistance then
                closestDistance = distance
                closestPlayer = v
            end
        end
    end
    return closestPlayer
end

-- starts the loop
UIS.InputBegan:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton2 then
        g_aim = true
        while wait() do
            camera.CFrame = CFrame.new(camera.CFrame.Position, getClosest().Character.Head.Position)
            if g_aim == false then return end
        end
    end
end)

-- stops the loop
UIS.InputEnded:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton2 then
        g_aim = false
    end
end)
