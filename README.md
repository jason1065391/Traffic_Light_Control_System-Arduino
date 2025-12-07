# Traffic_Light_Control_System-Arduino

本專案示範 兩種交通號誌實作方式：

1. delay() 版本（入門）
2. millis() 狀態機版本（進階／工程師標準）

📌 功能概述
本交通號誌包含：
🟢 綠燈：4 秒
🟡 黃燈：2 秒
🔴 紅燈：4 秒
並提供 行人按鈕模式（輸入 "P" 觸發）

1：delay() 版本

✔ 優點
簡單
容易理解

❌ 缺點
程式會被 delay 卡住
無法即時反應行人按鈕
無法做多任務
不適合真實機台控制

📌 代表程式碼
'''Serial.println("GREEN LIGHT");
delay(4000);  // 程式在這段時間內完全無法做別的事

Serial.println("YELLOW LIGHT");
delay(2000);

Serial.println("RED LIGHT");
delay(4000);'''


🧠 解釋
delay(4000) 會讓 Arduino「凍結」4 秒，
在這期間：
按鈕按了沒反應
無法切換模式
無法處理事件

<img width="659" height="401" alt="image" src="https://github.com/user-attachments/assets/124f8255-e1ac-4dfe-8a9e-80b8cad4f240" />


2：millis() + 狀態機版本

✔ 優點
非阻塞（程式不會停住）
可同時偵測行人請求
可同時做多件事
與 PLC 控制思維一致
容易擴充「緊急模式、夜間模式、感測器」

📌 代表程式碼
'''if (nowTime - stateStartTime > 4000) {
    currentState = STATE_YELLOW;
}'''

程式每次 loop 都能：
檢查按鈕
處理模式切換
不被 delay 卡住

<img width="516" height="363" alt="image" src="https://github.com/user-attachments/assets/7e9104ef-e471-4812-8ca5-8202d864929a" />

