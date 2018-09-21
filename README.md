# QuickHook
small x86 detour library

# Example
```c++
int hooked_gettop(int lua_S)
{
	hook_gettop.removeHook(); // remove hook
	int i = lua_gettop_d(lua_S);
	hook_gettop.installHook();
	return i;
}

C_Hook hook_gettop;
hook_gettop.setSubs((void *)lua_gettop_d, (void *)Lua::hooked_gettop);
hook_gettop.installHook();
```
