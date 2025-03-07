# Dandy-s-world-
Spaw Twisted only main
function spawnAllTwistedNearPlayer(player)
    local twistedTypes = {
        "Astro", 
        "Vee", 
        "Shelly", 
        "Sprout", 
        "Pebble", 
        "Dandy"
    }

    function spawnTwisted(twistedType, position)
        local twisted = Instance.new(twistedType)
        twisted.Position = position
        twisted.Parent = workspace
    end

    local spawnPosition = player.Character.HumanoidRootPart.Position + Vector3.new(5, 0, 0)

    for _, twistedType in ipairs(twistedTypes) do
        spawnTwisted(twistedType, spawnPosition)
        spawnPosition = spawnPosition + Vector3.new(5, 0, 0)
    end
end

game.Players.PlayerAdded:Connect(function(player)
    player.CharacterAdded:Connect(function()
        spawnAllTwistedNearPlayer(player)
    end)
end)
