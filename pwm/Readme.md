PWM GENRATION:



1.IOC



&#x20;--select timer --



* clock source--internal/external  clock source --depending on the board
* channel --pwm generation ch1



2.parameter settings--

* &#x20;prescaler =clock -1
* counter mode=up
* counter period(frequency of device converted to time f=1/t)=999
* auto reload=enable
* mode=pwm1 
* pulse=starting point of that device for eg(motor =1000us)







3.MAIN.C

* &#x20;HAL\_TIM\_PWM\_Start(\&htim2,TIM\_CHANNEL\_1);--START THE PWM GENRATION
* &#x20;\_\_HAL\_TIM\_SET\_COMPARE(\&htim2,TIM\_CHANNEL\_1,VALUE);--GENRATES THE PWM ACCORDING TO OUT REQUIREMENT



4.CHECK 



stm32f4xx\_hal\_msp.c 



IN THE ABOVE FILE WHETHER THE PIN IS INITALISED OR NOT .

