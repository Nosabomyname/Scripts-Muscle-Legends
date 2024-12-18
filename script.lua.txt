-- Criar uma GUI com janela ajustável
local Library = loadstring(game:HttpGet("https://pastebin.com/raw/EdJT9EGX"))()
local Window = Library:CreateWindow("Blox Fruits Ultimate Hub") -- Título da Janela
local MainTab = Window:CreateTab("Funções") -- Aba Principal

-- Tabelas de controle
local Toggles = {
    AutoFarm = false,
    AutoFactory = false,
    AutoPirate = false,
    AutoRaceUpgrade = false,
    AutoGetCDK = false,
    AutoGetTripleKatana = false,
}

-- Funções para as funcionalidades

-- Auto Farm
local function autoFarm()
    while Toggles.AutoFarm do
        -- Código para farm automático
        print("Auto Farm ativado...")
        wait(5) -- Simulação de funcionamento
    end
end

-- Auto Factory
local function autoFactory()
    while Toggles.AutoFactory do
        if game.PlaceId == 4442272183 then -- Verifica se está no 2º Sea
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.FactoryEvent.CFrame
            print("Teleportando para a Factory no 2º Sea!")
            wait(10)
        end
    end
end

-- Auto Pirate (3º Sea)
local function autoPirate()
    while Toggles.AutoPirate do
        if game.PlaceId == 7449423635 then -- Verifica se está no 3º Sea
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.PirateFarm.CFrame
            print("Farmando no 3º Sea...")
            wait(10)
        end
    end
end

-- Auto Upgrade de Raças
local function autoUpgradeRace()
    while Toggles.AutoRaceUpgrade do
        print("Fazendo upgrade de Raça v2/v3/v4...")
        wait(10)
    end
end

-- Auto Get CDK
local function autoGetCDK()
    while Toggles.AutoGetCDK do
        print("Obtendo Cursed Dual Katana...")
        wait(10)
    end
end

-- Auto Get Triple Katana
local function autoGetTripleKatana()
    while Toggles.AutoGetTripleKatana do
        print("Obtendo Triple Katana...")
        wait(10)
    end
end

-- Adicionando botões para ativar/desativar funcionalidades
MainTab:AddSwitch("Auto Farm", function(state)
    Toggles.AutoFarm = state
    if state then
        autoFarm()
    end
end)

MainTab:AddSwitch("Auto Factory (2º Sea)", function(state)
    Toggles.AutoFactory = state
    if state then
        autoFactory()
    end
end)

MainTab:AddSwitch("Auto Pirate (3º Sea)", function(state)
    Toggles.AutoPirate = state
    if state then
        autoPirate()
    end
end)

MainTab:AddSwitch("Auto Upgrade de Raças", function(state)
    Toggles.AutoRaceUpgrade = state
    if state then
        autoUpgradeRace()
    end
end)

MainTab:AddSwitch("Auto Get CDK", function(state)
    Toggles.AutoGetCDK = state
    if state then
        autoGetCDK()
    end
end)

MainTab:AddSwitch("Auto Get Triple Katana", function(state)
    Toggles.AutoGetTripleKatana = state
    if state then
        autoGetTripleKatana()
    end
end)

-- Configurações de minimização/maximização da janela
Window:CreateTab("Configurações"):AddButton("Minimizar", function()
    Window:Minimize() -- Minimizar a janela
end)

Window:CreateTab("Configurações"):AddButton("Maximizar", function()
    Window:Maximize() -- Maximizar a janela
end)

print("Script carregado com sucesso!")
