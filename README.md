## readme

#### settings.json

使用clangd代替vscode原有C++ intellicense功能，需要先安装好clangd（在LLVM套件中），再在settings.json里面添加设置项：
```json
"C_Cpp.autocomplete": "Disabled",   // So you don't get autocomplete from both extensions.
"C_Cpp.errorSquiggles": "Disabled", // So you don't get error squiggles from both extensions (clangd's seem to be more reliable anyway).
"clangd.path": "/data/huangxiaofeng/opt/llvm/bin/clangd",
"clangd.arguments": ["-log=verbose", "-pretty", "--background-index", "--compile-commands-dir=${workspaceFolder}/output/cpu_simu_dev/"],
```

#### clangd配置文件
- [clangd Configuration](https://clangd.llvm.org/config)

