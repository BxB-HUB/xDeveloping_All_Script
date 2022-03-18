
local Players = game:GetService("Players")
local LP = Players.LocalPlayer
local StarterGui = game:GetService('StarterGui')
for i=1, 15 do
    local r = pcall(StarterGui["SetCore"])
    if r then break end
    game:GetService('RunService').RenderStepped:wait()
end
wait()
local marketplaceService = game:GetService("MarketplaceService")
local isSuccessful, info = pcall(marketplaceService.GetProductInfo, marketplaceService, game.PlaceId)



local properties = {
    Color = Color3.new(0,255,222);
    Font = Enum.Font.SourceSansItalic;
    TextSize = 17.5; 
}





properties.Text = "╔══════════════════ ⚙ [ xDeveloper ] ⚙  ═══════════════════╗ "
StarterGui:SetCore("ChatMakeSystemMessage", properties)
properties.Text = "║ ◈ "..tostring(os.date("Time Global  | ".." %I:%M %p  ".."|".."  %H:%M:%S ")).."Your Execute!"
StarterGui:SetCore("ChatMakeSystemMessage", properties)
properties.Text = "║ ◈ [xDeveloper] The Best Translate"
StarterGui:SetCore("ChatMakeSystemMessage", properties)
properties.Text = "║ ◈ [xDeveloper] Player Name > "..game.Players.LocalPlayer.Name.." OR "..game.Players.LocalPlayer.DisplayName
StarterGui:SetCore("ChatMakeSystemMessage", properties)
properties.Text = "║ ◈ [xDeveloper] Check Game > "..info.Name
StarterGui:SetCore("ChatMakeSystemMessage", properties)
properties.Text = "║ ◈ [xDeveloper] Game PlaceId  > " ..game.PlaceId
StarterGui:SetCore("ChatMakeSystemMessage", properties)
properties.Text = "╚═══════════════════════════════════════════════.★.╝"
StarterGui:SetCore("ChatMakeSystemMessage", properties)

if not game['Loaded'] then game['Loaded']:Wait() end; repeat wait(.06) until game:GetService('Players').LocalPlayer ~= nil
local YourLang = "th" -- Language code that the messages are going to be translated to ---- รหัสภาษาที่จะแปลข้อความให้

local googlev = isfile'googlev.txt' and readfile'googlev.txt' or ''

function googleConsent(Body) -- Because google really said: "Fuck you."
    local args = {}

    for match in Body:gmatch('<input type="hidden" name=".-" value=".-">') do
        local k,v = match:match('<input type="hidden" name="(.-)" value="(.-)">')
        args[k] = v
    end
    googlev = args.v
    writefile('googlev.txt', args.v)
end

local function got(url, Method, Body) -- Basic version of https://www.npmjs.com/package/got using synapse's request API for google websites
    Method = Method or "GET"
    
    local res = syn.request({
        Url = url,
        Method = Method,
        Headers = {cookie="CONSENT=YES+"..googlev},
        Body = Body
    })
    
    if res.Body:match('https://consent.google.com/s') then
        print('consent')
        googleConsent(res.Body)
        res = syn.request({
            Url = url,
            Method = "GET",
            Headers = {cookie="CONSENT=YES+"..googlev}
        })
    end
    
    return res
end

