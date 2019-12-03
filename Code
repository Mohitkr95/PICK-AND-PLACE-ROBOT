#include <avr/io.h>
#define F_CPU 8000000UL
#include <util/delay.h>
#include <avr/interrupt.h>
#define r1a (1<<0)
#define r1b (1<<1)
#define r2a (1<<2)
#define r2b (1<<3)
#define l1a (1<<4)
#define l1b (1<<5)
#define l2a (1<<6)
#define l2b (1<<7)
#define ud1 (1<<0)
#define ud2 (1<<1)
#define oc1 (1<<2)
#define oc2 (1<<3)
void serial_init(void);
void serial_tx(char);
char serial_rx(void);
void move_servo(char);
char d,flag=0;

ISR(USART_RXC_vect)
{
		PORTA=0X00;
		PORTC=0X00;
		PORTB=0X00;
		d=UDR;
		UDR=d;

		if(d=='R')
		{
			PORTB&=~(1<<0)|~(1<<1)|~(1<<2)|~(1<<3);
			PORTB|=1<<0;
			PORTA|=l1a|l2a;
			PORTA&=~l1b|~l2b;
			PORTA|=r1a|r1b|r2a|r2b;
		}
		if(d=='L')
		{
			PORTB&=~(1<<0)|~(1<<1)|~(1<<2)|~(1<<3);
			PORTB|=1<<2;
			PORTA|=r1a|r2a;
			PORTA&=~r1b|~r2b;
			PORTA|=l1a|l1b|l2a|l2b;
		}
		if(d=='F')
		{
			PORTB&=~(1<<0)|~(1<<1)|~(1<<2)|~(1<<3);
			PORTB|=1<<1;
			PORTA|=l1a|l2a|r1a|r2a;
			PORTA&=~l1b|~l2b|~r1b|~r2b;
		}
		if(d=='B')
		{
			PORTB&=~(1<<0)|~(1<<1)|~(1<<2)|~(1<<3);
			PORTB|=1<<3;
			PORTA&=~l1a|~l2a|~r1a|~r2a;
			PORTA=l1b|l2b|r1b|r2b;
		}
		if (d=='S')
		{
			PORTB&=~(1<<0)|~(1<<1)|~(1<<2)|~(1<<3);
			PORTA|=l1a|l2a|l1b|l2b|r1a|r1b|r2a|r2b;
			PORTC|=ud1|ud2|oc2|oc1;
		}
	//	if(d=='U')
		{
			PORTC|=ud1;
			PORTC&=~ud2;
		}
		if(d=='D')
		{
			PORTC|=ud2;
			PORTC&=~ud1;
		}
		if(d=='O')
		{
			move_servo(180);
		}
		if(d=='C')
		{
			move_servo(0);
		}
}*/   (if u want to make its pick and place robot i.e. for its arm controlling one servo motor is                 used for its claw and 1 DC motor of 60rpm is used for its movement.)
int main(void)
{
	DDRA=0xFF;
	DDRC=0X03;
	DDRD=0x20;
	DDRB=0X0F;
	TCCR1A=0x82;
	TCCR1B=0x1A;
	ICR1=20000;
	sei();
	serial_init();
	while(1)
	{	
	}	
}
void serial_init()
{
	UBRRH=0X00;
	UBRRL=0X33;
	UCSRB=0X98;
	UCSRC=0X86;
}
void serial_tx(char ch)
{
	UDR=ch;
	while((UCSRA&(1<<UDRE))==0);
}
char serial_rx(void)
{
	while((UCSRA&(1<<RXC))==0);
	return(UDR);
}
void move_servo(char angle)
{
	OCR1A=1000+(5.5*angle);
}

