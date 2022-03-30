## readme

#### settings.json

使用clangd代替vscode原有C++ intellicense功能，需要先安装好clangd（在LLVM套件中），再在settings.json里面添加设置项：
```json
"C_Cpp.autocomplete": "Disabled",   // So you don't get autocomplete from both extensions.
"C_Cpp.errorSquiggles": "Disabled", // So you don't get error squiggles from both extensions (clangd's seem to be more reliable anyway).
"clangd.path": "/data/huangxiaofeng/opt/llvm/bin/clangd",
"clangd.arguments": ["-log=verbose", "-pretty", "--background-index", "--compile-commands-dir=${workspaceFolder}/output/cpu_simu_dev/"],
```

clangd完全配置：
```json
    "clangd.arguments": [
        "--background-index",
        "--compile-commands-dir=build",  //compile_command.json相对路径，cmake默认生成在build，自行配置
        "-j=12",
        "--all-scopes-completion",
        "--completion-style=detailed",
        "--header-insertion=iwyu",
        "--pch-storage=memory",
        "--cross-file-rename",
        "--enable-config",
        "--fallback-style=WebKit",
        "--pretty",
        "--clang-tidy"
        // 网上别人配置clang++，但我这边windows、linux实测不加这行也没啥问题，可能mac可能需要另外加
    	"--query-driver=clang++",
    ],
```
- [
vscode + clangd 开发 c\c++](https://blog.csdn.net/weixin_43862847/article/details/119274382)

#### clangd配置文件
- [clangd Configuration](https://clangd.llvm.org/config)

