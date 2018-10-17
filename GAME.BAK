#include<iostream.h>                    //iosstream header file included
#include<fstream.h>                     //fstream header file included
#include<stdlib.h>                      //standard library header file included
#include<conio.h>                       //console i/o header file included
#include<string.h>                      //string header file included
#include<graphics.h>                    //header file for graphics
#include<dos.h>                         //header file for sound and delay type functions

void welcome();                         //function for first screen
void win();                             //function for win result screen
void lose();                            //function for lose result screen
int pass();                             //function for login
int  single_player();                   //function for single player mode
int disp_opt();                         //function for displaying theme of game
int single_input(char *,int);           //function for catching word in single mode
int double_player();                    //function for double player mode game
int double_disp_opt();                  //function for choosing theme of game
int input(char *,int);                  //function for taking word from chooser
int no_limit();                         //function for random word selection
void keyboard();                        //function for displaying virtual keyboard
int output(char*);                      //function for guesser's turn
void end();                             //function for ending interface
void press_button(char c);              //function for button disappereance

int main()                              //start of main function
{

	clrscr();
	int i,r;
	char q;
	int gm,gd=DETECT,d,f;           //initialization of graphics
	initgraph(&gd, &gm, "c:/tc/bgi");

	welcome();                      //first screen function call
	pass();                         //login function call
	a:
	do
	{
		cleardevice();          //game mode selection

		setbkcolor(LIGHTMAGENTA);
		setfillstyle(SOLID_FILL,WHITE);
		bar3d(100, 80, 550, 300, 0, 0);
		setcolor(BLUE);
		outtextxy(200,100,"1. Single Player Game");
		outtextxy(200,140,"2. Double Player Game");
		outtextxy(200,185,"Enter mode of game : ");

		setfillstyle(SOLID_FILL,WHITE);
		bar3d(430,180,470,220,0,0);
		textbackground(4);
		gotoxy(57,13);
		textbackground(4);
		cin>>i;

		if(i==1)
		{
			single_player();         //single player mode
		}
		if(i==2)
		{
			double_player();         //double player mode
		}
		else
		{
			setcolor(RED);
			outtextxy(250,220,"Incorrect Input");
		}
		cleardevice();
		clrscr();
		setbkcolor(BLUE);
		textbackground(BLUE);
		outtextxy(250,200,"1 Try Again");
		outtextxy(250,230,"2 Exit");
		outtextxy(250,265,"Enter you choice = ");
		gotoxy(58,18);
		q=getch();
		cin>>r;
	}
	while(r==1);
	end();
	return 0;
}

int pass()                                          //function for login
{
	char t[]="aksu",a[10];
	int i,j=0,k,l;

	cleardevice();
	setbkcolor(RED);

	for(i=0;i<10;i++)
	{
		a[i]=NULL;
	}
	outtextxy(100,190,"ENTER PASSWORD - ");
	do
	{
		a[j]=getch();
		gotoxy(45+j,13);
		cout<<"*";                 //showing * in place of alphabets
		k=(int)a[j];
		l=strcmp(t,a);
		if(l==0)
		{
			return 0;
		}
		j++;
	}
	while(k!=13);
	sound(1000);                       //buzzer sound
	delay(200);
	nosound();
	outtextxy(150,240,"WRONG PAWWORD");
	getch();
	pass();
}
void welcome()
{                                          //first sceen function
	int a,b,i=0;

	cleardevice();

	do
	{
	i++;

	setcolor(i);

	settextstyle(0,HORIZ_DIR,5);
	outtextxy(80,50,"HANGMAN GAME");

	setcolor(i);
	line(250,350,330,350);
	line(280,350,280,130);
	line(280,130,380,130);
	line(380,130,380,170);
	circle(380,190,20);
	line(380,210,380,270);
	line(380,220,350,250);
	line(380,220,410,250);
	line(380,270,350,300);
	line(380,270,410,300);


	setcolor(i+1);
	settextstyle(7,HORIZ_DIR,1);
	outtextxy(50,400,"CREATED BY -");
	outtextxy(400,400,"SUBMITED TO - ");
	setcolor(i+3);
	outtextxy(400,420,"HOD CS DEPARTMENT");
	outtextxy(400,440,"AKHILESH A. WAOO");
	outtextxy(50,420,"TUSHARADRI SINGH");
	outtextxy(50,440,"PRIYA PANDEY");
	delay(40);                         // blinking
	cleardevice();                     //       alphabets
	}
	while(!kbhit());                   //  using delay clearscreen and while
	getch();
}

