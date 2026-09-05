getgenv().Resolution = { [".gg/scripters"] = 0.8955 }

local Camera = workspace.CurrentCamera

-- Clear old connections to prevent multiple loop bugs.
if getgenv().ResolutionConnection then
    getgenv().ResolutionConnection:Disconnect()
end

getgenv().ResolutionConnection = game:GetService("RunService").RenderStepped:Connect(function()
    Camera.CFrame = Camera.CFrame * CFrame.new(0, 0, 0, 1, 0, 0, 0, getgenv().Resolution[".gg/scripters"], 0, 0, 0, 1)
end)

getgenv().gg_scripters = "1Zeroq"
