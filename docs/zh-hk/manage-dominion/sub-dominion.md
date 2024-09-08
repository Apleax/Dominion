# 創建子領地

## 創建方法

創建方法與普通領地相同，可以使用自動創建，也可以手動創建。

命令分別為：

`/dominion create_sub <子領地名稱> [父領地名稱]`

`/dominion auto_create_sub <子領地名稱> [父領地名稱]`

當不填寫父領地名稱時會嘗試以當前所在領地為父領地進行創建。

## 權限

當玩家處在一個子領地內時，其行為只收到子領地的權限控製。
子領地的權限設置與傅領地完全相同，參考[權限管理](permission/README.md)。

## 關於子領地嵌套

子領地內部可以再創建子領地，但是子領地的嵌套深度是有限製的，具體嵌套深度由服務器管理員在[配置文件](../operator/config.md)中設置。