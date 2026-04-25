local way = 'https://github.com/Backlostunking/Open-Source/raw/refs/heads/main/Flee-the-Facility.luau'
local request, loadstring, setidentity, getidentity, ugc = http_request or request or (syn and syn.request) or (http and http.request) or (fluxus and fluxus.request), (loadstring or load), (setidentity or setthreadidentity) or (setthreadcontext or set_thread_context), (getidentity or getthreadidentity) or (getthreadcontext or get_thread_context), game or Game
local ide = getidentity and getidentity()
if type(ide)=='number' and ide<6 then pcall(setidentity,8) end
local v, u = pcall(function()
    return ugc:HttpGet(way)
end)
local x, r = pcall(loadstring, u)
if not (v and u) then
    v, u = pcall(function()
        return ugc:HttpGetAsync(way)
    end)
    x, r = pcall(loadstring, u);pcall(r)
else
    pcall(r)
end
if not (v and u) or not (x and r) and request then loadstring(request{Url=way,Method='GET'}.Body)() end
