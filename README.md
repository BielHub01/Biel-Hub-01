lua
if game.PlaceId == 2753915549 then
World1 = true
elseif game.PlaceId == 4442272183 then
World2 = true
elseif game.PlaceId == 7449423635 then
World3 = true
else
game:GetService("Players").LocalPlayer:Kick("Do not Support, Please wait...")
end

function rollFruit()
local player = game:GetService("Players").LocalPlayer
local fruitDealer = game.Workspace:FindFirstChild("Blox Fruit Dealer")
if fruitDealer then
player.Character.HumanoidRootPart.CFrame = fruitDealer.HumanoidRootPart.CFrame
wait(1)
game:GetService("VirtualUser"):CaptureController()
game:GetService("VirtualUser"):Button1Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
wait(1)
local dialog = fruitDealer:FindFirstChild("Dialog")
if dialog then
for _, option in pairs(dialog:GetChildren()) do
if option:IsA("TextButton") and option.Text == "Random Fruit" then
option:Activate()
wait(1)
local confirm = dialog:FindFirstChild("Confirm")
if confirm then
confirm:Activate()
end
end
end
end
end
end

function autoRollFruit()
while wait(3600) do -- roletar a cada 1 hora
rollFruit()
end
end

autoRollFruit()
