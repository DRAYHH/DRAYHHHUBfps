# DRAYHHHUBfps--========================================================--
--                    DRAYHH HUB
--          FPS BOOST + ULTRA LOW + KEY SYSTEM
--========================================================--

local Players = game:GetService("Players")
local Lighting = game:GetService("Lighting")
local Workspace = game:GetService("Workspace")
local RunService = game:GetService("RunService")

local Player = Players.LocalPlayer
local PlayerGui = Player:WaitForChild("PlayerGui")

--========================================================--
-- CONFIG
--========================================================--

local VALID_KEY = "DRAYHH-K7P2-X9QA"
local GET_KEY_LINK = "https://link-center.net/8212571/s6EpiSgdi6KZ"

local boostEnabled = false
local ultraEnabled = false

--========================================================--
-- GUI
--========================================================--

local Gui = Instance.new("ScreenGui")
Gui.Name = "DRAYHH_HUB"
Gui.ResetOnSpawn = false
Gui.IgnoreGuiInset = false
Gui.Parent = PlayerGui

--========================================================--
-- FPS
--========================================================--

local FPS = Instance.new("TextLabel")
FPS.Name = "FPS"
FPS.Size = UDim2.fromOffset(90,28)
FPS.Position = UDim2.fromOffset(10,48)
FPS.BackgroundColor3 = Color3.fromRGB(20,20,20)
FPS.BackgroundTransparency = 0.15
FPS.BorderSizePixel = 0
FPS.TextColor3 = Color3.new(1,1,1)
FPS.Font = Enum.Font.GothamBold
FPS.TextSize = 14
FPS.Text = "FPS: --"
FPS.Parent = Gui

task.spawn(function()

	while Gui.Parent do

		local frames = 0
		local start = os.clock()

		while os.clock() - start < 0.5 do
			RunService.RenderStepped:Wait()
			frames += 1
		end

		local elapsed = os.clock() - start

		if elapsed > 0 then
			FPS.Text = "FPS: " .. math.floor(frames / elapsed + 0.5)
		end

	end

end)

--========================================================--
-- BOTÃO FLUTUANTE
--========================================================--

local Open = Instance.new("TextButton")
Open.Name = "OpenButton"
Open.Size = UDim2.fromOffset(42,42)
Open.Position = UDim2.new(0,10,0.5,-21)
Open.BackgroundColor3 = Color3.fromRGB(20,20,20)
Open.BorderSizePixel = 0
Open.Text = "≡"
Open.TextColor3 = Color3.new(1,1,1)
Open.TextSize = 22
Open.Font = Enum.Font.GothamBold
Open.Visible = false
Open.Parent = Gui

--========================================================--
-- KEY MENU
--========================================================--

local KeyMenu = Instance.new("Frame")
KeyMenu.Size = UDim2.fromOffset(290,275)
KeyMenu.Position = UDim2.new(0.5,-145,0.5,-137)
KeyMenu.BackgroundColor3 = Color3.fromRGB(23,23,23)
KeyMenu.BorderSizePixel = 0
KeyMenu.Parent = Gui

local KeyTitle = Instance.new("TextLabel")
KeyTitle.Size = UDim2.new(1,0,0,40)
KeyTitle.Position = UDim2.fromOffset(0,8)
KeyTitle.BackgroundTransparency = 1
KeyTitle.Text = "DRAYHH HUB"
KeyTitle.TextColor3 = Color3.new(1,1,1)
KeyTitle.Font = Enum.Font.GothamBold
KeyTitle.TextSize = 24
KeyTitle.Parent = KeyMenu

local KeySubtitle = Instance.new("TextLabel")
KeySubtitle.Size = UDim2.new(1,0,0,25)
KeySubtitle.Position = UDim2.fromOffset(0,45)
KeySubtitle.BackgroundTransparency = 1
KeySubtitle.Text = "KEY SYSTEM"
KeySubtitle.TextColor3 = Color3.fromRGB(170,170,170)
KeySubtitle.TextSize = 14
KeySubtitle.Parent = KeyMenu

