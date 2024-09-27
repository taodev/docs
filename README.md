# docs
## 软件破解
### SublimeText 4.0
- Build: 4180
- Step:
  - x64dbg打开sublime_text.exe搜索**update_check**
```
49:8B?? ?? ?? 0000   mov rax,qword ptr ds:[r14+2B8]   | r14+2B8:"ted in DLL at base 0x%p.\n"
8078 ?? 00           cmp byte ptr ds:[rax+5],0        | 这里改为mov byte ptr ds:[rax+0x5], 0x1
74 ??                je sublime_text.7FF76A8B7FE2     |
49:???? ????0000     mov rcx,qword ptr ds:[r14+128]   | r14+128:"previously, ModuleState: %d\n"
48:8D?? ??????00     lea rax,qword ptr ds:[xxxxxxxxxx]| xxxxxx:"update_check"
```
  - 修改汇编后打补丁保存
- 禁止联网更新
  - 设置->无干扰设置->打开
```
{
	"enable_telemetry": false,
	"update_check": false,
}
```
