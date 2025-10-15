-- KEY FODASTICA
function verificarKey(key)
    return key == "RBH-5F8D2B7C-9A4E-4C3F-8B1D-2E6A7C9F0B3D-NIG4-NIG3R_66665817"
end

local keyValida = false

local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/jensonhirst/Orion/main/source')))()
local Window = OrionLib:MakeWindow({Name = "🎩RED BLACK HUB-BROOKHAVEN🎩", HidePremium = false, SaveConfig = true, ConfigFolder = "OrionTest"})

-- KEY ABA
local TabKey = Window:MakeTab({
    Name = "KEY",
    Icon = "rbxassetid://134079269839821",
    PremiumOnly = false
})

TabKey:AddTextbox({
    Name = "INSIRA SUA KEY:",
    Default = "",
    TextDisappear = false,
    Callback = function(text)
        if verificarKey(text) then
            keyValida = true
            OrionLib:MakeNotification({Name = "Acesso Liberado", Content = "Bem-vindo ao Red Black Hub!", Image = "rbxassetid://87117402316439", Time = 5})
        else
            keyValida = false
            OrionLib:MakeNotification({Name = "Key Incorreta", Content = "Por favor, insira a key correta!", Image = "rbxassetid://87117402316439", Time = 5})
        end
    end
})

TabKey:AddButton({
    Name = "GET KEY",
    Callback = function()
        if syn and syn.open then
            syn.open("https://discord.gg/hHC643Utpg")
        elseif KRNL_LOADER then
            KRNL_LOADER:LaunchURL("https://discord.gg/hHC643Utpg")
        elseif getgenv().openbrowser then
            openbrowser("https://discord.gg/hHC643Utpg")
        else
            setclipboard("https://discord.gg/hHC643Utpg")
            OrionLib:MakeNotification({
                Name = "GET KEY",
                Content = "O link do Discord foi copiado para sua área de transferência!",
                Image = "rbxassetid://87117402316439",
                Time = 7
            })
        end
    end
})

repeat wait() until keyValida

