local Players = game:GetService("Players")
local TweenService = game:GetService("TweenService")
local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

-- Jungle theme colors
local jungleGreen = Color3.fromRGB(34, 139, 34)
local darkGreen = Color3.fromRGB(0, 100, 0)
local leafGreen = Color3.fromRGB(107, 142, 35)
local brown = Color3.fromRGB(101, 67, 33)
local vineGreen = Color3.fromRGB(0, 128, 0)

-- Main ScreenGui
local screenGui = Instance.new("ScreenGui")
screenGui.Name = "TZSKeySystem"
screenGui.Parent = playerGui
screenGui.ResetOnSpawn = false

-- Jungle Background
local background = Instance.new("Frame")
background.Name = "Background"
background.Size = UDim2.new(1, 0, 1, 0)
background.Position = UDim2.new(0, 0, 0, 0)
background.BackgroundColor3 = jungleGreen
background.BorderSizePixel = 0
background.Parent = screenGui

-- Jungle vines pattern
local vine1 = Instance.new("Frame")
vine1.Size = UDim2.new(0, 50, 0.3, 0)
vine1.Position = UDim2.new(0.1, 0, 0.1, 0)
vine1.BackgroundColor3 = vineGreen
vine1.BorderSizePixel = 0
vine1.Parent = background
local vine1Corner = Instance.new("UICorner")
vine1Corner.CornerRadius = UDim.new(0, 10)
vine1Corner.Parent = vine1

local vine2 = Instance.new("Frame")
vine2.Size = UDim2.new(0, 30, 0.25, 0)
vine2.Position = UDim2.new(0.85, 0, 0.7, 0)
vine2.BackgroundColor3 = vineGreen
vine2.BorderSizePixel = 0
vine2.Parent = background
local vine2Corner = Instance.new("UICorner")
vine2Corner.CornerRadius = UDim.new(0, 8)
vine2Corner.Parent = vine2

-- Leaves decoration
local leaf1 = Instance.new("Frame")
leaf1.Size = UDim2.new(0, 80, 0, 40)
leaf1.Position = UDim2.new(0.3, 0, 0.05, 0)
leaf1.BackgroundColor3 = leafGreen
leaf1.BorderSizePixel = 0
leaf1.Parent = background
local leaf1Corner = Instance.new("UICorner")
leaf1Corner.CornerRadius = UDim.new(0, 20)
leaf1Corner.Parent = leaf1

-- Key Frame
local keyFrame = Instance.new("Frame")
keyFrame.Name = "KeyFrame"
keyFrame.Size = UDim2.new(0.4, 0, 0.5, 0)
keyFrame.Position = UDim2.new(0.3, 0, 0.25, 0)
keyFrame.BackgroundColor3 = darkGreen
keyFrame.BorderSizePixel = 0
keyFrame.Parent = background
local keyCorner = Instance.new("UICorner")
keyCorner.CornerRadius = UDim.new(0, 25)
keyCorner.Parent = keyFrame

-- Wood border effect
local woodBorder = Instance.new("Frame")
woodBorder.Size = UDim2.new(1, 6, 1, 6)
woodBorder.Position = UDim2.new(0, -3, 0, -3)
woodBorder.BackgroundColor3 = brown
woodBorder.BorderSizePixel = 0
woodBorder.ZIndex = keyFrame.ZIndex - 1
woodBorder.Parent = keyFrame
local woodCorner = Instance.new("UICorner")
woodCorner.CornerRadius = UDim.new(0, 28)
woodCorner.Parent = woodBorder

-- Title
local title = Instance.new("TextLabel")
title.Name = "Title"
title.Size = UDim2.new(1, 0, 0.2, 0)
title.Position = UDim2.new(0, 0, 0, 0)
title.BackgroundTransparency = 1
title.Text = "🌿 TZS JUNGLE KEY 🌿"
title.TextColor3 = Color3.new(1, 1, 1)
title.TextScaled = true
title.Font = Enum.Font.SourceSansBold
title.Parent = keyFrame

