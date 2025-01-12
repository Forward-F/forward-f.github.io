# Hello I Am Forward



**Nightime Code**


-- forward created this!!

local Vignette = true -- change to false if you don't want a shadow frame

local Lighting = game:GetService("Lighting")
local StarterGui = game:GetService("StarterGui")
local Bloom = Instance.new("BloomEffect")
local Blur = Instance.new("BlurEffect")
local ColorCor = Instance.new("ColorCorrectionEffect")
local SunRays = Instance.new("SunRaysEffect")
local Sky = Instance.new("Sky")
local Atm = Instance.new("Atmosphere")

for i, v in pairs(Lighting:GetChildren()) do
	if v then
		v:Destroy()
	end
end

Bloom.Parent = Lighting
Blur.Parent = Lighting
ColorCor.Parent = Lighting
SunRays.Parent = Lighting
Sky.Parent = Lighting
Atm.Parent = Lighting

if Vignette == true then
	local Gui = Instance.new("ScreenGui")
	Gui.Parent = StarterGui
	Gui.IgnoreGuiInset = true

	local ShadowFrame = Instance.new("ImageLabel")
	ShadowFrame.Parent = Gui
	ShadowFrame.AnchorPoint = Vector2.new(0.5, 1)
	ShadowFrame.Position = UDim2.new(0.5, 0, 1, 0)
	ShadowFrame.Size = UDim2.new(1, 0, 1.05, 0)
	ShadowFrame.BackgroundTransparency = 1
	ShadowFrame.Image = "rbxassetid://4576475446"
	ShadowFrame.ImageTransparency = 0.7
	ShadowFrame.ZIndex = 10
end

Bloom.Intensity = 0.4
Bloom.Size = 15
Bloom.Threshold = 1

Blur.Size = 1.5

ColorCor.Brightness = 0.2
ColorCor.Contrast = 0.5
ColorCor.Saturation = -0.3
ColorCor.TintColor = Color3.fromRGB(150, 170, 220)

SunRays.Intensity = 0.05 -- Soft glow to simulate moon rays
SunRays.Spread = 0.8

Lighting.Ambient = Color3.fromRGB(100, 100, 150)
Lighting.Brightness = 1.5 -- Increased brightness for moonlight
Lighting.ColorShift_Bottom = Color3.fromRGB(20, 20, 40)
Lighting.ColorShift_Top = Color3.fromRGB(120, 140, 180)
Lighting.EnvironmentDiffuseScale = 0.4
Lighting.EnvironmentSpecularScale = 0.3
Lighting.GlobalShadows = true
Lighting.OutdoorAmbient = Color3.fromRGB(70, 70, 100)
Lighting.ShadowSoftness = 0.3
Lighting.ClockTime = 20 -- Nighttime (8 PM)
Lighting.GeographicLatitude = 0
Lighting.ExposureCompensation = 0.5 -- Slightly boost visibility

Atm.Density = 0.2
Atm.Offset = 0.2
Atm.Color = Color3.fromRGB(60, 70, 100)
Atm.Decay = Color3.fromRGB(40, 50, 70)
Atm.Glare = 0.3
Atm.Haze = 0.8

-- Skybox setup for nighttime
Sky.SkyboxBk = "rbxassetid://7018684000"
Sky.SkyboxDn = "rbxassetid://7018684000"
Sky.SkyboxFt = "rbxassetid://7018684000"
Sky.SkyboxLf = "rbxassetid://7018684000"
Sky.SkyboxRt = "rbxassetid://7018684000"
Sky.SkyboxUp = "rbxassetid://7018684000"
Sky.MoonAngularSize = 15
Sky.StarCount = 500

print("Moonlit nighttime settings applied!")

script:Destroy()