int single_player()                        //single player mode
{

	clrscr();

	disp_opt();                        //theme selection
	return 0;
}

int disp_opt()                             //theme selection function
{
	int i,x,z;
	char path[20];
	b:
	cleardevice();
	setbkcolor(LIGHTRED);
	setfillstyle(SOLID_FILL,LIGHTGRAY);
	bar3d(100, 50, 500, 300, 0, 0);              //displaying sqaure for options
	setcolor(BLUE);
	outtextxy(200,80,"1 Animals Name");
	outtextxy(200,120,"2 Country Name");
	outtextxy(200,160,"3 Fruits & Vegetables");
	outtextxy(200,200,"4 Random Word");
	outtextxy(200,247,"Enter theme of game : ");

	setfillstyle(SOLID_FILL,WHITE);
	bar3d(430,245,470,285,0,0);                  //displaying bar for input
	gotoxy(57,17);
	cin>>i;

	switch(i)
	{
		case 1:
			{
				strcpy(path,"ANIMALS.TXT"); //copying path of file
				x=556;
				break;
			}
		case 2:
			{
				strcpy(path,"COUNTRY.TXT"); //copying path of file
				x=186;
				break;
			}
		case 3:
			{
				strcpy(path,"FRUITS.TXT");  //copying path of file
				x=156;
				break;
			}
		case 4:
			{
			randomize();
			z=random(2);
			if(z==0)
			{
			strcpy(path,"ANIMALS.TXT");          //copying path of file
			x=556;
			}
			if(z==1)
			{
				strcpy(path,"COUNTRY.TXT");  //copying path of file
				x=186;
			}
			if(z==2)
			{
				strcpy(path,"FRUITS.TXT");   //copying path of file
				x=156;
			}
			break;
			}
		default:
			{
				break;
			}
	}
	if(i==1||i==2||i==3||i==4)
	{

		randomize();
		x=random(x);
		single_input(path,x);
	}
	else
	{
		sound(1000);
		delay(200);
		nosound();
		outtextxy(250,300,"Incorrect Input");
		getch();
		goto b;
	}
	return 0;

}

int single_input(char *u,int x)
{
	int i,l,m,h;
	const int SIZE=80;
	char line[SIZE],wrd[80],*p,path[11];

	ifstream fin;                  //creatinh object of opening file
	fin.open(u);                   //opening file of given theme

	for(i=0;i<x;i++)
	{
		if(fin.eof()!=0)           //checking end of file
		{
			cout<<"Exit from word after i = "<<i<<endl;
			cout<<"Exiting, No word is found"<<endl;

		}
		fin.getline(line,SIZE);           //getting word from line

	}
	h=strlen(line);
	strcpy(wrd,line);                          //length of word
						   //coying word to given variable
	fin.close();
	output(wrd);                               //closing file
						   //chooser's turn
	return 0;
}


int double_player()                                //playing in double player mode
{
	int l;
	double_disp_opt();            //theme selection in double player mode
	return 0;
}
int double_disp_opt()                //function for selecting theme
{
	int i,x;
	char path[20],l;

	c:
	cleardevice();

	setbkcolor(LIGHTRED);
	setfillstyle(SOLID_FILL,LIGHTGRAY);
	bar3d(100, 50, 500, 300, 0, 0);       //square for displaying options
	setcolor(BLUE);

	outtextxy(200,80,"1 Animals Name");
	outtextxy(200,120,"2 Country Name");
	outtextxy(200,160,"3 Fruits & Vegetables");
	outtextxy(200,200,"4 Random Word");
	outtextxy(200,247,"Enter theme of game : ");

	setfillstyle(SOLID_FILL,WHITE);
	bar3d(430,245,470,285,0,0);
	gotoxy(57,17);
	cin>>i;

	switch(i)
	{
		case 1:
			{
				strcpy(path,"ANIMALS.TXT"); //copying file address
				x=556;
				break;
			}
		case 2:
			{
				strcpy(path,"COUNTRY.TXT"); //copying file address
				x=222;
				break;
			}
		 case 3:
			{
				strcpy(path,"FRUITS.TXT");  //copying file address
				x=156;
				break;
			}
		case 4:
			{
				no_limit();          //randomly input value
				break;

			}
		default:
			{
				break;
			}
	}

	if(i==1||i==2||i==3)
	{
		l=input(path,x);
	}
	else
	{
		sound(1000);
		delay(200);
		nosound();
		outtextxy(250,300,"Incorrect Input");
		getch();
		goto c;
	}

	return 0;

}

