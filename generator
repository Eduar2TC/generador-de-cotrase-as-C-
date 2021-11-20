#include <iostream>
#include <time.h>
using namespace std;
class Password{
    private:
     int tamanio;
     string abecedario = "abcdefghijklmnopqrstuvwxyz";
     char *minisculas;
     char *mayusculas;
     const char *numeros;
     const char *caracteresEspeciales;

     public: Password(){
         this->iniMinisculas();
         this->iniMayusculas();
         this->iniNumeros();
         this->iniCaracteres();
     };

    int generaRandom(int limiteInferior, int limiteSuperior){
        return (rand() % limiteSuperior) + limiteInferior;
    }
     void setTamanio(int tamanio){
         this->tamanio = tamanio;
     }
     int getTamanio(){
         return this->tamanio;
     }
     void iniMinisculas(){
         this->minisculas = new char[ this->abecedario.length() ];
         strcpy(this->minisculas, this->abecedario.c_str());
     }
     void iniMayusculas(){
         this->mayusculas = new char[this->abecedario.length()];
         strcpy(this->mayusculas, this->abecedario.c_str());
         for( int i = 0; i < sizeof(this->abecedario); i++ ){
             this->mayusculas[i] = toupper( this->abecedario[i] );
         }
     }
     void iniNumeros(){
         this->numeros = "1234567890";
     }
     void iniCaracteres(){
         this->caracteresEspeciales = "~`!@#$%^&*()_-+={[}]|:;\"'<,>.?/";
     }

     char obtenerRandomDeString(string cadena ){ 
         int random = this->generaRandom(0, cadena.length());
         return cadena[random];
     }

     string generaPassword(char minusculas, char mayusculas, char numeros, char caracteresEspeciales, int tamanio){
         string cadena;
         string password;
         if (minusculas == 'Y' || minusculas == 'y'){
             cadena += this->minisculas;
         }
         if (mayusculas == 'Y' || mayusculas == 'y'){
             cadena += this->mayusculas;
         }
         if (numeros == 'Y' || numeros == 'y'){
             cadena += this->numeros;
         }
         if (caracteresEspeciales == 'Y' || caracteresEspeciales == 'y'){
             cadena += this->caracteresEspeciales;
         }
         srand((unsigned)time(0));
         for( int i = 0; i < tamanio; i++ ){
             password += obtenerRandomDeString(cadena);
         }
         return password;
     }
     void iniInteraccion(){
         int tamanio = 6;
         char respuestaMinusculas;
         char respuestaMayusculas;
         char respuestaNumeros;
         char respuestaCaracteresEspeciales;
         
         cout<<"Minisculas ? [Y / N ] : ";
         cin>>respuestaMinusculas;
         cout << "Mayusculas ? [Y / N ] : ";
         cin >> respuestaMayusculas;
         cout << "Numeros ? [Y / N ] : ";
         cin >> respuestaNumeros;
         cout << "Caracteres Especiales ? [Y / N ] : ";
         cin >> respuestaCaracteresEspeciales;
         cin.ignore();
         cin.clear();
         cout << "Tamanio : ";
         while ( !(cin >> tamanio) || tamanio < 1){
             cout<<"Tamanio : ";
             cin.clear();
         }
        string password = this->generaPassword( respuestaMinusculas, respuestaMayusculas, respuestaNumeros, respuestaCaracteresEspeciales, tamanio );
        cout << "password generada : " << password;
     }

};
int main(){
    Password objeto = Password();
    objeto.iniInteraccion();
    cin.get();
}
