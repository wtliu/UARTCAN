## APP�̼���дָ��

UARTCAN�̼���xboot + app��ɣ�xboot����ˢ�룬�̼���������app�̼�����������
[��������](https://github.com/xjtuecho/UARTCAN/tree/master/HEX)

### ROM����

MCU FLASH�洢�ռ乲64kB����ʼ��ַ0x08000000������0x10000

xbootռ�ÿ�ʼ��16kB����ʼ��ַ0x08000000������0x4000

appռ��ʣ�µ�48kB����ʼ��ַ0x08004000,����0xC000

### MDK�������ã�
1. Alt+F7����Ŀ���ԣ�Target��ǩ�£�IROM1��Start��0x8004000,Size��0xC000
2. �޸��ж���������ַ��system_stm32f10x.c�У���VECT_TAB_OFFSET�����ݸ�Ϊ0x4000
   #define VECT_TAB_OFFSET  0x4000
   Ҳ������app��main�����е�������API�趨app�ж���������ַ
   NVIC_SetVectorTable(NVIC_VectTab_FLASH, 0x4000)

### ע������
1. ����ʹ��ST-LINKˢ���Լ��Ĵ��룬���������ƻ�xboot��xboot�ƻ��Ժ�appҲ�޷���д�룬
   ��Ҫ�Էѷ���д��xboot�����ܼ���ʹ�ùٷ��̼���
2. appд�뷽����ο�UARTCAN�û��ֲ�

## UARTCAN��ҪӲ��
- MCU��STM32F103C8T6
- CAN��TJA1050T
- LDO��XC6206

## MCU GPIO����
- PA9�� UART_TX
- PA10��UART_RX
- PA11��CANRX
- PA12��CANTX
- PB12��LED
- PC13��KEY

                                                   by ECHO Studio 2016.11.27
