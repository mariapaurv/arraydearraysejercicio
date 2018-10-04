#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    
int n;
    cout << "ingrese el tamanio de la matriz:";
    cin >> n;

    int arrInt[n][100];

    srand(time(nullptr));

    for (int i=0; i<n; i++) {
        for (int j = 0; j < n; j++) {
            arrInt[i][j] = rand() % 100;
        }
    }
    
    for (int i=0; i<n; i++) {
        for (int j = 0; j < n; j++) {
            cout << setw(5) << arrInt[i][j] << " ";
        }
        cout << "\n";
    }
    
    int col1 = 0, col2 = 0;
    cout << "\ningrese la columna origen:";
    cin >> col1;
    cout << "\ningrese la columna destino:";
    cin >> col2;
    
    int colcopy[n]; 
    for (int i=0; i<n; i++)
        colcopy[i] = arrInt[i][col1];
    
    for (int i=0; i<n; i++){
        arrInt[i][col1] = arrInt[i][col2];
        arrInt[i][col2] = colcopy[i];
    }
  
    for (int i=0; i<n; i++) {
        for (int j = 0; j < n; j++) {
            cout << setw(5) << arrInt[i][j] << " ";
        }
        cout << "\n";
    }
}
