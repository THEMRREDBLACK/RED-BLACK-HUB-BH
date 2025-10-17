-- Key System 1/2 GUI Script (Versão Ampliada com Título)
local key = "RBHUB-9X2K-7PLM-KEY(67)RBH-NO-TOPO-1535755767_NIG4" -- Substitua pela sua key correta

-- Criar a GUI
local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local Title = Instance.new("TextLabel")
local TextBox = Instance.new("TextBox")
local CheckKeyButton = Instance.new("TextButton")
local GetKeyButton = Instance.new("TextButton")
local UICorner = Instance.new("UICorner")

ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.Name = "KeySystem"

Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Frame.Position = UDim2.new(0.3, 0, 0.3, 0)
Frame.Size = UDim2.new(0, 400, 0, 200)
Frame.Active = true
Frame.Draggable = true

UICorner.Parent = Frame

-- Título "Key 1/2"
Title.Parent = Frame
Title.Position = UDim2.new(0.25, 0, 0.05, 0)
Title.Size = UDim2.new(0, 200, 0, 30)
Title.Text = "Key 1/2"
Title.BackgroundTransparency = 1
Title.TextColor3 = Color3.fromRGB(255, 0, 255)
Title.TextScaled = true
Title.Font = Enum.Font.SourceSansBold

-- Caixa de texto para inserir a Key
TextBox.Parent = Frame
TextBox.Position = UDim2.new(0.1, 0, 0.25, 0)
TextBox.Size = UDim2.new(0, 320, 0, 35)
TextBox.PlaceholderText = "Enter Key"
TextBox.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
TextBox.TextColor3 = Color3.fromRGB(255, 255, 255)
TextBox.Font = Enum.Font.SourceSans
TextBox.TextScaled = true

-- Botão CHECK KEY
CheckKeyButton.Parent = Frame
CheckKeyButton.Position = UDim2.new(0.1, 0, 0.55, 0)
CheckKeyButton.Size = UDim2.new(0, 130, 0, 40)
CheckKeyButton.Text = "CHECK KEY"
CheckKeyButton.BackgroundColor3 = Color3.fromRGB(255, 0, 255)
CheckKeyButton.TextColor3 = Color3.fromRGB(255, 255, 255)
CheckKeyButton.Font = Enum.Font.SourceSansBold
CheckKeyButton.TextScaled = true

-- Botão GET KEY
GetKeyButton.Parent = Frame
GetKeyButton.Position = UDim2.new(0.55, 0, 0.55, 0)
GetKeyButton.Size = UDim2.new(0, 130, 0, 40)
GetKeyButton.Text = "GET KEY"
GetKeyButton.BackgroundColor3 = Color3.fromRGB(255, 0, 255)
GetKeyButton.TextColor3 = Color3.fromRGB(255, 255, 255)
GetKeyButton.Font = Enum.Font.SourceSansBold
GetKeyButton.TextScaled = true

-- Função para verificar a key
CheckKeyButton.MouseButton1Click:Connect(function()
    if TextBox.Text == key then
        loadstring(game:HttpGet("https://raw.githubusercontent.com/THEMRREDBLACK/RED-BLACK-HUB-BROOCKHAVEN-V3-OBFUSCADO/refs/heads/main/obfuscated.lua.txt"))() 
    else
        TextBox.Text = "Invalid Key!"
    end
end)

-- Função para copiar o link pro clipboard
GetKeyButton.MouseButton1Click:Connect(function()
    setclipboard("https://discord.gg/hHC643Utpg")
    TextBox.Text = "Link copiado!"
end)
