-- Services
local HttpService = game:GetService("HttpService")

-- Variables
local vynixuModules = {
    Functions = loadstring(game:HttpGet("https://raw.githubusercontent.com/RegularVynixu/Utilities/main/Functions.lua"))()
}
local module = {}

-- Functions
local function getInviteCode(sInvite)
    local customPattern = "yourcustomdomain%.com/invite/([%w-_]+)"
    local discordPattern = "discord%.com/invite/([%w-_]+)"
    local customCode = sInvite:match(customPattern)
    local discordCode = sInvite:match(discordPattern)

    if customCode then
        return customCode
    elseif discordCode then
        return discordCode
    else
        for i = #sInvite, 1, -1 do
            local char = sInvite:sub(i, i)
            if char == "/" then
                return sInvite:sub(i + 1, #sInvite)
            end
        end
    end
    return sInvite
end

local function openURL(url)
    request({
        Url = url,
        Method = "GET"
    })
end

module.Join = function(sInvite)
    assert(type(sInvite) == "string", "<string> Invalid invite provided")
    local inviteCode = getInviteCode(sInvite)
    if inviteCode then
        local url = "https://yourcustomdomain.com/invite/" .. inviteCode
        openURL(url)
    end
end

-- Main
return module