int input(char *s,int x)
{
	int i,l,m;
	const int SIZE=80;
	char line[SIZE],wrd[80],*p;

	cleardevice();

	setbkcolor(WHITE);
	textcolor(WHITE);
	outtextxy(180,155,"Enter a word = ");        //inserting word of slected theme
	setfillstyle(SOLID_FILL,RED);
	bar3d(340,150,480,180,0,0);
	gotoxy(47,11);
	cin>>wrd;
	strupr(wrd);                                 //converting to uppercase


	p=wrd;

	ifstream fin;
	fin.open(s);
	fin.seekg(0);

	for(i=0;i<x;i++)
	{
		if(fin.eof()!=0)
		{
		      //	cout<<"Exit from word after i = "<<i<<endl;
		      //	cout<<"Exiting, No word is found"<<endl;

		}

		fin.getline(line,SIZE);
		l=strcmp(wrd,line);
		m=strlen(wrd);

		if(l==0)
		{
			fin.close();
			output(p);

			//exit(1);

			//return 0;
		}
		else
		{
		   //  outtextxy(100,200,"No word matched");
		}

	}
return 0;
}

int no_limit()                          //chooser randomly selecting word
{
	cleardevice();
	setbkcolor(WHITE);

	char wrd[80],*p;

	setbkcolor(WHITE);
	textcolor(WHITE);
	outtextxy(180,155,"Enter a word = ");   //randomly selecting word
	setfillstyle(SOLID_FILL,RED);
	bar3d(340,150,480,180,0,0);
	gotoxy(47,11);
	cin>>wrd;
	strupr(wrd);                         //conerting into upper case
	p=wrd;                               //p will point towards word
	output(p);                           //chooser's turn
	return 2;
}