-- imagem foda da rbc
do
    local TweenService = game:GetService("TweenService")
    local CoreGui = game:GetService("CoreGui")
    local ContentProvider = game:GetService("ContentProvider")

    local function splashImage(assetId, totalTime)
        totalTime = totalTime or 4
        local half = totalTime / 2

        local old = CoreGui:FindFirstChild("RBH_Splash")
        if old then old:Destroy() end

        local gui = Instance.new("ScreenGui")
        gui.Name = "RBH_Splash"
        gui.IgnoreGuiInset = true
        gui.ResetOnSpawn = false
        gui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
        gui.Parent = CoreGui

        local img = Instance.new("ImageLabel")
        img.Name = "Splash"
        img.BackgroundTransparency = 1
        img.AnchorPoint = Vector2.new(0.5, 0.5)
        img.Position = UDim2.fromScale(0.5, 0.5)
        img.Size = UDim2.fromScale(0.35, 0.35)
        img.Image = "rbxassetid://" .. tostring(assetId)
        img.ImageTransparency = 1
        img.Parent = gui

        local corner = Instance.new("UICorner")
        corner.CornerRadius = UDim.new(0, 16)
        corner.Parent = img

        pcall(function() ContentProvider:PreloadAsync({img}) end)

        local fadeIn = TweenService:Create(
            img,
            TweenInfo.new(half, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
            { ImageTransparency = 0 }
        )
        local fadeOut = TweenService:Create(
            img,
            TweenInfo.new(half, Enum.EasingStyle.Quad, Enum.EasingDirection.In),
            { ImageTransparency = 1 }
        )

        fadeIn:Play(); fadeIn.Completed:Wait()
        fadeOut:Play(); fadeOut.Completed:Wait()

        gui:Destroy()
    end

    task.spawn(function()
        splashImage(103830684951577, 4)
    end)
end

local sons = {
    "rbxassetid://87484814057059",
    "rbxassetid://113491014204126",
    "rbxassetid://110983956928751",
    "rbxassetid://80344181334677",
    "rbxassetid://97529429187942",
    "rbxassetid://5858548244",
    "rbxassetid://15929797051",
    "rbxassetid://113118633294800",
    "rbxassetid://113028772835303",
    "rbxassetid://102566984907215",
    "rbxassetid://100835951102315",
    "rbxassetid://4810729995"
}

_G.somIndex = (_G.somIndex or 0) + 1
if _G.somIndex > #sons then
    _G.somIndex = 1
end

local tiro = Instance.new("Sound")
tiro.SoundId = sons[_G.somIndex]
tiro.Volume = 5
tiro.Parent = game:GetService("SoundService")
tiro:Play()

local args = {
    [1] = "RolePlayName",
    [2] = "🚀✨RED BLACK HUB🚀✨"
}
game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1RPNam1eTex1t"):FireServer(unpack(args))

local Tab1 = Window:MakeTab({
    Name = "SCRIPTS",
    Icon = "rbxassetid://87117402316439",
    PremiumOnly = false
})

Tab1:AddTextbox({
    Name = "EXECUTE HUBS",
    Default = "",
    TextDisappear = false,
    Callback = function(text)
        _G.scriptCode = text
    end
})

Tab1:AddButton({
    Name = "EXECUTAR SCRIPT DESEJADO",
    Callback = function()
        if _G.scriptCode and _G.scriptCode ~= "" then
            local func = loadstring(_G.scriptCode)
            if func then
                func()
            else
                print("Erro ao carregar o script.")
            end
        else
            print("Por favor, insira um script válido na TextBox.")
        end
    end
})

Tab1:AddButton({
    Name = "ESP RED BLACK",
    Callback = function()
        loadstring(game:HttpGet('https://rawscripts.net/raw/Universal-Script-ESP-VERIFICADOR-DE-PLAYERS-V5-27937'))()
    end
})

Tab1:AddButton({
    Name = "YAK HUB BY PEDRO OF WAR",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/Yak-Scripts/yakhub/main/yakhub.lua", true))() 
    end
})

Tab1:AddButton({
    Name = "CLEITIN HUB V4",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/CLEITI6966/Brookhaven/refs/heads/main/start.lua"))()
    end
})

Tab1:AddButton({
    Name = "SANDER X️",
    Callback = function()
        loadstring(game:HttpGet('https://rawscripts.net/raw/Brookhaven-RP-Sander-X-Hub-Latest-Version-3-16718'))()
    end
})

Tab1:AddButton({
    Name = "FLY RED BLACK",
    Callback = function()
        loadstring("\108\111\97\100\115\116\114\105\110\103\40\103\97\109\101\58\72\116\116\112\71\101\116\40\34\104\116\116\112\115\58\47\47\114\97\119\46\103\105\116\104\117\98\117\115\101\114\99\111\110\116\101\110\116\46\99\111\109\47\107\105\119\105\57\57\57\45\98\108\105\112\47\77\114\47\114\101\102\115\47\104\101\97\100\115\47\109\97\105\110\47\82\69\65\68\77\69\46\109\100\34\41\41\40\41")()
    end
})

Tab1:AddButton({
    Name = "RED BLACK CALCULATOR",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/THEMRREDBLACK/CALCULADORA-RED-BLACK-/refs/heads/main/README.md"))()
    end
})

Tab1:AddButton({
    Name = "WALK FLING(SOMENTE EM MAPAS COM COLISÃO DE PLAYERS)",
    Callback = function()
       loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Walk-Fling-Script-18573"))()
    end
})

Tab1:AddButton({
    Name = "R4D SEM KEY",
    Callback = function()
        loadstring(game:HttpGet("https://rawscripts.net/raw/Brookhaven-RP-R4D-script-no-key-17562"))()
    end
})

Tab1:AddButton({
    Name = "INFINITE YIELD",
    Callback = function()
        loadstring(game:HttpGet("https://rawscripts.net/raw/Infinite-Yield_500"))()
    end
})

Tab1:AddButton({
    Name = "TROLL GUI",
    Callback = function()
        loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Troll-Gui-3874"))()
    end
})

local Tab2 = Window:MakeTab({
    Name = "TOOLS/LAG SERVER",
    Icon = "rbxassetid://85371650668851",
    PremiumOnly = false
})

Tab2:AddButton({
    Name = "Equipar Todos os Itens",
    Callback = function()
        equipAllItems()
    end
})

Tab2:AddButton({
    Name = "TELEPORT TOOL",
    Callback = function()
        loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Teleport-Tool-27419"))()
    end
})

Tab2:AddButton({
    Name = "TELEKINIS",
    Callback = function()
        loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Fe-Telekinesis-V5-21542"))()
    end
})

function teleporteEVoltar()
    local player = game.Players.LocalPlayer
    if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
        local posicaoOriginal = player.Character.HumanoidRootPart.CFrame
        local novaPosicao = CFrame.new(-58, -28, 113)
        player.Character.HumanoidRootPart.CFrame = novaPosicao
        print("Teletransportado para a nova posição: " .. tostring(novaPosicao))
        wait(5)
        player.Character.HumanoidRootPart.CFrame = posicaoOriginal
        print("Retornou à posição original: " .. tostring(posicaoOriginal))
    else
        print("Não foi possível teletransportar o jogador.")
    end
end

Tab2:AddButton({
    Name = " MÃO DE FOGO",
    Callback = function()
        teleporteEVoltar()
    end
})

local Tab3 = Window:MakeTab({
    Name = "TROLL",
    Icon = "rbxassetid://127552583822854",
    PremiumOnly = false
})

local playerName = ""

local TextBox = Tab3:AddTextbox({
    Name = "Nome do Jogador",
    Default = "",
    TextDisappear = false,
    Callback = function(value)
        playerName = value
        print("Nome do jogador inserido: " .. playerName)
    end
})

Tab3:AddButton({
    Name = "VIEW PLAYER",
    Callback = function()
        local players = game:GetService("Players")
        for _, player in pairs(players:GetPlayers()) do
            if string.match(player.Name:lower(), playerName:lower()) or string.match(player.DisplayName:lower(), playerName:lower()) then
                print("Visualizando jogador: " .. player.Name)
                break
            end
        end
    end
})

Tab3:AddButton({
    Name = "TELEPORTE PLAYER",
    Callback = function()
        local players = game:GetService("Players")
        local localPlayer = players.LocalPlayer
        for _, player in pairs(players:GetPlayers()) do
            if string.match(player.Name:lower(), playerName:lower()) or string.match(player.DisplayName:lower(), playerName:lower()) then
                if localPlayer and localPlayer.Character and localPlayer.Character:FindFirstChild("HumanoidRootPart") then
                    localPlayer.Character.HumanoidRootPart.CFrame = player.Character.HumanoidRootPart.CFrame
                    print("Teleportado para o jogador: " .. player.Name)
                end
                break
            end
        end
    end
})

Tab3:AddButton({
    Name = "FLING RED BLACK(MANUAL)",
    Callback = function()
        loadstring("\108\111\97\100\115\116\114\105\110\103\40\103\97\109\101\58\72\116\116\112\71\101\116\40\34\104\116\116\112\115\58\47\47\114\97\119\46\103\105\116\104\117\98\117\115\101\114\99\111\110\116\101\110\116\46\99\111\109\47\107\105\119\105\57\57\57\45\98\108\105\112\47\65\106\106\115\106\115\107\115\107\47\114\101\102\115\47\104\101\97\100\115\47\109\97\105\110\47\82\69\65\68\77\69\46\109\100\34\41\41\40\41")()
    end
})

Tab3:AddButton({
    Name = "BRING RED BLACK",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/THEMRREDBLACK/Bring-red-black-v2/refs/heads/main/README.md"))()
    end
})

Tab3:AddButton({
    Name = "FLING RED BLACK(AUTO)",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/92362763635362/redblacktools/main/FLINGREDBLACK.lua"))()
    end
})

Tab3:AddButton({
    Name = "PRISON RED BLACK ",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/THEMRREDBLACK/PRISON-RED-BLACK-/refs/heads/main/README.md"))()
    end
})

Tab3:AddButton({
    Name = "PEGAR SOFÁ",
    Callback = function()
        local player = game.Players.LocalPlayer
        if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
            player.Character.HumanoidRootPart.CFrame = CFrame.new(-82, 19, -130)
            print("Teletransportado para as coordenadas: X: -82, Y: 19, Z: -130")
        else
            print("Não foi possível teletransportar.")
        end
    end
})

local Tab4 = Window:MakeTab({
    Name = "TROLL VERSION V3",
    Icon = "rbxassetid://115893843340429",
    PremiumOnly = false
})

Tab4:AddButton({
    Name = "TROLL VERSION BETA️",
    Callback = function()
        loadstring(game:HttpGet('https://redblackhub-protected.vercel.app/script'))()
    end
})

Tab4:AddButton({
    Name = "RED BLACK HUB BY VOLTZ",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/ygagga/Red-Black-hub-1.0-/refs/heads/main/673b292c795c6275.txt"))()
    end
})

local Tab5 = Window:MakeTab({
    Name = "EXIBIÇÕES/REJOIN",
    Icon = "rbxassetid://92600174218873",
    PremiumOnly = false
})

Tab5:AddButton({
    Name = "REJOIN",
    Callback = function()
        game:GetService("TeleportService"):Teleport(game.PlaceId, game.Players.LocalPlayer)
    end
})

Tab5:AddButton({
    Name = "COORDENADAS",
    Callback = function()
        local player = game.Players.LocalPlayer
        if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
            local pos = player.Character.HumanoidRootPart.Position
            setclipboard(string.format("X: %d, Y: %d, Z: %d", pos.X, pos.Y, pos.Z))
            print("Coordenadas copiadas para a área de transferência: ", pos)
        else
            print("Não foi possível obter as coordenadas.")
        end
    end
})

-- FUNÇÃO SET SPAWNPOINT
local spawnCFrame = nil

Tab5:AddButton({
    Name = "SET SPAWNPOINT",
    Callback = function()
        local player = game.Players.LocalPlayer
        if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
            spawnCFrame = player.Character.HumanoidRootPart.CFrame
            print("Ponto de spawn definido!")
            OrionLib:MakeNotification({
                Name = "SpawnPoint",
                Content = "Seu ponto de spawn foi salvo!",
                Image = "rbxassetid://92600174218873",
                Time = 5
            })
        else
            print("Não foi possível definir o ponto de spawn.")
        end
    end
})

game.Players.LocalPlayer.CharacterAdded:Connect(function(char)
    if spawnCFrame then
        local hrp = char:WaitForChild("HumanoidRootPart", 10)
        if hrp then
            hrp.CFrame = spawnCFrame
            print("Teleportado para o ponto de spawn salvo!")
        end
    end
end)

function antiAFK()
    local player = game.Players.LocalPlayer
    local character = player.Character or player.CharacterAdded:Wait()
    local humanoidRootPart = character:WaitForChild("HumanoidRootPart")
    local function moverJogador()
        humanoidRootPart.CFrame = humanoidRootPart.CFrame * CFrame.new(0, 0, 0.1)
        wait(1)
        humanoidRootPart.CFrame = humanoidRootPart.CFrame * CFrame.new(0, 0, -0.1)
    end
    while true do
        wait(600)
        moverJogador()
    end
end

Tab5:AddButton({
    Name = "ANTI AFK",
    Callback = function()
        antiAFK()
    end
})

local Tab6 = Window:MakeTab({
    Name = "PLAYER",
    Icon = "rbxassetid://120801516384560",
    PremiumOnly = false
})

local spinning = false

Tab6:AddButton({
    Name = "Ativar Spin",
    Callback = function()
        spinning = true
        while spinning do
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.Angles(0, math.rad(10), 0)
            wait(0.1)
        end
        print("Spin ativado")
    end
})

Tab6:AddButton({
    Name = "Desativar Spin",
    Callback = function()
        spinning = false
        print("Spin desativado")
    end
})

local speed = 16
local jumpPower = 50

Tab6:AddTextbox({
    Name = "Velocidade",
    Default = tostring(speed),
    TextDisappear = false,
    Callback = function(text)
        local newSpeed = tonumber(text)
        if newSpeed then
            speed = newSpeed
            game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = speed
            print("Velocidade alterada para: " .. speed)
        else
            print("Por favor, insira um valor numérico válido para a velocidade.")
        end
    end
})

Tab6:AddButton({
    Name = "ANTI SIT",
    Callback = function()
        local humanoid = game.Players.LocalPlayer.Character:FindFirstChildOfClass("Humanoid")
        if humanoid then
            humanoid.Sit = false
            humanoid.Changed:Connect(function(property)
                if property == "Sit" then
                    humanoid.Sit = false
                end
            end)
            print("Anti Sit ativado")
        end
    end
})

Tab6:AddButton({
    Name = "VOLTAR A CONSEGUIR SENTAR",
    Callback = function()
        local humanoid = game.Players.LocalPlayer.Character:FindFirstChildOfClass("Humanoid")
        if humanoid then
            humanoid.Changed:Connect(function() end)
            print("Agora você pode sentar novamente")
        end
    end
})

Tab6:AddTextbox({
    Name = "Pulo",
    Default = tostring(jumpPower),
    TextDisappear = false,
    Callback = function(text)
        local newJumpPower = tonumber(text)
        if newJumpPower then
            jumpPower = newJumpPower
            game.Players.LocalPlayer.Character.Humanoid.JumpPower = jumpPower
            print("Pulo alterado para: " .. jumpPower)
        else
            print("Por favor, insira um valor numérico válido para o pulo.")
        end
    end
})

function equipAllItems()
    local character = game.Players.LocalPlayer.Character
    if character and character:FindFirstChildOfClass("Humanoid") then
        local humanoid = character:FindFirstChildOfClass("Humanoid")
        for i, tool in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
            if tool:IsA("Tool") then
                humanoid:EquipTool(tool)
                print("Item equipado: " .. tool.Name)
            end
        end
    else
        print("Personagem não encontrado ou não possui um Humanoid.")
    end
end

local Tab7 = Window:MakeTab({
    Name = "TIK TOK",
    Icon = "rbxassetid://77458568185817",
    PremiumOnly = false
})

Tab7:AddButton({
    Name = "TIK TOK DO MR RED BLACK",
    Callback = function()
        setclipboard("THE_MR_RED_BLACK_OFC")
    end
})

local Tab8 = Window:MakeTab({
    Name = "OWNER SCRIPT",
    Icon = "rbxassetid://133887216434541",
    PremiumOnly = false
})

Tab8:AddLabel("THE MR RED BLACK SCRIPTS OWNER")
Tab8:AddLabel("NOLY")
Tab8:AddLabel("KALEBAO")
Tab8:AddLabel("RYAN")
Tab8:AddLabel("THECLOCKWORKDEV")

local Tab9 = Window:MakeTab({
    Name = "AVATAR️",
    Icon = "rbxassetid://112208414782742",
    PremiumOnly = false
})

Tab9:AddButton({
    Name = "NOME DE RP RED BLACK MEMBER️",
    Callback = function()
        local args = {
            [1] = "RolePlayName",
            [2] = "🎩RED BLACK MEMBER🎩"
        }
        game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1RPNam1eTex1t"):FireServer(unpack(args))
        print("Nome de RP definido: 🎩RED BLACK MEMBER🎩")
    end
})

local TabChat = Window:MakeTab({
    Name = "CHAT",
    Icon = "rbxassetid://126878062099997",
    PremiumOnly = false
})

TabChat:AddButton({
    Name = "CHAT BY PASS",
    Callback = function()
        loadstring(game:HttpGet('https://raw.githubusercontent.com/Gazer-Ha/bruh/refs/heads/main/ImBadd1'))()
        print("Script do tutorial executado")
    end
})

TabChat:AddButton({
    Name = "PLACA GIGANTE 1",
    Callback = function()
        local player = game.Players.LocalPlayer
        if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
            player.Character.HumanoidRootPart.CFrame = CFrame.new(-238, 88, -549)
            print("Teletransportado para as coordenadas: X: -238, Y: 88, Z: -549")
        else
            print("Não foi possível teletransportar.")
        end
    end
})