local GetKey = Instance.new("TextButton")
GetKey.Size = UDim2.new(1,-30,0,40)
GetKey.Position = UDim2.fromOffset(15,75)
GetKey.BackgroundColor3 = Color3.fromRGB(43,43,43)
GetKey.BorderSizePixel = 0
GetKey.Text = "GET KEY"
GetKey.TextColor3 = Color3.new(1,1,1)
GetKey.Font = Enum.Font.GothamBold
GetKey.TextSize = 15
GetKey.Parent = KeyMenu

local KeyBox = Instance.new("TextBox")
KeyBox.Size = UDim2.new(1,-30,0,40)
KeyBox.Position = UDim2.fromOffset(15,123)
KeyBox.BackgroundColor3 = Color3.fromRGB(38,38,38)
KeyBox.BorderSizePixel = 0
KeyBox.TextColor3 = Color3.new(1,1,1)
KeyBox.PlaceholderColor3 = Color3.fromRGB(140,140,140)
KeyBox.PlaceholderText = "Espaço para a key"
KeyBox.Text = ""
KeyBox.ClearTextOnFocus = false
KeyBox.Font = Enum.Font.Gotham
KeyBox.TextSize = 14
KeyBox.Parent = KeyMenu

local Check = Instance.new("TextButton")
Check.Size = UDim2.new(1,-30,0,40)
Check.Position = UDim2.fromOffset(15,171)
Check.BackgroundColor3 = Color3.fromRGB(43,43,43)
Check.BorderSizePixel = 0
Check.Text = "CHECK KEY"
Check.TextColor3 = Color3.new(1,1,1)
Check.Font = Enum.Font.GothamBold
Check.TextSize = 15
Check.Parent = KeyMenu

local Status = Instance.new("TextLabel")
Status.Size = UDim2.new(1,-30,0,35)
Status.Position = UDim2.fromOffset(15,219)
Status.BackgroundTransparency = 1
Status.Text = ""
Status.TextColor3 = Color3.new(1,1,1)
Status.TextSize = 13
Status.Parent = KeyMenu

--========================================================--
-- MENU PRINCIPAL
--========================================================--

local Menu = Instance.new("Frame")
Menu.Size = UDim2.fromOffset(260,200)
Menu.Position = UDim2.new(0.5,-130,0.5,-100)
Menu.BackgroundColor3 = Color3.fromRGB(23,23,23)
Menu.BorderSizePixel = 0
Menu.Visible = false
Menu.Parent = Gui

local MainTitle = Instance.new("TextLabel")
MainTitle.Size = UDim2.new(1,0,0,35)
MainTitle.Position = UDim2.fromOffset(0,8)
MainTitle.BackgroundTransparency = 1
MainTitle.Text = "DRAYHH HUB"
MainTitle.TextColor3 = Color3.new(1,1,1)
MainTitle.Font = Enum.Font.GothamBold
MainTitle.TextSize = 22
MainTitle.Parent = Menu

local MainSubtitle = Instance.new("TextLabel")
MainSubtitle.Size = UDim2.new(1,0,0,25)
MainSubtitle.Position = UDim2.fromOffset(0,40)
MainSubtitle.BackgroundTransparency = 1
MainSubtitle.Text = "FPS BOOST"
MainSubtitle.TextColor3 = Color3.fromRGB(170,170,170)
MainSubtitle.TextSize = 14
MainSubtitle.Parent = Menu

local Boost = Instance.new("TextButton")
Boost.Size = UDim2.new(1,-20,0,45)
Boost.Position = UDim2.fromOffset(10,72)
Boost.BackgroundColor3 = Color3.fromRGB(43,43,43)
Boost.BorderSizePixel = 0
Boost.Text = "FPS BOOST: OFF"
Boost.TextColor3 = Color3.new(1,1,1)
Boost.Font = Enum.Font.GothamBold
Boost.TextSize = 15
Boost.Parent = Menu

