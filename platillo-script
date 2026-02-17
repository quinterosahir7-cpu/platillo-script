script.lua
local PLATILLO_TAMANO = Vector3.new(600, 6, 600)
local PLATILLO_POSICION = Vector3.new(0, 80, 0)

local function esNPC(model)
	if model:IsA("Model") then
		local humanoid = model:FindFirstChildOfClass("Humanoid")
		local player = game.Players:GetPlayerFromCharacter(model)
		if humanoid and not player then
			return true
		end
	end
	return false
end

for _, obj in pairs(workspace:GetDescendants()) do
	if obj:IsA("ParticleEmitter")
	or obj:IsA("Smoke")
	or obj:IsA("Fire")
	or obj:IsA("Trail")
	or obj:IsA("Beam") then
		obj.Enabled = false
	end
end

for _, obj in pairs(workspace:GetChildren()) do
	if obj:IsA("Model") then
		if not esNPC(obj) then
			obj:Destroy()
		end
	else
		obj:Destroy()
	end
end

local platillo = Instance.new("Part")
platillo.Name = "PlatilloGigante"
platillo.Size = PLATILLO_TAMANO
platillo.Position = PLATILLO_POSICION
platillo.Anchored = true
platillo.CanCollide = true
platillo.Material = Enum.Material.SmoothPlastic
platillo.Color = Color3.fromRGB(170, 170, 170)
platillo.Parent = workspace
