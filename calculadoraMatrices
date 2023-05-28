#include<iostream>
#include<String>
#include<locale>

using namespace std;

int main(int argc, char*argv[]){
	
	setlocale(LC_ALL,"");
	system ("color e0");
	
	int i=0, j=0, cantidadMatrices, fila=0, columna=0, opcion, contar=0;
	float matriz[10][10][10]; 
	int filas[10];
	int columnas[10];
	float matrizResultado[10][10] = {0};
	float matrizTemporal[10][10] = {0};
	float matrizResta[10][10] = {0};
	float matrizCuadrado[10][10][10] = {0};
	bool contienenCeros = false;
	
	cout << "\t\t\tParcial Calculadora de Matrices.\n\n";
	
	cout << "Cuantas matrices deseas operar: ";
	cin >> cantidadMatrices;
	cout << endl;
	
	for (i=0; i<cantidadMatrices; i++){
		cout << "En la matriz " << i+1 << " cuantas filas deseas: ";
		cin >> filas[i];
		cout << "En la matriz "<< i+1 << " cuantas columnas deseas: ";
		cin >> columnas[i];
		cout << endl;	
		
		cout << "\t\tDigita de la matriz " << i+1 << endl;
		cout << endl; 
		
		for (fila=0; fila<filas[i]; fila++)
			for (columna=0; columna<columnas[i]; columna++){
				cout << "El dato numerico de la posición, fila " << fila+1 << " y columna " << columna+1 << ": ";
				cin >> matriz[i][fila][columna];	
			}
		cout << endl;
	}
	
	// Imprimir las matrices:
	
	for (i=0; i<cantidadMatrices; i++){
		cout << "La matriz " << i+1 << " es: " << endl;
    	cout << endl;
		for (fila=0; fila<filas[i]; fila++){
			for (columna=0; columna<columnas[i]; columna++)
				cout << matriz[i][fila][columna] << " ";
				cout << endl;
		}
		cout << endl;	
	}
	
	cout << "Opciones de operación a realizar:.\n\n";
	
	cout << "1. Suma\n";
	cout << "2. Resta\n";
	cout << "3. Multiplicación\n";
	cout << "4. División\n";
	cout << "5. Transpuesta\n";
	cout << "6. Elevados al cuadrado\n";
	cout << "7. Salir de la calculadora\n\n";
	
	cout << "Elije una opcion: ";
	cin >> opcion;
	cout << endl;
	
	switch (opcion){
		
		case 1: // Sumar Matrices:
			 
			for (i=1; i<cantidadMatrices; i++)	
				if ((filas[0] != filas[i])||(columnas[0] != columnas[i]))
					contar++;
					
			if (contar > 0){
				cout << "No se pueden sumar las matrices ya que no son iguales."<< endl << endl;
			}
				
			else{
			 	
			 	for (i=0; i<cantidadMatrices; i++)
					for (fila=0; fila<filas[0]; fila++)
						for (columna=0; columna<columnas[0]; columna++)
							if (i<cantidadMatrices){
								matrizResultado[fila][columna] += matriz[i][fila][columna];
							}else{
								break;
							}
				
				cout << "La matriz suma es: " << endl;
				cout << endl;
		
				for (fila=0; fila<filas[0]; fila++){
					for (columna=0; columna<columnas[0]; columna++)
						cout << matrizResultado[fila][columna] << " ";
						cout << endl;				
				}
				cout << endl;
			}
	
		break;
	
		case 2: // Restar Matrices:
			
			for (i=1; i<cantidadMatrices; i++)	
				if ((filas[0] != filas[i])||(columnas[0] != columnas[i]))
					contar++;
					
			if (contar > 0){
				cout << "No se pueden restar las matrices ya que no son iguales."<< endl << endl;
			}
				
			else{
			 	
			 	// La matriz resultado va ser igual que la primera matriz:
			 	
    			for (fila=0; fila<filas[0]; fila++)
        			for (columna=0; columna<columnas[0]; columna++)
            			matrizResultado[fila][columna] = matriz[0][fila][columna];
    			
			 	// Se va ir restando cada matriz y se va guardando en una matriz temporal:
    			
				for (i=1; i<cantidadMatrices; i++){	
        			for (fila=0; fila<filas[0]; fila++)
            			for (columna=0; columna<columnas[i]; columna++)
                    			matrizTemporal[fila][columna] = matrizResultado[fila][columna] - matriz[i][fila][columna];
        		
        		// Cuando termina la matriz temporal pasa a ser la matriz resultado para imprimir:
        		
				for (fila=0; fila<filas[0]; fila++)
            		for (columna=0; columna<columnas[i]; columna++)
                		matrizResultado[fila][columna] = matrizTemporal[fila][columna];
    			}
    			
    			cout << "La matriz resta es: " << endl;
    			cout << endl;
    			
    			for (fila=0; fila<filas[0]; fila++){
        			for (columna=0; columna<columnas[cantidadMatrices-1]; columna++)
            			cout << matrizResultado[fila][columna] << " ";
        				cout << endl;
    			}
    			cout << endl;
    		}
	
		break;
		
		case 3: // Multiplicar Matrices:
			
			// Comprobar si las matrices son compatibles:
			
			for (i=1; i<cantidadMatrices; i++)	
				if (columnas[0] != filas[i])
					contar++;
					
			if (contar > 0){
				cout << "No se pueden multiplicar las matrices ya que el numero de columnas no es igual al numero de filas."<< endl << endl;
			}
				
			else{
			 	
			 	// La matriz resultado ca ser igual que la primera matriz:
			 	
    			for (fila=0; fila<filas[0]; fila++)
        			for (columna=0; columna<columnas[0]; columna++)
            			matrizResultado[fila][columna] = matriz[0][fila][columna];
    			
    			// Se va ir multiplicando cada matriz y se va guardando temporalmente en una matriz temporal:
    			
				for (i=1; i<cantidadMatrices; i++){	
        			for (fila=0; fila<filas[0]; fila++)
            			for (columna=0; columna<columnas[i]; columna++)
                			for (j=0; j<columnas[0]; j++)
                    			matrizTemporal[fila][columna] += matrizResultado[fila][j] * matriz[i][j][columna];
        		
        		// Cuando termina la matriz temporal pasa a ser la matriz resultado para imprimir:
        		
				for (fila=0; fila<filas[0]; fila++)
            		for (columna=0; columna<columnas[i]; columna++)
                		matrizResultado[fila][columna] = matrizTemporal[fila][columna];	
    			}
    			
    			if (cantidadMatrices > 2){
    				for (i=0; i<1; i++){	
  		      			for (fila=0; fila<filas[0]; fila++)
        	    			for (columna=0; columna<columnas[i]; columna++)
            	    			for (j=0; j<columnas[0]; j++)
                	    			matrizResta[fila][columna] += matriz[i][fila][j] * matriz[i][j][columna];
               		}
    			
    				cout << "La matriz multiplicación es: " << endl;
    				cout << endl;
    			
    				for (fila=0; fila<filas[0]; fila++){
        				for (columna=0; columna<columnas[cantidadMatrices-1]; columna++)
            				cout << matrizResultado[fila][columna] - matrizResta[fila][columna] << " ";
        					cout << endl;
    				}
    				cout << endl;
    			}
    			else {
    				
    				cout << "La matriz multiplicación es: " << endl;
    				cout << endl;
    			
    				for (fila=0; fila<filas[0]; fila++){
        				for (columna=0; columna<columnas[cantidadMatrices-1]; columna++)
            				cout << matrizResultado[fila][columna] << " ";
        					cout << endl;
					}
				}
				cout << endl;
			}
	
		break;
		
		case 4: // Dividir Matrices:
		
			// Verificar que ninguna matriz contenga ceros y que sean iguales:
    		
    		for (i=1; i<cantidadMatrices; i++)	
				if ((filas[0] != filas[i])||(columnas[0] != columnas[i]))
					contar++;
							
			if (contar > 0){
				cout << "No se pueden dividir las matrices ya que no son iguales."<< endl << endl;
			}
			
			else {
				
    		for (i=0; i<cantidadMatrices; i++) {
        		for (fila=0; fila<filas[0]; fila++) {
            		for (columna=0; columna<columnas[0]; columna++) {
                		if (matriz[i][fila][columna] == 0) {
                    		contienenCeros = true;
                    		break;
               		 	}
       		    	}
            		if (contienenCeros) break;
        		}
        		if (contienenCeros) break;
    		}

    		if (contienenCeros) {
        		cout << "No se pueden dividir las matrices ya que una o más matrices contienen ceros." << endl;
        		cout << "Por lo tanto una o mas matrices no son invertibles para dividirlas." << endl << endl;
    		} 
			
			else {
    			
        		// La matriz resultado ca ser igual que la primera matriz:
			 	
    			for (fila=0; fila<filas[0]; fila++)
        			for (columna=0; columna<columnas[0]; columna++)
            			matrizResultado[fila][columna] = matriz[0][fila][columna];
    			
    			// Se va ir dividiendo cada matriz y se va guardando en una matriz temporal:
    			
				for (i=1; i<cantidadMatrices; i++){	
        			for (fila=0; fila<filas[0]; fila++)
            			for (columna=0; columna<columnas[i]; columna++)
                    			matrizTemporal[fila][columna] = matrizResultado[fila][columna] / matriz[i][fila][columna];
        		
        			// Cuando termina la matriz temporal pasa a ser la matriz resultado para imprimir:
        		
					for (fila=0; fila<filas[0]; fila++){
            			for (columna=0; columna<columnas[i]; columna++)
                			matrizResultado[fila][columna] = matrizTemporal[fila][columna];
    				}
    			}
    			
    			cout << "La matriz división es: " << endl;
    			cout << endl;
    			
    			for (fila=0; fila<filas[0]; fila++){
        			for (columna=0; columna<columnas[cantidadMatrices-1]; columna++)
           				cout << matrizResultado[fila][columna] << " ";
       					cout << endl;
   				}
   				cout << endl;
   			}
   		}
    	
		
		break;
	
		case 5: // Transponer Matrices:
		
			cout << "La matriz Transpuesta es: " << endl;
			cout << endl;
		
			for (i=0; i<cantidadMatrices; i++){
				for (columna=0; columna<columnas[i]; columna++){
					for (fila=0; fila<filas[i]; fila++)
						cout << matriz[i][fila][columna] << " ";
						cout << endl;
				}
				cout << endl;
			}
						
		break;
		
		case 6: // Matrices elevadas al cuadrado
			
			for (i=1; i<cantidadMatrices; i++)	
				if ((filas[0] != filas[i])||(columnas[0] != columnas[i]))
					contar++;
					
			if (contar > 0){
				cout << "No se pueden elevar al cuadrado las matrices ya que no son iguales."<< endl;
				cout << "Si quieres ingresalas por separado o ingresa matrices iguales."<< endl;
				cout << endl;
			}
				
			else{
				
				cout << "Los elementos elevados al cuadrado serian: " << endl;
				cout << endl;
			
   				for (i=0; i<cantidadMatrices; i++){	
	      			for (fila=0; fila<filas[0]; fila++)
       	    			for (columna=0; columna<columnas[i]; columna++)
           	    			for (j=0; j<columnas[0]; j++)
               	    			matrizResultado[fila][columna] += matriz[i][fila][j] * matriz[i][j][columna];
               	}
               	
               	for (i=0; i<1; i++){	
      				for (fila=0; fila<filas[0]; fila++)
   	    				for (columna=0; columna<columnas[i]; columna++)
       	    				for (j=0; j<columnas[0]; j++)
           	    				matrizResta[fila][columna] += matriz[i][fila][j] * matriz[i][j][columna];
       			}
                	
				if (cantidadMatrices > 1){
					
					for (i=0; i<cantidadMatrices; i++){
						cout << "La matriz " << i+1 << " elevada al cuadrado es: " << endl;
   						cout << endl;
   						for (fila=0; fila<filas[0]; fila++){
       						for (columna=0; columna<columnas[cantidadMatrices-1]; columna++)
           						cout << matrizResultado[fila][columna] - matrizResta[fila][columna] << " ";
       							cout << endl;
       					}
       					cout << endl;
   					}
   					cout << endl;
   				}
    				
				else{
					    			
   					cout << "La matriz elevada al cuadrado es: " << endl;
   					cout << endl;
    			
   					for (fila=0; fila<filas[0]; fila++){
       					for (columna=0; columna<columnas[cantidadMatrices-1]; columna++)
           					cout << matrizResultado[fila][columna] << " ";
       						cout << endl;
   					}
   					cout << endl;
   				}	
			}
			
		break;
	
		case 7: // Salir de la Calculadora	
		
		return 0;
		
		break; 	
	}
	
	system("pause");
	return 0;
	
}