-- Grow a Garden | Powerful Pet and Seed Spawner Script
-- Keyless, allows spawning powerful pets and seeds, and duplicating items.

local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local player = Players.LocalPlayer

-- Configuration: Add powerful pets and seeds here
local POWERFUL_PETS = {
    "Legendary Dragon",  -- Replace with actual powerful pet names
    "Mythical Unicorn",
    "Epic Phoenix"
}

local POWERFUL_SEEDS = {
    "Golden Seed",  -- Replace with actual powerful seed names
    "Diamond Seed",
    "Mystic Seed"
}

-- Function to get the SpawnPet remote event
local function getSpawnPetRemote()
    local remotes = ReplicatedStorage:FindFirstChild("Remotes")
    if remotes then
        return remotes:FindFirstChild("SpawnPet")
    end
    return nil
end

-- Function to get the SpawnSeed remote event
local function getSpawnSeedRemote()
    local remotes = ReplicatedStorage:FindFirstChild("Remotes")
    if remotes then
        return remotes:FindFirstChild("SpawnSeed")
    end
    return nil
end

-- Function to duplicate money
local function duplicateMoney(amount)
    local moneyRemote = ReplicatedStorage:FindFirstChild("Remotes"):FindFirstChild("DuplicateMoney")
    if moneyRemote then
        moneyRemote:FireServer(amount)
        print("Duplicated money: " .. amount)
    else
        warn("Money duplication remote not found!")
    end
end

-- Function to spawn powerful pets
local function spawnPowerfulPets()
    local spawnPetRemote = getSpawnPetRemote()
    if spawnPetRemote then
        for _, petName in ipairs(POWERFUL_PETS) do
            spawnPetRemote:FireServer(petName)
            print("Spawned pet: " .. petName)
            wait(0.5) -- Small delay to avoid server overload
        end
    else
        warn("SpawnPet remote not found!")
    end
end

-- Function to spawn powerful seeds
local function spawnPowerfulSeeds()
    local spawnSeedRemote = getSpawnSeedRemote()
    if spawnSeedRemote then
        for _, seedName in ipairs(POWERFUL_SEEDS) do
            spawnSeedRemote:FireServer(seedName)
            print("Spawned seed: " .. seedName)
            wait(0.5) -- Small delay to avoid server overload
        end
    else
        warn("SpawnSeed remote not found!")
    end
end

-- Main execution
spawnPowerfulPets()
spawnPowerfulSeeds()
duplicateMoney(1000000) -- Adjust the amount as needed

print("All powerful pets and seeds spawned, and money duplicated!")
