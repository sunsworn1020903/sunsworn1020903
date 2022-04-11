speaker=Game.Players.localPlayer
chart=speaker.Character
core=Game.CoreGui
text=" script, v1.00, made by sunsworn1"

ins={
   but=Instance.new
}

screen=ins.but("ScreenGui", core)
hidemain=ins.but("Frame", screen)
main2=ins.but("Frame", screen)
main=ins.but("ScrollingFrame", main2)
title=ins.but("TextLabel", main2)
Button1=ins.but("TextButton", hidemain)
Button2=ins.but("TextButton", main)
Label1=ins.but("TextLabel", main)
Button3=ins.but("TextButton", main)

function des(target)
    target:Destroy()
    end

 color={
    border=Color3.new(0,0,0),
    background=Color3.new(0,1,1)

    
}

pos={
    posleft=UDim2.new(0, 4, 0, 15),
    posright=UDim2.new(0, 205, 0, 15),
    posbos=UDim2.new(0, 150, 0, 13),
    posboz2=UDim2.new(0, 150, 0, 65),
    size=UDim2.new(0, 91, 0, 32),
    posbosright=UDim2.new(0, 0, 0, 65),
    posbosleft=UDim2.new(0, 4, 0, 55)
    
}
screen.Name="screen"


hidemain.Name = "hidemain"
hidemain.Active = false
hidemain.BackgroundColor3 = color.background
hidemain.BorderColor3 = Color3.new(0,0,0)
hidemain.Draggable = false
hidemain.ZIndex=100
hidemain.Position = UDim2.new(1, -249, 1, -40)
hidemain.BorderSizePixel=5
hidemain.Size = UDim2.new(0, 85, 0, 27)
hidemain.ClipsDescendants = true


main2.Name = "main2"
main2.Active = true
main2.BackgroundColor3 = color.background
main2.BorderColor3 = Color3.new(0, 0, 0)
main2.Draggable = true
main2.BorderSizePixel=2
main2.Visible=false
main2.ZIndex=100
main2.BackgroundTransparency=0
main2.Position = UDim2.new(1, -496, 1, -578)
main2.Size = UDim2.new(0, 302, 0, 424)
main2.ClipsDescendants = true


main.Name = "main"
main.Active = false
main.BackgroundColor3 = color.background
main.BorderColor3 = Color3.new(0, 0, 0)
main.Draggable = false
main.BorderSizePixel=1
main.BackgroundTransparency=0
main.Visible=true
main.ZIndex=200
main.ScrollBarImageColor3=Color3.new(0,0,0)
main.BackgroundTransparency=.3
main.Position = UDim2.new(1,-301,1,-387)
main.Size = UDim2.new(0, 300, 0, 386)
main.ClipsDescendants = true
main.CanvasSize=UDim2.new(0,0,2,0)
main.ScrollingDirection="Y"
main.ScrollBarImageTransparency=0
main.ScrollBarThickness=6


title.Name = "title"
title.BackgroundColor3 = color.background
title.BackgroundTransparency=1
title.Size = UDim2.new(0,295,0,30)
title.Position = UDim2.new(0, 2, 0, 3)
title.Font = Enum.Font.Cartoon
title.BorderSizePixel = 1
title.ZIndex=200
title.BorderColor3 = color.border
title.Text = "Remote spy"..text
title.TextColor3 = Color3.new(0,0,0)
title.TextSize = 19
title.TextWrapped = true
title.TextScaled = true


Button1.Name = "Button1"
Button1.BackgroundColor3 = color.background
Button1.Position = UDim2.new(0,0,0,0)
Button1.Size = UDim2.new(0, 85, 0, 27)
Button1.Font = Enum.Font.Cartoon
Button1.Text = "OPEN"
Button1.BorderSizePixel = 0
Button1.BorderColor3 = color.border
Button1.TextColor3 = Color3.new(0,0,0)
Button1.TextScaled=false
Button1.TextSize = 19
Button1.ZIndex=300
Button1.TextWrapped=false
Button1.MouseButton1Click:Connect(function()
    if Button1.Text=="OPEN" then
Button1.Text="CLOSE"
    main2.Visible=true
elseif Button1.Text=="CLOSE" then
Button1.Text="OPEN"
    main2.Visible=false
end
    end)


