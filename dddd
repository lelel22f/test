--update v0.5 update for mobile executors and queue_on_teleport, filesystem unsurpported
if not game:IsLoaded() then
    game.Loaded:Wait()
end

if syn ~= nil and syn.queue_on_teleport ~= nil or queue_on_teleport ~= nil then
	local queue = syn.queue_on_teleport or queue_on_teleport
end

if isfile and readfile and writefile and queue_on_teleport and delfile and isfile("autorj-lastimsg.rj") then
    game.StarterGui:SetCore("SendNotification",{
        Title = "Auto Rejoind!",
        Text = "Message: \n"..readfile("autorj-lastimsg.rj"),
        Icon = "",
        Duration = 3
	})
    delfile("autorj-lastimsg.rj")
end

game:GetService("CoreGui").RobloxPromptGui.promptOverlay.ChildAdded:Connect(function(prompt)
    if prompt.Name == "ErrorPrompt" and prompt:FindFirstChild('MessageArea') and prompt.MessageArea:FindFirstChild("ErrorFrame") then
        spawn(function()
            if writefile and queue and readfile and isfile and delfile then
                writefile("autorj-lastimsg.rj", game.CoreGui.RobloxPromptGui.promptOverlay.ErrorPrompt.MessageArea.ErrorFrame.ErrorMessage.Text)
                queue([[loadstring(game:HttpGet("https://raw.githubusercontent.com/baechooYT/Just_Stop/main/autorj.lua", true))()]])
            end
            game.StarterGui:SetCore("SendNotification",{
                Title = "Auto Rejoining...",
                Text = "Rejoining...",
                Icon = "",
                Duration = math.huge
	        })
            while wait() do 
              if #game.Players:GetPlayers() <= 1 then
		           wait()
		           game:GetService('TeleportService'):Teleport(game.PlaceId, game.Players.LocalPlayer)
	           else
	               game:GetService('TeleportService'):TeleportToPlaceInstance(game.PlaceId, game.JobId, game.Players.LocalPlayer)
	           end
            end
        end)
    end
end)
