# program-uas
//GAME LEMPAR DADU

#include <iostream>
#include <stdlib.h>
#include <conio.h>
#include <time.h> 

// DADU PROGRAM GIBRAN GENTA R
using namespace std;

struct dataPemain{
    int jmlPemain;
    string pemain[5];
} P;

int randomDadu(){
    srand(time(0));
    return rand()%6;
}
void Header(){
    cout << "   DADU PROGRAM   " << endl;
    cout << "---------------------------------" << endl;
}
void inputPemain(){ 
    for(int a=0;a<P.jmlPemain;a++){
        cout << "Pemain " << a+1 << " = ";
        cin >> P.pemain[a];
    }
}
int main(){
    Header();
    do{
        cout << "Berapa Yang Ingin Main [MAX 5] ? ";
        cin >> P.jmlPemain;
    }while(P.jmlPemain > 5);

    cout << "Masukan nama pemain !" << endl;
    inputPemain();cout << endl << endl;

    while(true){
        for(int a=0;a<P.jmlPemain;a++){
            cout << "===============" << endl;
            cout << " Dadu : <["<< P.pemain[a] << "]>"<< endl;
            cout << "===============" << endl;
            cout << "=      " << randomDadu()+1 << "      = " << endl;
            cout << "===============" << endl;
            if(randomDadu()+1 == 6){
                cout << "<[" << P.pemain[a] << "]> Kamu main lagi ! "; getch();
                cout << endl<< endl;
                cout << "===============" << endl;
                cout << " Dadu : <["<< P.pemain[a] << "]>"<< endl;
                cout << "===============" << endl;
                cout << "=      " << randomDadu()+1 << "      = " << endl;
                cout << "===============" << endl;
                if(randomDadu()+1 == 6){
                    cout << "Anda sudah Kedua kalinya mendapat Dadu 6, maka giliran Lainya "; getch();
                    cout << endl << endl;
                }
            }
            cout << "[ENTER]"; 
            getch();
            cout << endl << endl;
        }
    }
}
