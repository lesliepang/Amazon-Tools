## 基本框架

```VB
Sub write()

Set uADO = CreateObject("adodb.connection")
Set reADO = CreateObject("adodb.recordset")
strPath = ThisWorkbook.Path & "\ABA.accdb"
uADO.Open "Provider=Microsoft.ace.oledb.12.0;Data Source=" & strPath

'写入的预置
reADO.activeConnection = uADO
reADO.LockType = 3
reADO.Open "test"

'增加记录
For Each i In holy
    reADO.AddNew
    reADO!heihei = i
    reADO.Update
Next i

'事后处理
reADO.Close
uADO.Close

Set holy = Nothing
Set uADO = Nothing
Set reADO = Nothing

End Sub
```
