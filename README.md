# 家族聚餐點餐

給家人提前點餐的單頁網站。打開網址、選名字、點餐；「大家的訂單」分頁即時看到所有人點了什麼、合計金額、還有誰沒點。

- `index.html`：整個網站（菜單、人員名單都寫在裡面的 `MENU`、`PEOPLE`）
- `config.js`：共用資料庫網址。留空時是示範模式，資料只存在自己的裝置

## 接上共用資料庫（Firebase Realtime Database）

1. 到 <https://console.firebase.google.com> 用 Google 帳號建立專案（不需要 Analytics）
2. 左側「建構 → Realtime Database → 建立資料庫」，位置選 Singapore，規則選「以測試模式啟動」
3. 複製資料庫網址（`https://xxxx-default-rtdb.asia-southeast1.firebasedatabase.app`），貼到 `config.js`
4. 測試模式的規則 30 天後會自動關閉；聚餐在那之後的話，到「規則」分頁把到期日往後改

資料庫是公開讀寫的：知道網址的人都能看到、修改訂單。內容只有名字和餐點，聚餐結束後可以刪掉 Firebase 專案。

## 本機預覽

```bash
python3 -m http.server 8765
```
