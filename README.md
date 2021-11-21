//masukkan fungsi include nya
#include "iostream"
#include "ncurses.h"
#include "string.h"

using namespace std;

#define KEY_ESC 27
#define kolom_tengah 40
#define baris_bawah 22

int main(){
	
	int tombol;
   short int baris, kolom;
   
    baris = baris_bawah;
	kolom = kolom_tengah;
	
	initscr();
	  
	keypad(stdscr,TRUE);
	
	curs_set(0);
	
	nodelay(stdscr, TRUE);
	
	mvprintw(baris,kolom," kucing ");  
	
	  while (tombol != KEY_ESC) {
          if ((tombol = getch()) == ERR) {
              (tombol !== KEY_ESC){
              	printw("Error\n");
			  }
          }
          
           else {
               	printw("kucing\n");
               	
         	 if(tombol == KEY_ENTER)
                { 
                 (tombol == KEY_ENTER){
				printw("kucing\n");
				}
                  } 
        
		else if(tombol == KEY_LEFT)
                { kolom = kolom - 1;
                
                  if (kolom==1) kolom=1;
                }  
         else if(tombol == KEY_RIGHT)
                { 
                  kolom = kolom + 1;

                  if (kolom==75) kolom=75;
                }  
             else if(tombol == KEY_UP)
                { 
                  mvprintw(baris,kolom,"     ");

                  baris = baris - 1;

                  if (baris==5) baris=5;
                } 
            else if(tombol == KEY_DOWN)
                { 
                  
                  mvprintw(baris,kolom,"     ");

                  baris = baris + 1;

            if (baris==baris_bawah) baris=baris_bawah;
                }      
                
                 // cetak sesuatu sesuai dengan baris dan kolom
                // di kanan dan kiri diberi spasi
                // untuk menghapus
                
    mvprintw(baris,kolom," kucing ");
                
	  }  
     }
   endwin();  
   return 0;
	
	
	
	
	
}
