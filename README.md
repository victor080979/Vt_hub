-- Detecta qual mundo você está
local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer
local Level = LocalPlayer.Data.Level.Value
local PlaceId = game.PlaceId

local World1, World2, World3 = false, false, false
if PlaceId == 2753915549 then
    World1 = true
elseif PlaceId == 4442272183 then
    World2 = true
elseif PlaceId == 7449423635 then
    World3 = true
else
    LocalPlayer:Kick("Do not Support, Please wait...")
end

-- Função auxiliar para arredondar número
local function round(n)
    return math.floor(tonumber(n) + 0.5)
end

-- Define variáveis da quest com base no level
function SetQuestInfo()
    -- Exemplo para World1 (você pode seguir a mesma lógica para os outros)
    if World1 then
        if Level <= 9 then
            return {
                Mon = "Bandit",
                Quest = "BanditQuest1",
                LevelQuest = 1,
                CFrameQuest = CFrame.new(1059, 15, 1550),
                CFrameMon = CFrame.new(1045, 27, 1560)
            }
        elseif Level <= 14 then
            return {
                Mon = "Monkey",
                Quest = "JungleQuest",
                LevelQuest = 1,
                CFrameQuest = CFrame.new(-1598, 35, 153),
                CFrameMon = CFrame.new(-1448, 67, 11)
            }
        end
        -- Continue para os demais níveis...
    end
end

local QuestData = SetQuestInfo()
