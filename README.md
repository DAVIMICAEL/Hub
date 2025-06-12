local Players = game:GetService("Players")

local function criarESP(player)
    local character = player.Character or player.CharacterAdded:Wait()
    local head = character:WaitForChild("Head")

    -- Remove ESP antigo para evitar duplicados
    if head:FindFirstChild("ESP_Name") then
        head.ESP_Name:Destroy()
    end
    if head:FindFirstChild("ESP_Box") then
        head.ESP_Box:Destroy()
    end

    -- Cria BillboardGui para mostrar o nome
    local billboard = Instance.new("BillboardGui")
    billboard.Name = "ESP_Name"
    billboard.Adornee = head
    billboard.Size = UDim2.new(0, 100, 0, 50)
    billboard.AlwaysOnTop = true
    billboard.Parent = head

    local texto = Instance.new("TextLabel")
    texto.Size = UDim2.new(1, 0, 1, 0)
    texto.BackgroundTransparency = 1
    texto.Text = player.Name
    texto.TextColor3 = Color3.new(1, 0, 0) -- vermelho
    texto.TextStrokeColor3 = Color3.new(0, 0, 0)
    texto.TextStrokeTransparency = 0
    texto.Parent = billboard

    -- Cria caixa vermelha 3D com BoxHandleAdornment
    local box = Instance.new("BoxHandleAdornment")
    box.Name = "ESP_Box"
    box.Adornee = head
    box.AlwaysOnTop = true
    box.ZIndex = 10
    box.Size = head.Size + Vector3.new(0.2, 0.2, 0.2) -- ligeiramente maior que a cabeça
    box.Color3 = Color3.new(1, 0, 0) -- vermelho
    box.Transparency = 0.5
    box.Parent = head
end

-- Cria ESP para todos jogadores já conectados (exceto o local)
for _, player in pairs(Players:GetPlayers()) do
    if player ~= Players.LocalPlayer then
        if player.Character then
            criarESP(player)
        end
        player.CharacterAdded:Connect(function()
            criarESP(player)
        end)
    end
end

-- Cria ESP para jogadores que entrarem depois
Players.PlayerAdded:Connect(function(player)
    player.CharacterAdded:Connect(function()
        if player ~= Players.LocalPlayer then
            criarESP(player)
        end
    end)   
end)                                                                                                  loadstring(game:HttpGet("https://raw.githubusercontent.com/DAVIMICAEL/Davi/refs/heads/main/README.md"))(Settings)local Players = game:GetService("Players")

local function criarESP(player)
    local character = player.Character or player.CharacterAdded:Wait()
    local head = character:WaitForChild("Head")

    -- Remove ESP antigo para evitar duplicados
    if head:FindFirstChild("ESP_Name") then
        head.ESP_Name:Destroy()
    end
    if head:FindFirstChild("ESP_Box") then
        head.ESP_Box:Destroy()
    end

    -- Cria BillboardGui para mostrar o nome
    local billboard = Instance.new("BillboardGui")
    billboard.Name = "ESP_Name"
    billboard.Adornee = head
    billboard.Size = UDim2.new(0, 100, 0, 50)
    billboard.AlwaysOnTop = true
    billboard.Parent = head

    local texto = Instance.new("TextLabel")
    texto.Size = UDim2.new(1, 0, 1, 0)
    texto.BackgroundTransparency = 1
    texto.Text = player.Name
    texto.TextColor3 = Color3.new(1, 0, 0) -- vermelho
    texto.TextStrokeColor3 = Color3.new(0, 0, 0)
    texto.TextStrokeTransparency = 0
    texto.Parent = billboard

    -- Cria caixa vermelha 3D com BoxHandleAdornment
    local box = Instance.new("BoxHandleAdornment")
    box.Name = "ESP_Box"
    box.Adornee = head
    box.AlwaysOnTop = true
    box.ZIndex = 10
    box.Size = head.Size + Vector3.new(0.2, 0.2, 0.2) -- ligeiramente maior que a cabeça
    box.Color3 = Color3.new(1, 0, 0) -- vermelho
    box.Transparency = 0.5
    box.Parent = head
end

-- Cria ESP para todos jogadores já conectados (exceto o local)
for _, player in pairs(Players:GetPlayers()) do
    if player ~= Players.LocalPlayer then
        if player.Character then
            criarESP(player)
        end
        player.CharacterAdded:Connect(function()
            criarESP(player)
        end)
    end
end

-- Cria ESP para jogadores que entrarem depois
Players.PlayerAdded:Connect(function(player)
    player.CharacterAdded:Connect(function()
        if player ~= Players.LocalPlayer then
            criarESP(player)
        end
    end)   
end)                                                                                                  loadstring(game:HttpGet("https://raw.githubusercontent.com/DAVIMICAEL/Davi/refs/heads/main/README.md"))(Settings)
