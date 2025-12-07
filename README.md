# Traffic-Light-Control-System-Arduino-
以 Arduino 模擬「交通號誌控制系統」， 透過 時序控制、狀態切換、事件（按鈕）觸發。

功能介紹:
一般交通燈循環模式
  交通燈會依序執行：
    綠燈 4 秒
    黃燈 2 秒
    紅燈 4 秒
  並持續循環。

進階：行人按鈕模式（Pedestrian Mode）
使用者可在 Arduino 序列埠輸入："p" 代表行人按下按鈕（模擬按鈕觸發）。

觸發流程：
中斷目前循環
縮短黃燈
進入紅燈（讓行人通行）
完成後回到一般循環

<img width="659" height="401" alt="image" src="https://github.com/user-attachments/assets/124f8255-e1ac-4dfe-8a9e-80b8cad4f240" />
