# hw2
裡用hw1的兩個計數來模擬PWM訊號，一個上數一個下數，兩個計數值相加為255。
這次的作業要加一個FSM2(gettingBright,gettingDark)來控制LED變亮與變暗的轉換，reset後狀態會進入gettingBright讓LED逐漸變亮，如果已經最亮了就進入gettingDark讓LED逐漸變暗。

upbnd1與upbnd2為兩個計數的計數上限，是用來切換FSM2的狀態，相加為255，要知道是否已經最亮或最暗看其中一個upbnd就好。(第一個Bug)。

程式裡面有個變數p，是用來確認pwm是否過了p個週期，避免pwm開關的速度太快，導致波形看不出變化。
先用一個Detect_PWM_pos_edge來抓取PWM的正緣訊號號，然後確定P_PWM_cycles計數是否過了指定的P個週期，如果過了就讓alreadyP_PWM_cycles輸出為1。 （第二個Bug)。

上板子後，要增加p的上限，否則會因為太快導致肉眼看不見。
影片連結：https://youtube.com/shorts/fT1ff9UEovk

<img width="2520" height="481" alt="image" src="https://github.com/user-attachments/assets/e9a4579f-9500-4772-aa7f-2d532eae72d5" />
<img width="2520" height="481" alt="image" src="https://github.com/user-attachments/assets/8eb0586f-5486-4635-81b5-b26e1d64b765" />
<img width="2525" height="417" alt="image" src="https://github.com/user-attachments/assets/e9fc38a5-2214-48c6-8491-685691592771" />
<img width="2527" height="439" alt="image" src="https://github.com/user-attachments/assets/576ef8f1-2587-4bcc-b506-80d75a3b9848" />
<img width="2521" height="470" alt="image" src="https://github.com/user-attachments/assets/abb5c5f4-a1c0-44c0-9111-a478457bcf4b" />
<img width="2523" height="441" alt="image" src="https://github.com/user-attachments/assets/d8d6a9f2-894c-4212-9782-fa0729ecf4fe" />

