# hw03
 (1) gesture UI (f1, function 1)
亮led1代表進入gesture UI
用RPC serial call gestureUI()，gestureUI() call gesture()利用lab8的model來判斷gesture並控制selected angle顯示在uLCD上。
gesture與angle對應:
ring->30
slope->50
counterwise ring->70

按下user botton後，跳出function。

(2) tilt angle detection(f2, function 2)
亮led2代表進入tilt angle detection
用RPC serial call angleDetection ()，angleDetection () call detection ()從mbed讀取三軸加速度儀的值，一開始先初始化值，透過亮起led3提醒使用者平放，五秒後讀取初始值，關閉led3(led4同時會亮起)透過
abcos(theta)= a dot b
計算傾角theta，並每300ms更新一次，若超過selected angle則publish message，同時在uLCD上顯示theta。達到十次時停止。