local languages = {
    auto = "Automatic",
    af = "Afrikaans",
    sq = "Albanian",
    am = "Amharic",
    ar = "Arabic",
    hy = "Armenian",
    az = "Azerbaijani",
    eu = "Basque",
    be = "Belarusian",
    bn = "Bengali",
    bs = "Bosnian",
    bg = "Bulgarian",
    ca = "Catalan",
    ceb = "Cebuano",
    ny = "Chichewa",
    ['zh-cn'] = "Chinese Simplified",
    ['zh-tw'] = "Chinese Traditional",
    co = "Corsican",
    hr = "Croatian",
    cs = "Czech",
    da = "Danish",
    nl = "Dutch",
    en = "English",
    eo = "Esperanto",
    et = "Estonian",
    tl = "Filipino",
    fi = "Finnish",
    fr = "French",
    fy = "Frisian",
    gl = "Galician",
    ka = "Georgian",
    de = "German",
    el = "Greek",
    gu = "Gujarati",
    ht = "Haitian Creole",
    ha = "Hausa",
    haw = "Hawaiian",
    iw = "Hebrew",
    hi = "Hindi",
    hmn = "Hmong",
    hu = "Hungarian",
    is = "Icelandic",
    ig = "Igbo",
    id = "Indonesian",
    ga = "Irish",
    it = "Italian",
    ja = "Japanese",
    jw = "Javanese",
    kn = "Kannada",
    kk = "Kazakh",
    km = "Khmer",
    ko = "Korean",
    ku = "Kurdish (Kurmanji)",
    ky = "Kyrgyz",
    lo = "Lao",
    la = "Latin",
    lv = "Latvian",
    lt = "Lithuanian",
    lb = "Luxembourgish",
    mk = "Macedonian",
    mg = "Malagasy",
    ms = "Malay",
    ml = "Malayalam",
    mt = "Maltese",
    mi = "Maori",
    mr = "Marathi",
    mn = "Mongolian",
    my = "Myanmar (Burmese)",
    ne = "Nepali",
    no = "Norwegian",
    ps = "Pashto",
    fa = "Persian",
    pl = "Polish",
    pt = "Portuguese",
    pa = "Punjabi",
    ro = "Romanian",
    ru = "Russian",
    sm = "Samoan",
    gd = "Scots Gaelic",
    sr = "Serbian",
    st = "Sesotho",
    sn = "Shona",
    sd = "Sindhi",
    si = "Sinhala",
    sk = "Slovak",
    sl = "Slovenian",
    so = "Somali",
    es = "Spanish",
    su = "Sundanese",
    sw = "Swahili",
    sv = "Swedish",
    tg = "Tajik",
    ta = "Tamil",
    te = "Telugu",
    th = "Thai",
    tr = "Turkish",
    uk = "Ukrainian",
    ur = "Urdu",
    uz = "Uzbek",
    vi = "Vietnamese",
    cy = "Welsh",
    xh = "Xhosa",
    yi = "Yiddish",
    yo = "Yoruba",
    zu = "Zulu"
};

function find(lang)
    for i,v in pairs(languages) do
        if i == lang or v == lang then
            return i
        end
    end
end

function isSupported(lang)
    local key = find(lang)
    return key and true or false 
end

function getISOCode(lang)
    local key = find(lang)
    return key
end

function stringifyQuery(dataFields)
    local data = ""
    for k, v in pairs(dataFields) do
        if type(v) == "table" then
            for _,v in pairs(v) do
                data = data .. ("&%s=%s"):format(
                    game.HttpService:UrlEncode(k),
                    game.HttpService:UrlEncode(v)
                )
            end
        else
            data = data .. ("&%s=%s"):format(
                game.HttpService:UrlEncode(k),
                game.HttpService:UrlEncode(v)
            )
        end
    end
    data = data:sub(2)
    return data
end

local reqid = math.random(1000,9999)
local rpcidsTranslate = "MkEWBc"
local rootURL = "https://translate.google.com/"
local executeURL = "https://translate.google.com/_/TranslateWebserverUi/data/batchexecute"
local fsid, bl

do -- init
	print('initialize')
    local InitialReq = got(rootURL)
    fsid = InitialReq.Body:match('"FdrFJe":"(.-)"')
    bl = InitialReq.Body:match('"cfb2h":"(.-)"')
end

local HttpService = game:GetService("HttpService")
function jsonE(o)
    return HttpService:JSONEncode(o)
end
function jsonD(o)
    return HttpService:JSONDecode(o)
end