local Ultra = Instance.new("TextButton")
Ultra.Size = UDim2.new(1,-20,0,45)
Ultra.Position = UDim2.fromOffset(10,125)
Ultra.BackgroundColor3 = Color3.fromRGB(43,43,43)
Ultra.BorderSizePixel = 0
Ultra.Text = "ULTRA LOW: OFF"
Ultra.TextColor3 = Color3.new(1,1,1)
Ultra.Font = Enum.Font.GothamBold
Ultra.TextSize = 15
Ultra.Parent = Menu

--========================================================--
-- REMOVE EFEITOS
--========================================================--

local function removeEffects()

	for _, obj in ipairs(Lighting:GetDescendants()) do

		if obj:IsA("PostEffect") then
			obj.Enabled = false
		end

		if obj:IsA("Atmosphere") then
			obj.Density = 0
			obj.Haze = 0
			obj.Glare = 0
		end

	end

	for _, obj in ipairs(Workspace:GetDescendants()) do

		if obj:IsA("ParticleEmitter")
		or obj:IsA("Trail")
		or obj:IsA("Beam")
		or obj:IsA("Smoke")
		or obj:IsA("Fire")
		or obj:IsA("Sparkles") then

			obj.Enabled = false

		end

	end

end

--========================================================--
-- GRÁFICOS MÍNIMOS
--========================================================--

local function minimumGraphics()

	pcall(function()
		settings().Rendering.QualityLevel = Enum.QualityLevel.Level01
	end)

	Lighting.GlobalShadows = false
	Lighting.EnvironmentDiffuseScale = 0
	Lighting.EnvironmentSpecularScale = 0
	Lighting.FogEnd = 1000000

	for _, obj in ipairs(Workspace:GetDescendants()) do

		if obj:IsA("BasePart") then

			obj.CastShadow = false
			obj.Reflectance = 0

			pcall(function()
				obj.Material = Enum.Material.SmoothPlastic
			end)

		end

	end

end

--========================================================--
-- TEXTURAS
--========================================================--

local function removeTextures()

	for _, obj in ipairs(Workspace:GetDescendants()) do

		if obj:IsA("SurfaceAppearance") then

			obj.Enabled = false

		elseif obj:IsA("Texture") then

			obj.Transparency = 1

		elseif obj:IsA("Decal") then

			obj.Transparency = 1

		end

	end

end

--========================================================--
-- PERSONAGENS
--========================================================--

local function optimizeCharacter(character)

	if not character then
		return
	end

	for _, obj in ipairs(character:GetDescendants()) do

		if obj:IsA("Shirt")
		or obj:IsA("Pants")
		or obj:IsA("ShirtGraphic") then

			obj:Destroy()

		elseif obj:IsA("Decal") and obj.Name == "face" then

			obj.Transparency = 1

		elseif obj:IsA("Texture") then

			obj.Transparency = 1

		elseif obj:IsA("Accessory") then

			obj:Destroy()

		end

	end

end

--========================================================--
-- TERRAIN
--========================================================--

local function optimizeTerrain()

	local terrain = Workspace:FindFirstChildOfClass("Terrain")

	if not terrain then
		return
	end

	pcall(function()
		terrain.Decoration = false
	end)

	pcall(function()
		terrain.WaterWaveSize = 0
	end)

	pcall(function()
		terrain.WaterWaveSpeed = 0
	end)

	pcall(function()
		terrain.WaterReflectance = 0
	end)

	pcall(function()
		terrain.WaterTransparency = 1
	end)

end

--========================================================--
-- ULTRA LOW
-- CORES ORIGINAIS NO MAPA
--========================================================--

