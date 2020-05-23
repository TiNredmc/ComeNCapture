# ComeNCapture
This is very quick and dirty logic analyzer. Built with my sdcc template. 

# The Concept
The concept is. The microcontroller (STM8L151F3U6) communicate with PC using USART with baud rate at 115200. The Timer4 Counter Interrupt is used for nearly perfect timing for the data sampling, Gathering the data be reading the PB_IDR (Port B input register) and put it directly to the USART1_DR (USART Shift register for TX). The capturing process start by PC send 3 byte to the MCU. The first one is the Start or Stop indicator, Next is the ARR period and the last is Prescaler. The Arr and Prescaler is important to control the timing of TIM4 interrupt. In the code I use TIM4 counter interrupt for data sampling which I can control the period for every single byte of the data being read from PP_IDR and write to USART_DR . The USART RX interrupt is for pausing TIM4 counter and re-config the ARR and Pre-scaler for other sampling speed.

# Project status

Work in progress. From my perspective, This code is 0 % reliable. But hey, If you never try, Then you never know.  