function translate(str, to, from)
    reqid+=10000
    from = from and getISOCode(from) or 'auto'
    to = to and getISOCode(to) or 'en'

    local data = {{str, from, to, true}, {nil}}

    local freq = {
        {
            {
                rpcidsTranslate, 
                jsonE(data),
                nil,
                "generic"
            }
        }
    }

    local url = executeURL..'?'..stringifyQuery{rpcids = rpcidsTranslate, ['f.sid'] = fsid, bl = bl, hl="en", _reqid = reqid-10000, rt = 'c'}
    local body = stringifyQuery{['f.req'] = jsonE(freq)}
    
    local req = got(url, "POST", body)
	
    local body = jsonD(req.Body:match'%[.-%]\n')
    local translationData = jsonD(body[1][3])
    local result = {
        text = "",
        from = {
            language = "",
            text = ""
        },
        raw = ""
    }
    result.raw = translationData
    result.text = translationData[2][1][1][6][1][1]
    
    result.from.language = translationData[3]
    result.from.text = translationData[2][5][1]

    return result
end

local Players = game:GetService("Players")
local LP = Players.LocalPlayer
local StarterGui = game:GetService('StarterGui')
for i=1, 15 do
    local r = pcall(StarterGui["SetCore"])
    if r then break end
    game:GetService('RunService').RenderStepped:wait()
end
wait()

local properties = {
    Color = Color3.new(255,0,0);
    Font = Enum.Font.SourceSansItalic;
    TextSize = 17;
}

game:GetService("StarterGui"):SetCore("SendNotification",
    {
        Title = "Chat Translator",
        Text = "Ported to Google Translate",
        Duration = 3
    }
)
properties.Text = "╔══════════════════ ⚙ [ How To Use] ⚙  ═══════════════════╗ "
StarterGui:SetCore("ChatMakeSystemMessage", properties)
properties.Text = "║ ◈ [xDev-EN] To send messages in a language, say > followed by the target language/language \n║ ◈ code, e.g.: >en or >th. To disable (go back to original language), say >d."
StarterGui:SetCore("ChatMakeSystemMessage", properties)
properties.Text = "╠═════════════════ ⚙ [ Thai language ] ⚙ ═══════════════════"
StarterGui:SetCore("ChatMakeSystemMessage", properties)
properties.Text = "║ ◈ [xDev-TH] หากต้องการส่งข้อความในภาษา ให้พูด > ตามด้วยรหัสภาษา/ภาษาเป้าหมาย \n║ ◈ เช่น >en หรือ >th หากต้องการปิดใช้งาน (กลับไปที่ภาษาต้นฉบับ) ให้พูด >d"
StarterGui:SetCore("ChatMakeSystemMessage", properties)
properties.Text = "╚═══════════════════════════════════════════════.★.╝"
StarterGui:SetCore("ChatMakeSystemMessage", properties)




local properties = {
    Color = Color3.new(0,0,255);
    Font = Enum.Font.SourceSansItalic;
    TextSize = 17.5; 
}
properties.Text = "╔══════════════════ ⚙ [ Language ] ⚙  ════════════════════╗ "
StarterGui:SetCore("ChatMakeSystemMessage", properties)
if YourLang == "th" then
    properties.Text = ("║ ◈ Your Select Language is Thialand Language!")
    StarterGui:SetCore("ChatMakeSystemMessage", properties)
elseif YourLang == "en" then
    properties.Text = ("║ ◈ Your Select Language is English Language!")
    StarterGui:SetCore("ChatMakeSystemMessage", properties)
elseif YourLang == "auto" then
    properties.Text = ("║ ◈ Your Select Language is Automatic Language!")
    StarterGui:SetCore("ChatMakeSystemMessage", properties)
elseif YourLang == "af" then
    properties.Text = ("║ ◈ Your Select Language is Afrikaans Language!")
    StarterGui:SetCore("ChatMakeSystemMessage", properties)
elseif YourLang == "sq" then
    properties.Text = ("║ ◈ Your Select Language is Albanian Language!")
    StarterGui:SetCore("ChatMakeSystemMessage", properties)
