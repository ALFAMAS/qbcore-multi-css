# [QBCore] [Multicharacter](https://github.com/qbcore-framework/qb-multicharacter) & Spawn Reworked CSS
# For Latest QBCore Public Server

# Note Add this on qb-core/server/functions.lua

QBCore.Functions.ExecuteSql = function(wait, query, cb)
    local rtndata = {}
    local waiting = true
    exports.oxmysql:execute(query, {}, function(data)
        if cb ~= nil and wait == false then
            cb(data)
        end
        rtndata = data
        waiting = false
    end)
    if wait then
        while waiting do
            Citizen.Wait(5)
        end
        if cb ~= nil and wait == true then
            cb(rtndata)
        end
    end
    return rtndata
end

### Preview : https://youtu.be/GG_9eDq1u1E

### My Discord Server - [DISCORD](https://discord.gg/jSDMuNjpuw)

### SETUP 
- Add these 2 lines your to `Server.cfg`.
- Ensure qb-multicharacter 
- Ensure qb-spawn
- Done!