local function ultraGrayPart(obj)

	if not obj or not obj.Parent then
		return
	end

	if obj:IsA("BasePart") then

		pcall(function()
			obj.CastShadow = false
		end)

		pcall(function()
			obj.Reflectance = 0
		end)

		-- SOMENTE troca o material.
		-- A cor original é preservada.
		pcall(function()
			obj.Material = Enum.Material.SmoothPlastic
		end)

		if obj:IsA("MeshPart") then

			pcall(function()
				obj.RenderFidelity = Enum.RenderFidelity.Performance
			end)

		end

	elseif obj:IsA("Texture") or obj:IsA("Decal") then

		pcall(function()
			obj.Transparency = 1
		end)

	elseif obj:IsA("SurfaceAppearance") then

		pcall(function()
			obj.Enabled = false
		end)

	elseif obj:IsA("ParticleEmitter")
		or obj:IsA("Trail")
		or obj:IsA("Beam")
		or obj:IsA("Smoke")
		or obj:IsA("Fire")
		or obj:IsA("Sparkles") then

		pcall(function()
			obj.Enabled = false
		end)

	end

end


local function ultraLowVisuals()

	--====================================================--
	-- QUALIDADE MÍNIMA
	--====================================================--

	pcall(function()
		settings().Rendering.QualityLevel = Enum.QualityLevel.Level01
	end)

	--====================================================--
	-- LIGHTING
	--====================================================--

	pcall(function()
		Lighting.GlobalShadows = false
	end)

	pcall(function()
		Lighting.EnvironmentDiffuseScale = 0
	end)

	pcall(function()
		Lighting.EnvironmentSpecularScale = 0
	end)

	pcall(function()
		Lighting.Brightness = 2
	end)

	pcall(function()
		Lighting.Ambient = Color3.fromRGB(180,180,180)
	end)

	pcall(function()
		Lighting.OutdoorAmbient = Color3.fromRGB(180,180,180)
	end)

	pcall(function()
		Lighting.FogStart = 0
	end)

	pcall(function()
		Lighting.FogEnd = 1000000
	end)

	--====================================================--
	-- IMAGEM LEVEMENTE ACINZENTADA
	--====================================================--

	local oldColor = Lighting:FindFirstChild("DRAYHH_ULTRA_GRAY")

	if oldColor then
		oldColor:Destroy()
	end

	local gray = Instance.new("ColorCorrectionEffect")
	gray.Name = "DRAYHH_ULTRA_GRAY"

	-- Apenas 15% de redução da saturação
	gray.Saturation = -0.15
	gray.Contrast = 0
	gray.Brightness = 0

	gray.Enabled = true
	gray.Parent = Lighting

	--====================================================--
	-- POST EFFECTS
	--====================================================--

	for _, obj in ipairs(Lighting:GetDescendants()) do

		if obj:IsA("PostEffect") and obj ~= gray then

			pcall(function()
				obj.Enabled = false
			end)

		elseif obj:IsA("Atmosphere") then

			pcall(function()
				obj.Density = 0
				obj.Haze = 0
				obj.Glare = 0
			end)

		end

	end

	--====================================================--
	-- CÉU
	--====================================================--

	for _, obj in ipairs(Lighting:GetChildren()) do

		if obj:IsA("Sky") then
			obj:Destroy()
		end

	end

	local sky = Instance.new("Sky")
	sky.Name = "DRAYHH_ULTRA_GRAY_SKY"

	pcall(function()
		sky.CelestialBodiesShown = false
	end)

	pcall(function()
		sky.StarCount = 0
	end)

	sky.SkyboxBk = ""
	sky.SkyboxDn = ""
	sky.SkyboxFt = ""
	sky.SkyboxLf = ""
	sky.SkyboxRt = ""
	sky.SkyboxUp = ""

	sky.Parent = Lighting

	--====================================================--
	-- MAPA
	--====================================================--

	for _, obj in ipairs(Workspace:GetDescendants()) do
		ultraGrayPart(obj)
	end

	--====================================================--
	-- TERRAIN
	--====================================================--

	local terrain = Workspace:FindFirstChildOfClass("Terrain")

	if terrain then

		pcall(function()
			terrain.Decoration = false
		end)

		pcall(function()
			terrain.WaterWaveSize = 0
		end)

		pcall(function()
			terrain.WaterWaveSpeed = 0
		end)

		pcall(function()
			terrain.WaterReflectance = 0
		end)

		pcall(function()
			terrain.WaterTransparency = 1
		end)

	end

	--====================================================--
	-- PERSONAGENS
	--====================================================--

	for _, player in ipairs(Players:GetPlayers()) do

		local character = player.Character

		if character then

			for _, obj in ipairs(character:GetDescendants()) do

				if obj:IsA("Shirt")
				or obj:IsA("Pants")
				or obj:IsA("ShirtGraphic") then

					pcall(function()
						obj:Destroy()
					end)

				elseif obj:IsA("Accessory") then

					pcall(function()
						obj:Destroy()
					end)

				elseif obj:IsA("Decal")
				or obj:IsA("Texture") then

					pcall(function()
						obj.Transparency = 1
					end)

				else

					ultraGrayPart(obj)

				end

			end

		end

	end

