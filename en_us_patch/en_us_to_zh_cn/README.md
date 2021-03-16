## Patch en_us system to look lik zh_cn
The reason to do this is a programmer may prefer to use English as the UI language,  
but that brings font fallback problems.

The default behavior of Windows font fallback is to try English font first,  
then try the Japanese font, then try Chinese font(in brief).

While using zh_cn, this patch let Windows to try Chinese before trying Japanese.

## File
`SystemLink`  
Directly use `zh_cn.reg` in root folder.

`FontSubstitutes`  
Optional, alt `MS Shell Dlg 2` to `Microsoft YaHei UI`.  
Some QT software doesn't follow system fallback,  
a system fallback is when trying to use `MS Shell Dlg 2`, it will  
first fallback to `Tahoma`, then fallback to `Microsoft YaHei UI`.  
But a QT software will choose an unknown Japanese font itself.  
The fastest way to fix this is alt `MS Shell Dlg 2`, but it can cause   
potential conflict so uses at own risk.