elseif YourLang == "am" then
    properties.Text = ("║ ◈ Your Select Language is Amharic Language!")
    StarterGui:SetCore("ChatMakeSystemMessage", properties)
elseif YourLang == "ar" then
    properties.Text = ("║ ◈ Your Select Language is Arabic Language!")
    StarterGui:SetCore("ChatMakeSystemMessage", properties)
elseif YourLang == "hy" then
    properties.Text = ("║ ◈ Your Select Language is Armenian Language!")
    StarterGui:SetCore("ChatMakeSystemMessage", properties)
elseif YourLang == "tl" then
    properties.Text = ("║ ◈ Your Select Language is Filipino Language!")
    StarterGui:SetCore("ChatMakeSystemMessage", properties)
elseif YourLang == "fr" then
    properties.Text = ("║ ◈ Your Select Language is French Language!")
    StarterGui:SetCore("ChatMakeSystemMessage", properties)
elseif YourLang == "tr" then
    properties.Text = ("║ ◈ Your Select Language is Turkish Language!")
    StarterGui:SetCore("ChatMakeSystemMessage", properties)
elseif YourLang == "ru" then
    properties.Text = ("║ ◈ Your Select Language is Russian Language!")
    StarterGui:SetCore("ChatMakeSystemMessage", properties)
elseif YourLang == "lo" then
    properties.Text = ("║ ◈ Your Select Language is Lao Language!")
    StarterGui:SetCore("ChatMakeSystemMessage", properties)
elseif YourLang == "uk" then
    properties.Text = ("║ ◈ Your Select Language is Ukrainian Language!")
    StarterGui:SetCore("ChatMakeSystemMessage", properties)
elseif YourLang == "" then
    properties.Text = ("║ ◈ Your Select Language is [ No Selected ] Language!")
    StarterGui:SetCore("ChatMakeSystemMessage", properties)
end
properties.Text = "╚═══════════════════════════════════════════════.★.╝"
StarterGui:SetCore("ChatMakeSystemMessage", properties)

local properties = {
    Color = Color3.new(0,255,0);
    Font = Enum.Font.SourceSansItalic;
    TextSize = 17.5; 
}
properties.Text = "╔═══════════════════ ⚙ [ Set-Lang] ⚙  ════════════════════╗ "
StarterGui:SetCore("ChatMakeSystemMessage", properties)
properties.Text = ("║ ◈ >ข้อความที่จะพิมพ์ | >ข้อความที่ส่งออก!")
StarterGui:SetCore("ChatMakeSystemMessage", properties)
properties.Text = ("║ ◈ >en | >th = English to Thai language!")
StarterGui:SetCore("ChatMakeSystemMessage", properties)
properties.Text = ("║ ◈ >th | >en = Thai To English language!")
StarterGui:SetCore("ChatMakeSystemMessage", properties)
properties.Text = "╚═══════════════════════════════════════════════.★.╝"
StarterGui:SetCore("ChatMakeSystemMessage", properties)
local properties = {
    Color = Color3.new(255,255,255);
    Font = Enum.Font.SourceSansItalic;
    TextSize = 17;
}

function translateFrom(message)
    local translation = translate(message, YourLang)

    local text
    if translation.from.language ~= YourLang then 
        text = translation.text
    end

    return {text, translation.from.language}
end

function get(plr, msg)
    local tab = translateFrom(msg)
    local translation = tab[1]
    if translation then
        properties.Text = "("..tab[2]:upper()..") ".."[".. plr.Name .."]: "..translation
        StarterGui:SetCore("ChatMakeSystemMessage", properties)
    end
end

for i, plr in ipairs(Players:GetPlayers()) do
    plr.Chatted:Connect(function(msg)
        get(plr, msg)
    end)
end
Players.PlayerAdded:Connect(function(plr)
    plr.Chatted:Connect(function(msg)
        get(plr, msg)
    end)
end)

local sendEnabled = false
local target = ""