end


local function ultraLow()

	ultraLowVisuals()

end

--========================================================--
-- FPS BOOST
--========================================================--

Boost.MouseButton1Click:Connect(function()

	boostEnabled = not boostEnabled

	if boostEnabled then

		removeEffects()
		minimumGraphics()

		Boost.Text = "FPS BOOST: ON"

	else

		Boost.Text = "FPS BOOST: OFF"

	end

end)

--========================================================--
-- ULTRA LOW BUTTON
--========================================================--

Ultra.MouseButton1Click:Connect(function()

	ultraEnabled = not ultraEnabled

	if ultraEnabled then

		Ultra.Text = "ULTRA LOW: ON"

		ultraLow()

	else

		Ultra.Text = "ULTRA LOW: OFF"

	end

end)

--========================================================--
-- GET KEY
--========================================================--

GetKey.MouseButton1Click:Connect(function()

	local copied = false

	if typeof(setclipboard) == "function" then

		copied = pcall(function()
			setclipboard(GET_KEY_LINK)
		end)

	end

	if copied then
		GetKey.Text = "LINK COPIADO!"
	else
		GetKey.Text = "COPIE O LINK MANUALMENTE"
	end

	task.delay(1.5,function()

		if GetKey and GetKey.Parent then
			GetKey.Text = "GET KEY"
		end

	end)

end)

--========================================================--
-- CHECK KEY
--========================================================--

Check.MouseButton1Click:Connect(function()

	if KeyBox.Text == VALID_KEY then

		Status.Text = "KEY VALID!"
		Status.TextColor3 = Color3.fromRGB(80,255,120)

		task.wait(0.5)

		KeyMenu.Visible = false
		Menu.Visible = true
		Open.Visible = true

	else

		Status.Text = "KEY INVALID!"
		Status.TextColor3 = Color3.fromRGB(255,80,80)

	end

end)

--========================================================--
-- ABRIR / FECHAR
--========================================================--

Open.MouseButton1Click:Connect(function()

	Menu.Visible = not Menu.Visible

end)

--========================================================--
-- RESPAWN
--========================================================--

Player.CharacterAdded:Connect(function(character)

	task.wait(1)

	if boostEnabled then

		removeEffects()
		minimumGraphics()

		Boost.Text = "FPS BOOST: ON"

	end

	if ultraEnabled then

		ultraLow()

		Ultra.Text = "ULTRA LOW: ON"

	end

end)

--========================================================--
-- NOVOS OBJETOS
--========================================================--

Workspace.DescendantAdded:Connect(function(obj)

	if not ultraEnabled then
		return
	end

	task.defer(function()

		if not obj or not obj.Parent then
			return
		end

		ultraGrayPart(obj)

	end)

end)

--========================================================--
-- FIM
--========================================================--
