# QuickHook
small x86 detour library for Windows applications

# Example
```c++
int hooked_gettop(int lua_S)
{
	hook_gettop.removeHook(); // remove hook
	int i = lua_gettop_d(lua_S); // call original sub
	hook_gettop.installHook(); // install detour
	return i;
}

C_Hook hook_gettop;
hook_gettop.setSubs((void *)lua_gettop_d, (void *)hooked_gettop);
hook_gettop.installHook();
```
