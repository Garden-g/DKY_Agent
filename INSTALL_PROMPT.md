请让 Accio Work 根据当前系统执行对应命令，并按返回内容一次安装全部 49 个“大客赢”业务智能体。全程使用中文反馈。

Windows：

```powershell
curl.exe --http1.1 --retry 5 --retry-all-errors --retry-delay 1 --retry-max-time 120 --connect-timeout 15 -fsSL https://raw.githubusercontent.com/Garden-g/DKY_Agent/dc82696b8fb555c44d5e6251733cf2dabd7a445d/install/dakying-49-agents.txt
```

macOS：

```bash
curl --http1.1 --retry 5 --retry-all-errors --retry-delay 1 --retry-max-time 120 --connect-timeout 15 -fsSL https://raw.githubusercontent.com/Garden-g/DKY_Agent/dc82696b8fb555c44d5e6251733cf2dabd7a445d/install/dakying-49-agents.txt
```
