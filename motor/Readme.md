PWM GENRATION MOTOR:



1.IOC



&#x20;--select timer --



* clock source--internal/external  clock source --depending on the board
* channel --pwm generation ch1



2.parameter settings--

* &#x20;prescaler =clock -1
* counter mode=up
* counter period(frequency of device converted to time f=1/t)=19999  (FOR Motor esc frequency is 50HZ which is equal 20000us = 0-19999)
* auto reload=enable
* mode=pwm1
* pulse=starting point of that device for eg(motor =1000us)







3.MAIN.C

* &#x20;HAL\_TIM\_PWM\_Start(\&htim2,TIM\_CHANNEL\_1);--START THE PWM GENRATION
* &#x20;\_\_HAL\_TIM\_SET\_COMPARE(\&htim2,TIM\_CHANNEL\_1,VALUE);--GENRATES THE PWM ACCORDING TO OUT REQUIREMENT



for(int i=1000;i<2000;i+=100)

&#x09;      {

&#x09;      	\_\_HAL\_TIM\_SET\_COMPARE(\&htim2,TIM\_CHANNEL\_1,i);

&#x09;      	HAL\_Delay(3000);

&#x09;      	if(i==1900)

&#x09;      	{

&#x09;      	\_\_HAL\_TIM\_SET\_COMPARE(\&htim2,TIM\_CHANNEL\_1,1000);

&#x09;      }}--motor speed variation by 100



4.CHECK



stm32f4xx\_hal\_msp.c



IN THE ABOVE FILE WHETHER THE PIN IS INITALISED OR NOT .

