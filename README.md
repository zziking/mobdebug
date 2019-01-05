# mobdebug
a debug plugin for Lua, fork from [AliWax](https://github.com/alibaba/wax.git), and upgrade to support Lua 5.2x ~ 5.3x

# How to use

1. download [ZeroBrane Studio](https://studio.zerobrane.com/)
2. open lua scripts directory with ZeroBrane
   
    ![open lua](README/zerobrane.png)
3. start debugger server
    
    ZeroBrand - >Project -> Start Debugger Server
    !(start_debugger_server)[README/start_debugger_server.png]

    ZeroBrane will start debugger server on port 8172
4. add mobdebug to your Project

    ```
    self.luaState = luaL_newstate();

    // .....

    extern void luaopen_mobdebug_scripts(void* L);
    luaopen_mobdebug_scripts(self.luaState);

    luaL_dostring(self.luaState, "require('mobdebug').start('Your Debugger Server IP Address')")
    ```