Button2.Name = "Button2"
Button2.BackgroundColor3 = color.background
Button2.Position = pos.posleft
Button2.Size = UDim2.new(0, 85, 0, 27)
Button2.Font = Enum.Font.Fantasy
Button2.Text = "Copy"
Button2.Draggable=false
Button2.BorderSizePixel = 1
Button2.BorderColor3 = color.border
Button2.TextColor3 = Color3.new(0,0,0)
Button2.TextScaled=false
Button2.TextSize = 14
Button2.ZIndex=300
Button2.TextWrapped=false
Button2.MouseButton1Click:Connect(function()
   setclipboard(Label1.Text)
end)


Label1.Name = "Label1"
Label1.BackgroundColor3 = color.background
Label1.BackgroundTransparency=0
Label1.Size = UDim2.new(0,195,0,200)
Label1.Position = UDim2.new(0, 92, 0, 15)
Label1.Font = Enum.Font.Legacy
Label1.TextYAlignment="Top"
Label1.BorderSizePixel = 1
Label1.ZIndex=300
Label1.BorderColor3 = color.border
Label1.Draggable=true
Label1.Text = ""
Label1.TextColor3 = Color3.new(0,0,0)
Label1.TextSize = 19
Label1.TextWrapped = true
Label1.TextScaled = true


Button3.Name = "Button3"
Button3.BackgroundColor3 = color.background
Button3.Position = pos.posbosleft
Button3.Size = UDim2.new(0, 85, 0, 27)
Button3.Font = Enum.Font.Fantasy
Button3.Text = "Clear"
Button3.Draggable=false
Button3.BorderSizePixel = 1
Button3.BorderColor3 = color.border
Button3.TextColor3 = Color3.new(0,0,0)
Button3.TextScaled=false
Button3.TextSize = 14
Button3.ZIndex=300
Button3.TextWrapped=false
Button3.MouseButton1Click:Connect(function()
   Label1.Text=""
end)


--[[

	-Created by Vaeb.

]]

_G.scanRemotes = true

_G.ignoreNames = {
	Event = true;
	MessagesChanged = true;
}

setreadonly(getrawmetatable(game), false)
local pseudoEnv = {}
local gameMeta = getrawmetatable(game)

local tabChar = "      "

local function getSmaller(a, b, notLast)
	local aByte = a:byte() or -1
	local bByte = b:byte() or -1
	if aByte == bByte then
		if notLast and #a == 1 and #b == 1 then
			return -1
		elseif #b == 1 then
			return false
		elseif #a == 1 then
			return true
		else
			return getSmaller(a:sub(2), b:sub(2), notLast)
		end
	else
		return aByte < bByte
	end
end

