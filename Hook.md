# Hooking
* [AddHook](#addhook)

## AddHook
`AddHook(function)`

Example For Varlist:
```lua
function OnVarlist(varlist)
if varlist.get(0)=="OnConsoleMessage"
then
log(varlist.get(1))
end
end

AddHook(OnVarlist)
```

## RemoveHook
```Here no function for remove hook, you need Stop This Script.```