int output(char *w)                          //guesser's turn
{
	int i,j,k,l,m,x=8,z,b,a,q;
	char ch,s,*cpy;

	cleardevice();
	setbkcolor(CYAN);

	keyboard();                          //virtual keyboard function

	strupr(w);                           //converting word into upper case
	l=strlen(w);                         //checking lenght of word
	gotoxy(35,2);
	for(i=0;i<l;i++)
	{
		cout<<"-";                   //showing underscore in output screen
	}
	//gotoxy(35,26);
	//cout<<"W = "<<w<<endl;

	cpy=new char[l+1];
	for(i=0;i<(l+1);i++)
	{
		cpy[i]=NULL;
	}

	b=strlen(cpy);

	for(i=0;i<(l+8);i++)
	{
		gotoxy(24,1);
		m=0;

		outtextxy(220,57,"Enter a character : ");
		gotoxy(53,6);
		ch=getch();

		gotoxy(53,5);
		cout<<ch<<endl;

		press_button(ch);            //character removal from keyboard
		ch=int(ch)-32;

		for(j=0;j<l;j++)
		{
			k=ch-w[j];           //comparing alphabets

			if(k==0)             //if alphabets exist
			{
				gotoxy(35+j,2);
				cout<<ch;            //showing alphabet at right position
				cpy[j]=ch;           //storing alphabet at righ place
				z=strcmp(cpy,w);     //cheking word is matched or not
				b=strlen(cpy);
				gotoxy(10,1);
				//cout<<"B = "<<b<<endl;
				gotoxy(30,10);

				if(z==0)             //if word matches
				{
					gotoxy(35,14);
					cout<<"You Win";        //result in output screen
					getch();
					win();                  //win result function call

					for(q=0;q<l;q++)
					{
						cpy[q]=NULL;
					}
					return 0;
				}
				m++;
			 }
		}
		if(m==0)
		{
			sound(100);
			delay(300);
			nosound();
			x--;
			if(x==7)
			{                                       //displaying texture for first
				line(10,220,100,220);            //wrong move
				line(20,20,20,220);
			}
			if(x==6)
			{

				line(20,20,120,20);             //displaying texture for second
				line(120,20,120,60);            //wrong move
			}
			if(x==5)
			{

				circle(120, 80, 20);            //displaying texture for third wrong move
			}
			if(x==4)
			{
				line(120,100,120,160);         //displaying texture for fourth wrong move
			}
			if(x==3)
			{
				line(120,110,90,140);          //displaying texture for fifth wrong move
			}
			if(x==2)
			{
				line(120,110,150,140);         //displaying texture for sixth wrong move
			}
			if(x==1)
			{
				line(120,160,90,190);          //displaying texture for seventh wrong move
			}
			if(x==0)
			{
				line(120,160,150,190);         //displaying texture for eighth wrong move
				//getch();
				gotoxy(25,14);
				//cout<<"You Loose"<<endl;
				cout<<"Correct word = "<<w<<endl;   //displaying result
				cleardevice();
				getch();
				gotoxy(25,14);
				//cout<<"You Loose"<<endl;
				cout<<"Correct word = "<<w<<endl;
				outtextxy(450,40,"Predictions Left = ");    //displaying result
				gotoxy(79,4);
				cout<<x<<endl;
				getch();
				lose();                        //lose function call
				for(q=0;q<b;q++)
				{
					cpy[q]=NULL;
				}

				return 1;
			}
		}
		gotoxy(30,10);

		outtextxy(450,40,"Predictions Left = ");
		gotoxy(79,4);
		cout<<x<<endl;
		gotoxy(2+j,1);


	}
	//
	cout<<endl<<l<<endl<<cpy<<endl;

	return 2;
}
void keyboard()
{

	int i,x,l=65,m=73,n=81,ch;
	char c,*d,k,o,p,z,y;

	for(i=0;i<8;i++)
	{
		rectangle(13+(i*80),230,53+(i*80),260); //displaying blocks
		rectangle(13+(i*80),277,53+(i*80),307); // on each
		rectangle(13+(i*80),324,53+(i*80),354); //    row

		k=char(l);
		gotoxy(4+(i*10),16);
		cout<<k;
		l++;

		o=char(m);
		gotoxy(4+(i*10),19);
		cout<<o;
		m++;

		p=char(n);
		gotoxy(4+(i*10),22);
		cout<<p;
		n++;

		if(n==89)
		{
			break;
		}

	}
	gotoxy(4,25);
	cout<<"Y";
	rectangle(13,371,53,401);

	gotoxy(74,25);
	cout<<"Z"<<endl;
	rectangle(13+(7*80),371,53+(7*80),401);

	gotoxy(38,25);
	cout<<"SPACE";
	rectangle(13+(1*80),371,53+(6*80),401);
}
void press_button(char c)
{

	int l;
	l=int(c);
	gotoxy(1,1);
	if(l==105)
	{
		gotoxy(4,19);
		cout<<" ";
	}
	if(l>96&&l<106)
	{
		l=l-97;
		gotoxy(4+(l*10),16);
		cout<<" ";
	}
	if(l>103&&l<113)
	{
		l=l-105;
		gotoxy(4+(l*10),19);
		cout<<" ";
	}
	if(l>112&&l<121)
	{
		l=l-113;
		gotoxy(4+(l*10),22);
		cout<<" ";
	}
	if(l==32)
	{
		gotoxy(38,25);
		cout<<"     ";
	}
	if(l==121)
	{
		gotoxy(4,25);
		cout<<" ";
	}
	if(l==122)
	{
		gotoxy(74,25);
		cout<<" ";
	}
}

void end()
{
	cleardevice();
	setbkcolor(YELLOW);
	settextstyle(7,HORIZ_DIR,3);
	setcolor(8);
	outtextxy(150,100,"Hope you enjoyed the game");
	settextstyle(0,HORIZ_DIR,4);
	setcolor(RED);
	outtextxy(100,230,"THANK YOU...!!!");
	getch();
	exit(1);
}
void win()
{
	int i=0;
	cleardevice();
	//setcolor(RED);
	setbkcolor(WHITE);
	//settextstyle(7,HORIZ_DIR,3);
	do
	{
		i++;
		outtextxy(220,150,"Congratulations......!!!!");
		setcolor(i);
		outtextxy(250,200,"Guesser Wins");
		delay(40);
		cleardevice();
	}
	while(!kbhit());
	cleardevice();
	setbkcolor(BLUE);
}
void lose()
{
	int i=0;
	cleardevice();
	//setcolor(RED);
	setbkcolor(WHITE);
	//settextstyle(7,HORIZ_DIR,3);
	do
	{
		i++;
		outtextxy(220,150,"Congratulations......!!!!");
		setcolor(i);
		outtextxy(250,200,"Chooser Wins");
		delay(40);
		cleardevice();
	}
	while(!kbhit());
	cleardevice();
	setbkcolor(BLUE);
}