local function parseData(obj, numTabs, isKey, overflow, noTables, forceDict)
	local objType = typeof(obj)
	local objStr = tostring(obj)
	if objType == "table" then
		if noTables then
			return objStr
		end
		local isCyclic = overflow[obj]
		overflow[obj] = true
		local out = {}
		local nextIndex = 1
		local isDict = false
		local hasTables = false
		local data = {}

		for key, val in next, obj do
			if not hasTables and typeof(val) == "table" then
				hasTables = true
			end

			if not isDict and key ~= nextIndex then
				isDict = true
			else
				nextIndex = nextIndex + 1
			end

			data[#data+1] = {key, val}
		end

		if isDict or hasTables or forceDict then
			out[#out+1] = (isCyclic and "Cyclic " or "") .. "{"
			table.sort(data, function(a, b)
				local aType = typeof(a[2])
				local bType = typeof(b[2])
				if bType == "string" and aType ~= "string" then
					return false
				end
				local res = getSmaller(aType, bType, true)
				if res == -1 then
					return getSmaller(tostring(a[1]), tostring(b[1]))
				else
					return res
				end
			end)
			for i = 1, #data do
				local arr = data[i]
				local nowKey = arr[1]
				local nowVal = arr[2]
				local parseKey = parseData(nowKey, numTabs+1, true, overflow, isCyclic)
				local parseVal = parseData(nowVal, numTabs+1, false, overflow, isCyclic)
				if isDict then
					local nowValType = typeof(nowVal)
					local preStr = ""
					local postStr = ""
					if i > 1 and (nowValType == "table" or typeof(data[i-1][2]) ~= nowValType) then
						preStr = "\n"
					end
					if i < #data and nowValType == "table" and typeof(data[i+1][2]) ~= "table" and typeof(data[i+1][2]) == nowValType then
						postStr = "\n"
					end
					out[#out+1] = preStr .. string.rep(tabChar, numTabs+1) .. parseKey .. " = " .. parseVal .. ";" .. postStr
				else
					out[#out+1] = string.rep(tabChar, numTabs+1) .. parseVal .. ";"
				end
			end
			out[#out+1] = string.rep(tabChar, numTabs) .. "}"
		else
			local data2 = {}
			for i = 1, #data do
				local arr = data[i]
				local nowVal = arr[2]
				local parseVal = parseData(nowVal, 0, false, overflow, isCyclic)
				data2[#data2+1] = parseVal
			end
			out[#out+1] = "{" .. table.concat(data2, ", ") .. "}"
		end

		return table.concat(out, "\n")
	else
		local returnVal = nil
		if (objType == "string" or objType == "Content") and (not isKey or tonumber(obj:sub(1, 1))) then
			local retVal = '"' .. objStr .. '"'
			if isKey then
				retVal = "[" .. retVal .. "]"
			end
			returnVal = retVal
		elseif objType == "EnumItem" then
			returnVal = "Enum." .. tostring(obj.EnumType) .. "." .. obj.Name
		elseif objType == "Enum" then
			returnVal = "Enum." .. objStr
		elseif objType == "Instance" then
			returnVal = obj.Parent and obj:GetFullName() or obj.ClassName
		elseif objType == "CFrame" then
			returnVal = "CFrame.new(" .. objStr .. ")"
		elseif objType == "Vector3" then
			returnVal = "Vector3.new(" .. objStr .. ")"
		elseif objType == "Vector2" then
			returnVal = "Vector2.new(" .. objStr .. ")"
		elseif objType == "UDim2" then
			returnVal = "UDim2.new(" .. objStr:gsub("[{}]", "") .. ")"
		elseif objType == "BrickColor" then
			returnVal = "BrickColor.new(\"" .. objStr .. "\")"
		elseif objType == "Color3" then
			returnVal = "Color3.new(" .. objStr .. ")"
		elseif objType == "NumberRange" then
			returnVal = "NumberRange.new(" .. objStr:gsub("^%s*(.-)%s*$", "%1"):gsub(" ", ", ") .. ")"
		elseif objType == "PhysicalProperties" then
			returnVal = "PhysicalProperties.new(" .. objStr .. ")"
		else
			returnVal = objStr
		end
		return returnVal
	end
end

function tableToString(t)
	return parseData(t, 0, false, {}, nil, false)
end

local detectClasses = {
	BindableEvent = true;
	BindableFunction = true;
	RemoteEvent = true;
	RemoteFunction = true;
}

local classMethods = {
	BindableEvent = "Fire";
	BindableFunction = "Invoke";
	RemoteEvent = "FireServer";
	RemoteFunction = "InvokeServer";
}

local realMethods = {}

for name, enabled in next, detectClasses do
	if enabled then
		realMethods[classMethods[name]] = Instance.new(name)[classMethods[name]]
	end
end

for key, value in next, gameMeta do pseudoEnv[key] = value end

local incId = 0

local function getValues(self, key, ...)
	return {realMethods[key](self, ...)}
end

gameMeta.__index, gameMeta.__namecall = function(self, key)
	if not realMethods[key] or _G.ignoreNames[self.Name] or not _G.scanRemotes then return pseudoEnv.__index(self, key) end
	return function(_, ...)
		incId = incId + 1
		local nowId = incId
		local strId = "[RemoteSpy_" .. nowId .. "]"

		local allPassed = {...}
		local returnValues = {}

		local ok, data = pcall(getValues, self, key, ...)

		if ok then
			returnValues = data
			print("\n".. self:GetFullName() .. ":" .. key .. "\n" .. tableToString(allPassed) .. "\n"  .. tableToString(returnValues) .. "\n")
		else
			print("\n" .. self:GetFullName() .. ":" .. key .. "\n" .. tableToString(allPassed) .. "\n" .. data .. "\n")
		end

		return unpack(returnValues)
	end
end

print("\nRan Vaeb's RemoteSpy\n")
--[[

	-Created by Vaeb.

]]

_G.scanRemotes = true

_G.ignoreNames = {
	Event = true;
	MessagesChanged = true;
}

setreadonly(getrawmetatable(game), false)
local pseudoEnv = {}
local gameMeta = getrawmetatable(game)

local tabChar = "      "

local function getSmaller(a, b, notLast)
	local aByte = a:byte() or -1
	local bByte = b:byte() or -1
	if aByte == bByte then
		if notLast and #a == 1 and #b == 1 then
			return -1
		elseif #b == 1 then
			return false
		elseif #a == 1 then
			return true
		else
			return getSmaller(a:sub(2), b:sub(2), notLast)
		end
	else
		return aByte < bByte
	end
end

local function parseData(obj, numTabs, isKey, overflow, noTables, forceDict)
	local objType = typeof(obj)
	local objStr = tostring(obj)
	if objType == "table" then
		if noTables then
			return objStr
		end
		local isCyclic = overflow[obj]
		overflow[obj] = true
		local out = {}
		local nextIndex = 1
		local isDict = false
		local hasTables = false
		local data = {}

		for key, val in next, obj do
			if not hasTables and typeof(val) == "table" then
				hasTables = true
			end

			if not isDict and key ~= nextIndex then
				isDict = true
			else
				nextIndex = nextIndex + 1
			end

			data[#data+1] = {key, val}
		end

		if isDict or hasTables or forceDict then
			out[#out+1] = (isCyclic and "Cyclic " or "") .. "{"
			table.sort(data, function(a, b)
				local aType = typeof(a[2])
				local bType = typeof(b[2])
				if bType == "string" and aType ~= "string" then
					return false
				end
				local res = getSmaller(aType, bType, true)
				if res == -1 then
					return getSmaller(tostring(a[1]), tostring(b[1]))
				else
					return res
				end
			end)
			for i = 1, #data do
				local arr = data[i]
				local nowKey = arr[1]
				local nowVal = arr[2]
				local parseKey = parseData(nowKey, numTabs+1, true, overflow, isCyclic)
				local parseVal = parseData(nowVal, numTabs+1, false, overflow, isCyclic)
				if isDict then
					local nowValType = typeof(nowVal)
					local preStr = ""
					local postStr = ""
					if i > 1 and (nowValType == "table" or typeof(data[i-1][2]) ~= nowValType) then
						preStr = "\n"
					end
					if i < #data and nowValType == "table" and typeof(data[i+1][2]) ~= "table" and typeof(data[i+1][2]) == nowValType then
						postStr = "\n"
					end
					out[#out+1] = preStr .. string.rep(tabChar, numTabs+1) .. parseKey .. " = " .. parseVal .. ";" .. postStr
				else
					out[#out+1] = string.rep(tabChar, numTabs+1) .. parseVal .. ";"
				end
			end
			out[#out+1] = string.rep(tabChar, numTabs) .. "}"
		else
			local data2 = {}
			for i = 1, #data do
				local arr = data[i]
				local nowVal = arr[2]
				local parseVal = parseData(nowVal, 0, false, overflow, isCyclic)
				data2[#data2+1] = parseVal
			end
			out[#out+1] = "{" .. table.concat(data2, ", ") .. "}"
		end

		return table.concat(out, "\n")
	else
		local returnVal = nil
		if (objType == "string" or objType == "Content") and (not isKey or tonumber(obj:sub(1, 1))) then
			local retVal = '"' .. objStr .. '"'
			if isKey then
				retVal = "[" .. retVal .. "]"
			end
			returnVal = retVal
		elseif objType == "EnumItem" then
			returnVal = "Enum." .. tostring(obj.EnumType) .. "." .. obj.Name
		elseif objType == "Enum" then
			returnVal = "Enum." .. objStr
		elseif objType == "Instance" then
			returnVal = obj.Parent and obj:GetFullName() or obj.ClassName
		elseif objType == "CFrame" then
			returnVal = "CFrame.new(" .. objStr .. ")"
		elseif objType == "Vector3" then
			returnVal = "Vector3.new(" .. objStr .. ")"
		elseif objType == "Vector2" then
			returnVal = "Vector2.new(" .. objStr .. ")"
		elseif objType == "UDim2" then
			returnVal = "UDim2.new(" .. objStr:gsub("[{}]", "") .. ")"
		elseif objType == "BrickColor" then
			returnVal = "BrickColor.new(\"" .. objStr .. "\")"
		elseif objType == "Color3" then
			returnVal = "Color3.new(" .. objStr .. ")"
		elseif objType == "NumberRange" then
			returnVal = "NumberRange.new(" .. objStr:gsub("^%s*(.-)%s*$", "%1"):gsub(" ", ", ") .. ")"
		elseif objType == "PhysicalProperties" then
			returnVal = "PhysicalProperties.new(" .. objStr .. ")"
		else
			returnVal = objStr
		end
		return returnVal
	end
end

function tableToString(t)
	return parseData(t, 0, false, {}, nil, false)
end

local detectClasses = {
	BindableEvent = true;
	BindableFunction = true;
	RemoteEvent = true;
	RemoteFunction = true;
}

local classMethods = {
	BindableEvent = "Fire";
	BindableFunction = "Invoke";
	RemoteEvent = "FireServer";
	RemoteFunction = "InvokeServer";
}

local realMethods = {}

for name, enabled in next, detectClasses do
	if enabled then
		realMethods[classMethods[name]] = Instance.new(name)[classMethods[name]]
	end
end

for key, value in next, gameMeta do pseudoEnv[key] = value end

local incId = 0

local function getValues(self, key, ...)
	return {realMethods[key](self, ...)}
end

gameMeta.__index, gameMeta.__namecall = function(self, key)
	if not realMethods[key] or _G.ignoreNames[self.Name] or not _G.scanRemotes then return pseudoEnv.__index(self, key) end
	return function(_, ...)
		incId = incId + 1
		local nowId = incId
		local strId = "[RemoteSpy_" .. nowId .. "]"

		local allPassed = {...}
		local returnValues = {}

		local ok, data = pcall(getValues, self, key, ...)

		if ok then
			returnValues = data
			Label1.Text=("\n".. self:GetFullName() .. ":" .. key .. "\n" .. tableToString(allPassed) .. "\n"  .. tableToString(returnValues) .. "\n")
		else
			Label1.Text=("\n" .. self:GetFullName() .. ":" .. key .. "\n" .. tableToString(allPassed) .. "\n" .. data .. "\n")
		end

		return unpack(returnValues)
	end
end

print("\nRan Vaeb's RemoteSpy\n")


function rain()
    script=ins.but("Script", hidemain)
script.Name="Rainbow"

while true do
		script.Parent.BorderColor3 = Color3.new(255/255,0/255,0/255)
		for i = 0,255,10 do
			wait()
			script.Parent.BorderColor3 = Color3.new(255/255,i/255,0/255)
		end
		for i = 255,0,-10 do
			wait()
			script.Parent.BorderColor3 = Color3.new(i/255,255/255,0/255)
		end
		for i = 0,255,10 do
			wait()
			script.Parent.BorderColor3= Color3.new(0/255,255/255,i/255)
		end
		for i = 255,0,-10 do
			wait()
			script.Parent.BorderColor3= Color3.new(0/255,i/255,255/255)
		end
		for i = 0,255,10 do
			wait()
			script.Parent.BorderColor3= Color3.new(i/255,0/255,255/255)
		end
		for i = 255,0,-10 do
			wait()
			script.Parent.BorderColor3= Color3.new(255/255,0/255,i/255)
end
end
end
coroutine.wrap(rain)()