-- Key input box
local keyBox = Instance.new("TextBox")
keyBox.Name = "KeyBox"
keyBox.Size = UDim2.new(0.85, 0, 0.25, 0)
keyBox.Position = UDim2.new(0.075, 0, 0.35, 0)
keyBox.BackgroundColor3 = Color3.new(1, 1, 1)
keyBox.BorderSizePixel = 0
keyBox.Text = ""
keyBox.PlaceholderText = "Enter jungle key..."
keyBox.TextColor3 = darkGreen
keyBox.PlaceholderColor3 = Color3.fromRGB(150, 150, 150)
keyBox.TextScaled = true
keyBox.Font = Enum.Font.SourceSans
keyBox.Parent = keyFrame
local keyBoxCorner = Instance.new("UICorner")
keyBoxCorner.CornerRadius = UDim.new(0, 15)
keyBoxCorner.Parent = keyBox

-- Enter button
local enterButton = Instance.new("TextButton")
enterButton.Name = "EnterButton"
enterButton.Size = UDim2.new(0.85, 0, 0.2, 0)
enterButton.Position = UDim2.new(0.075, 0, 0.65, 0)
enterButton.BackgroundColor3 = leafGreen
enterButton.BorderSizePixel = 0
enterButton.Text = "🌱 ENTER JUNGLE 🌱"
enterButton.TextColor3 = Color3.new(1, 1, 1)
enterButton.TextScaled = true
enterButton.Font = Enum.Font.SourceSansBold
enterButton.Parent = keyFrame
local enterCorner = Instance.new("UICorner")
enterCorner.CornerRadius = UDim.new(0, 15)
enterCorner.Parent = enterButton

-- Unlock function
local function unlock()
    keyFrame:TweenPosition(UDim2.new(0.3, 0, 2, 0), "Out", "Quad", 0.5, true)
    wait(0.5)
    
    -- Main script loader (REPLACE WITH YOUR ACTUAL SCRIPT HERE)
    local mainScript = [[
-- 🔥 TZS MALE MAIN SCRIPT 🔥
-- Put your actual exploits/hacks here
print("🌿 TZS MALE UNLOCKED 🌿")
-- Example: game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 100
-- Add your cheats below
    ]]
    
    loadstring(mainScript)()
    
    -- Success message
    local successLabel = Instance.new("TextLabel")
    successLabel.Size = UDim2.new(0.6, 0, 0.15, 0)
    successLabel.Position = UDim2.new(0.2, 0, 0.4, 0)
    successLabel.BackgroundTransparency = 1
    successLabel.Text = "✅ TZS JUNGLE ACCESS GRANTED"
    successLabel.TextColor3 = Color3.new(1, 1, 1)
    successLabel.TextScaled = true
    successLabel.Font = Enum.Font.SourceSansBold
    successLabel.Parent = background
    successLabel:TweenSize(UDim2.new(0, 400, 0, 60), "Out", "Quad", 0.3, true)
end

-- Button click
enterButton.MouseButton1Click:Connect(function()
    if keyBox.Text == "sigmamale" then
        unlock()
    else
        keyBox.Text = ""
        keyBox.PlaceholderText = "❌ Wrong key, TZS..."
    end
end)

-- Enter key support
keyBox.FocusLost:Connect(function(enterPressed)
    if enterPressed then
        if keyBox.Text == "sigmamale" then
            unlock()
        else
            keyBox.Text = ""
            keyBox.PlaceholderText = "❌ Wrong key, TZS..."
        end
    end
end)

-- Animations
keyFrame:TweenSize(UDim2.new(0.45, 0, 0.55, 0), "Out", "Back", 0.8, true)
enterButton.MouseEnter:Connect(function()
    enterButton:TweenSize(UDim2.new(0.9, 0, 0.22, 0), "Out", "Quad", 0.2, true)
end)
enterButton.MouseLeave:Connect(function()
    enterButton:TweenSize(UDim2.new(0.85, 0, 0.2, 0), "Out", "Quad", 0.2, true)
end)
