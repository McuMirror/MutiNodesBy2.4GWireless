PA.1--TIM2 Channel2  as Output IIS-WS
PA.11--FLASH1 CS OUT PUT
PA.12--FLASH2 CS OUT PUT
PB.12--FLASH3 CS OUT PUT
PB.1 --RF IRQ IN PUT
PB.0 --RF CE OUT PUT
PA.4--RF CS OUT PUT

Configure SPI1 pins-TO RF(FLASH): SCK, MISO and MOSI
PA.5--SPI1 SCK
PA.6--SPI1 MISO
PA.7--SPI1 MOSI

Configure SPI1 pins-GPIO TO FLASH  	 GPIO_SPI
PA.8 as Output used as SPIflash-CLK
PA.9 as Output push-pull, used as SPIflash-MOSI
PA.10 as Input used as SPIflash-MISO

Configure SPI1 pins-USART1 TO FLASH  USART_SPI
PA.9--MOSI(Tx)
PA.8--SCK(CK)
PA.10--MISO(Rx) 

Configure SPI2 pins--TO dac: SCK,  MOSI
PB.13--SPI2  SCK
PB.15--SPI2  MOSI

PB.5 OUTPUT LED
PA.2 VBB-AD



���Ź�ģ�飨�Լ������������ؼ�������ʵ�֣�
ADCģ�飨AD���Ź�ʵ�ֶԵ�ѹ�ļ�⣩
��ʱ��ģ��
��Ƶģ�飨SPI�ڶ�2401���ʵ�֣�
flashģ�� ��USART�ڷ�SPI�ڶ�дFLAHSʵ�֣�

�����ģ��


1��GPIO������  GPIO_Configuration
2��IWDG���� IWDG_Configuration
3��EXTI����EXTI_Configuration
4��USART������USART1_configuration
5��DMA��ʽ���� DMA_spiConfiguration��DMA_usartConfiguration
6��ADC���� ADC_AWDconfiguration
7��TIM���� TIM2_Configuration
8��RCC���� RCC_Configuration
9��NVIC���� NVIC_Configuration
10��IRQ���� stm32f10x_it.c

main.c         ������              Ƭ�������������ģ���ʼ��
spi_flash.c    FLASH��д�Ӻ���     DMA��ͨ�÷�ʽ��дFLASH���ݡ�ID
radio.c        RFģ���д�Ӻ���    RFоƬ�Ĵ�����д��RFģ���ʼ����
spi.c          SPI�ײ㺯��         SPI�����á�ΪFLASH��RF�ṩ�ײ�����
stm32f10x_it.c ϵͳ�жϺ���        ��ʱ���жϡ�RF�����жϡ�DMA(FLASH��RF)����жϺ�ADC�ж�
STM32F10x.s    ϵͳ��� оƬ��ʼ�� �ж��������ʼ�� C����main��������ת   