function translateTo(message, target)
    target = target:lower() 
    local translation = translate(message, target, "auto")

    return translation.text
end

function disableSend()
    sendEnabled = false
    properties.Text = "[xDev] Sending Disabled"
    StarterGui:SetCore("ChatMakeSystemMessage", properties)
end

local CBar, CRemote, Connected = LP['PlayerGui']:WaitForChild('Chat')['Frame'].ChatBarParentFrame['Frame'].BoxFrame['Frame'].ChatBar, game:GetService('ReplicatedStorage').DefaultChatSystemChatEvents['SayMessageRequest'], {}

local HookChat = function(Bar)
    coroutine.wrap(function()
        if not table.find(Connected,Bar) then
            local Connect = Bar['FocusLost']:Connect(function(Enter)
                if Enter ~= false and Bar['Text'] ~= '' then
                    local Message = Bar['Text']
                    Bar['Text'] = '';
                    if Message == ">stop" then
                        disableSend()
                    elseif Message == ">ani" then
                                                local Fire = Instance.new("Fire")
Fire.Parent = game.Players.LocalPlayer.Character.Head
Fire.Heat = 15
Fire.Size = 2
wait()
local Fire = Instance.new("Fire")
Fire.Parent = game.Players.LocalPlayer.Character.RightHand
Fire.Heat = 5
Fire.Size = 2
wait()
local Fire = Instance.new("Fire")
Fire.Parent = game.Players.LocalPlayer.Character.LeftHand
Fire.Heat = 5
Fire.Size = 2

local animation = game.Players.LocalPlayer.Character.Animate
    animation.idle.Animation1.AnimationId = "http://www.roblox.com/asset/?id=782841498"
    animation.idle.Animation2.AnimationId = "http://www.roblox.com/asset/?id=782845736"	
    animation.run.RunAnim.AnimationId = "http://www.roblox.com/asset/?id=616163682"
    animation.jump.JumpAnim.AnimationId = "http://www.roblox.com/asset/?id=1083218792"
    animation.fall.FallAnim.AnimationId = "http://www.roblox.com/asset/?id=1083189019"
    animation.climb.ClimbAnim.AnimationId = "http://www.roblox.com/asset/?id=616003713"
    animation.walk.WalkAnim.AnimationId = "http://www.roblox.com/asset/?id=616013216"

                    elseif Message:sub(1,1) == ">" and not Message:find(" ") then
                        if getISOCode(Message:sub(2)) then
                            sendEnabled = true
                            target = Message:sub(2)
                        else
                            properties.Text = "[xDev] Invalid language"
                            StarterGui:SetCore("ChatMakeSystemMessage", properties)
                        end
                    elseif sendEnabled then
                        Message = translateTo(Message, target)
                        if not _G.SecureChat then
                            game:GetService('Players'):Chat(Message); 
                        end
                        CRemote:FireServer(Message,'All')
                    else
                        if not _G.SecureChat then
                            game:GetService('Players'):Chat(Message); 
                        end
                        CRemote:FireServer(Message,'All')

                    end
                end
            end)
            Connected[#Connected+1] = Bar; Bar['AncestryChanged']:Wait(); Connect:Disconnect()
        end
    end)()
end


HookChat(CBar); local BindHook = Instance.new('BindableEvent')

local MT = getrawmetatable(game); local NC = MT.__namecall; setreadonly(MT, false)

MT.__namecall = newcclosure(function(...)
    local Method, Args = getnamecallmethod(), {...}
    if rawequal(tostring(Args[1]),'ChatBarFocusChanged') and rawequal(Args[2],true) then 
        if LP['PlayerGui']:FindFirstChild('Chat') then
            BindHook:Fire()
        end
    end
    return NC(...)
end)

BindHook['Event']:Connect(function()
    CBar = LP['PlayerGui'].Chat['Frame'].ChatBarParentFrame['Frame'].BoxFrame['Frame'].ChatBar
    HookChat(CBar)
end)
