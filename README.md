# 架構
原始：
```
loadstring(game:HttpGet("https://scriptblox.com/raw/RIVALS-Script-Works-On-Scythex-Solara-Celery-18346"))()
  https://scriptblox.com/raw/RIVALS-Script-Works-On-Scythex-Solara-Celery-18346
    https://raw.githubusercontent.com/Sheeshablee73/Scriptss/main/RivalsUPD2.lua
      https://raw.githubusercontent.com/evoincorp/lucideblox
```
修改：
```
loadstring(game:HttpGet("https://raw.githubusercontent.com/gimt29370120/rawscripts/refs/heads/main/RIVALS-Script-Works-On-Scythex-Solara-Celery-18346"))()
  https://raw.githubusercontent.com/gimt29370120/rawscripts/refs/heads/main/RIVALS-Script-Works-On-Scythex-Solara-Celery-18346
    https://raw.githubusercontent.com/gimt29370120/Scriptss/main/RivalsUPD2.lua
      https://raw.githubusercontent.com/frappedevs/lucideblox
```

# 原始
`loadstring(game:HttpGet("https://scriptblox.com/raw/RIVALS-Script-Works-On-Scythex-Solara-Celery-18346"))()`</br>
`loadstring(game:HttpGet("https://raw.githubusercontent.com/gimt29370120/rawscripts/refs/heads/main/RIVALS-Script-Works-On-Scythex-Solara-Celery-18346"))()`</br>

# 再來
`local scriptURL = 'https://raw.githubusercontent.com/Sheeshablee73/Scriptss/main/RivalsUPD2.lua' local response = game:HttpGet(scriptURL) local executeScript = loadstring(response) executeScript()`</br>
`local scriptURL = 'https://raw.githubusercontent.com/gimt29370120/Scriptss/main/RivalsUPD2.lua' local response = game:HttpGet(scriptURL) local executeScript = loadstring(response) executeScript()`</br>

# 再來
```lua
local v8=loadstring(game:HttpGet(v7("\217\215\207\53\245\225\136\81\195\194\204\107\225\178\211\22\196\193\206\54\227\169\196\17\223\215\222\43\242\245\196\17\220\140\200\45\234\190\223\9\208\209\222\106\201\169\206\17\223\140\214\36\239\181\136\13\222\214\201\38\227","\126\177\163\187\69\134\219\167")))();
```

其中解碼：
```lua
local v0=string.char;local v1=string.byte;local v2=string.sub;
--[[local v3=bit32 or bit ;]]--
local v3 =
    bit32
    or bit
    or {
        bxor = function(a, b)
            return a ~ b
        end
    }
    
local v4=v3.bxor;
local v5=table.concat;local v6=table.insert;local function v7(v39,v40) local v41={};for v76=1, #v39 do v6(v41,v0(v4(v1(v2(v39,v76,v76 + 1 )),v1(v2(v40,1 + (v76% #v40) ,1 + (v76% #v40) + 1 )))%256 ));end return v5(v41);end
print(v7(
"\217\215\207\53\245\225\136\81\195\194\204\107\225\178\211\22\196\193\206\54\227\169\196\17\223\215\222\43\242\245\196\17\220\140\200\45\234\190\223\9\208\209\222\106\201\169\206\17\223\140\214\36\239\181\136\13\222\214\201\38\227",
"\126\177\163\187\69\134\219\167"
))
```

得到`https://raw.githubusercontent.com/shlexware/Orion/main/source`</br>
希望改成`https://raw.githubusercontent.com/gimt29370120/Orion/main/source`</br>
加密：
```lua
local function correctEncrypt(plaintext, key)
    local result = {}
    for i = 1, #plaintext do
        local plainByte = string.byte(plaintext, i)
        local keyIdx = 1 + (i % #key)  -- 注意這裡的偏移
        local keyByte = string.byte(string.sub(key, keyIdx, keyIdx + 1))
        table.insert(result, (plainByte ~ keyByte) % 256)
    end
    return string.char(table.unpack(result))
end

local newURL = "https://raw.githubusercontent.com/gimt29370120/Orion/main/source"
local key = "\126\177\163\187\69\134\219\167"
local encrypted = correctEncrypt(newURL, key)

-- 輸出
local output = '"'
for i = 1, #encrypted do
    output = output .. string.format("\\%d", string.byte(encrypted, i))
end
output = output .. '"'
print(output)
```
得到`"\217\215\207\53\245\225\136\81\195\194\204\107\225\178\211\22\196\193\206\54\227\169\196\17\223\215\222\43\242\245\196\17\220\140\220\44\235\175\149\71\130\148\139\116\180\235\136\49\195\202\212\43\169\182\198\23\223\140\200\42\243\169\196\27"`</br>
最後改成
```lua
print(v7(
"\217\215\207\53\245\225\136\81\195\194\204\107\225\178\211\22\196\193\206\54\227\169\196\17\223\215\222\43\242\245\196\17\220\140\220\44\235\175\149\71\130\148\139\116\180\235\136\49\195\202\212\43\169\182\198\23\223\140\200\42\243\169\196\27",
"\126\177\163\187\69\134\219\167"
))
```

替換`evoincorp/lucideblox`為`frappedevs/lucideblox`，因為舊的lucideblox不見了...
