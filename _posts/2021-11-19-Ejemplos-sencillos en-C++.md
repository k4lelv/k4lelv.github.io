---
layout: single
title: Ejemplos sencillos para practicar en C++
excerpt: "Recordando los viejos tiempos, aqui te muestro algunos ejercicios buenos para practicar logica de programacion en el lenguaje de C++, Veamos de cuantos eres capaz de resolver."
date: 2021-11-19
classes: wide
header:
  teaser: https://k4lelv.github.io/assets/images/c++-examples/hacker-pc-blue.png
  teaser_home_page: true
categories:
  - Ejercicios
tags:
  - Practica
  - C++
---

![](https://k4lelv.github.io/assets/images/c++-examples/vs-code-in-a-computer.jpg)

# Lista de ejercicios

Antes que nada, quiero recordar que estos ejercicios son sacado de un libro de texto que no recuerdo muy bien xd, si lo encuentro, mas tarde, les dejaré un link por si lo quieren ir a ver mas detalladamente.

Comenzamos abriendo algun editor de texto a tu gusto, en este caso, yo trabajaré con el programa `Dev C++`.

El primer Ejercicio nos dice:

## Calcular los N primeros multiplos de 4 (4 inclusive), donde N es un valor introducido por teclado.

```c++
//Calculando los n primeros numeros multiplos de 4
#include <iostream>

using namespace std;

int main (){
	
	//Definiendo variables
	int input = 0;
	int x = 4;
	double multiplo = 0;
	char flag;
	
	/*Agregamos un loop para que el usuario si desea seguir probando el codigo 
    lo pueda hacer sin necesidad de volverlo a correr */
	do{
		//Ingreso de dato
		cout << "\nCuantos multiplos del numero (4) desea calcular?\n -> ";
		cin >> input;

		cout << "\n-----------------------------------------------";
		cout << "\nLos multiplos son: ";
		//Calculo de los multiplos con un ciclo (FOR)
		for(int i = 1; i < (input + 1); i++){
			multiplo = i * x;
			cout << "[" << multiplo << "] ";
		}
		
		//Menu footer
		cout << "\n\n-----------------------------------------------";
		cout <<"\nQuiere seguir caluculando multiplos? (s/n)\n -> ";
		cin >> flag;
		cout << "\n-----------------------------------------------\n";
		//Limpiando Pantalla
		system("cls");
		
	} while(flag == 's' || flag == 'S');
	
	cout << "\n--------------------------------\n";
	cout << "Gracias :)\n\n";
	
	cout << "Author: https://k4lelv.github.io ";
	
	return 0;
}
```


- - -
## El sistema de calificación americano (de Estados Unidos) se suele calcular de acuerdo al siguiente cuadro:

<p center="left">
<img src="https://k4lelv.github.io/assets/images/c++-examples/tablaCalificaciones.png">
</p> Utilizando esta información, escribir un algoritmo que acepte una calificación numeérica del estudiante (0-100), convierta esta calificación a su equivalente en letra y visualice la calificación correspondiente en letra.

```c++
// Sistema de calificacion de Estados Unidos
#include <iostream>

using namespace std;

int main(){
	//Definiendo las variables a utilizar
	int flag = 0;
	double notaInput = 0;
	string conversion;
	char miniFlag;
	
	do{
		cout <<"Menu de opciones";
		cout <<"\n1. Calificar (sistema de cakificacion EE.UU)";
		cout <<"\n2. Ver cuadro de Calificaciones";
		cout <<"\n3. Salir\n  -> ";
		cin >> flag;
		
		switch(flag){
			case 1:
				do{
					cout <<"\n############################################\n";
					//Ingreso de datos
					cout << "\nIngrese nota:\n-> ";
					cin >> notaInput;
					
					//Conversion de los sistemas de calificacion
					if(notaInput >= 90 && notaInput < 100){
						cout <<"\n** WOW, Tu calificion es una " << "A **\n\n";
					}
					else if(notaInput < 90 && notaInput >= 80){
						cout <<"\n** Esta bien, Tu calificion es una " << "B **\n\n";
					}
					else if(notaInput < 80 && notaInput >= 70){
						cout <<"\n **No esta mal, pero puede ser mejor, Tu calificacion es una " << "C **\n\n";
					}
					else if(notaInput < 70 && notaInput >= 60){
						cout <<"\n **Deberias mejorar un poco, Tu calificion es una " << "D **\n\n";
					}
					else if(notaInput < 69){
						cout <<"\n **Talves esto no sea lo tuyo :), Tu calificion es una " << "F **\n\n";
					}else{//Mandamos este mensaje de error cuando la nota ingresada sea mayor a 100
						cout <<"\nEsto no es una nota, revisalo porfavor y vuelve a intentarlo\n\n";
					}
					//Submenu para elegir si quiere seguir calificando sin volver al menu principal
					cout <<"\n############################################\n\n";
					cout <<"Quieres seguir calificando (s/n)\n -> ";
					cin >> miniFlag;
					system("cls");
				} while (miniFlag == 's' || miniFlag == 'S');
				break;
			case 2:
				/*Mostramos el pequeño catalogo de las calificaciones y sus equivalencias 
                entre ambos sistemas de calificacion */

				cout <<"\n############################################";
				cout <<"\nSistema de Calificaciones de EEUU\n";
				cout <<"\nMayor o Igual a 90 --------------------- A";
				cout <<"\nMenor de 90 pero Mayor o igual a 80 ---- B";
				cout <<"\nMenor de 80 pero Mayor o igual a 70 ---- C";
				cout <<"\nMenor de 70 pero Mayor o igual a 60 ---- D";
				cout <<"\nMenor de 69----------------------------- F\n";
				cout <<"\n############################################\n\n";
				break;
		}
		
	} while(flag != 3);
	
	cout << "\n--------------------------------\n";
	cout << "Gracias :)\n\n";
	
	cout << "Author: https://k4lelv.github.io ";
}
```


- - -
## Se pretende leer todos los empleados de una empresa situados en un archivo `EMPRESA` y a la terminación de la lectura del archivo se debe visualizar un mensaje <<existen trabajadores mayores de 65 años en un número de ...>> y el número de trabajadores mayores de 65 años.

Para poder empezar a resolverlo necesitamos este archivo que le pondremos de nombre `EMPRESA`, no es mas que un archivo `.txt` en el cual estará una base de datos de Empleados con las siguientes especificaciones: `Nombre`, `Apellido`, `Edad`, `Cargo`. 
<br>
Esta lista fue generada gracias a [Mockaroo.com](https://www.mockaroo.com/).
<br>
Pero para facilitar el proceso les dejo un link para q se lo descarguen aqui: <a href="https://drive.google.com/file/d/1U9p4Oa2G0M14Qgj96Wuf-ViVoQtg3Hy9/view?usp=sharing" target="_blank">Descarga EMPRESA.txt</a>

Ahora si, estamos listo. `Siiiuuuu`

```c++
//Leer la edad de trabajadores desde un archivo txt llamado EMPRESA
#include <iostream>
#include <string.h>
#include <iomanip>
#include <sstream>
#include <vector>
#include <fstream>
#include <cstdlib>

using namespace std;


int main(){
	
	//Definiendo las variables que ocuparemos para este caso
	string Nombre, apellido, edad, cargo; //variables del archivo a ocupar (las columnas)
	vector<string>NAME;
	vector<string>LASTNAME;
	vector<int>AGE;
	vector<string>TITLEJOB;
	int flag = 0;
	int cuenta = 0;
	
	cout << "-------------------------------------------------------------";
	cout << "\t\t\t\tMenu de Opciones\n";
	cout << "1. Visualizar los trabajadores con edad mayores a 65 anios\n";
	cout << "2. Visualizar toda la lista de empleados de 'EMPRESA'\n  -> ";
	cin >> flag;
	
	if(flag == 1){
		ifstream archivo;
		archivo.open("EMPRESA.txt",ios::in); //Ahora procedemos a abrir nuestro archivo en modo de lectura solamente
		
		//validamos los posibles errores al abrir un archivo
		if(archivo.fail()){
			cout <<"Ups, No se pudo abrir el archivo";
			exit(1);
		}
		
		//numero de lineas
		int i = 0;
		
		while(!archivo.eof()){
			string linea;
			getline(archivo,linea);//Para ignorar la primera fila donde se encuentra las columnas
			
			//Convertimos las datos de string a entero en el caso de la edad
			getline(archivo,Nombre, ',');
			NAME.push_back(Nombre);
			getline(archivo,apellido,',');
			LASTNAME.push_back(apellido);
			getline(archivo,edad,',');
			AGE.push_back(atoi(edad.c_str())+2);
			
			i += 1;
		}
		
		cout << "\n\n########################################################\n\n";
		archivo.close();//Cerramos el archivo para terminar la ejecucion
		cout << "--> Numero de empleados total: " << (i-1) << endl;	
		
		for(int j = 0; j < i; j++){//Iniciamos a contar el numero de veces en el que el numero 65 se menciona en el archivo
			
			if(AGE[j] > 65){
				cuenta += 1;
			}
		}
		cout << "\n\n--> El numero de empleado con edad mayores de 65 anios es de: " << cuenta << endl;
		cout << "\n########################################################";
	}
	else if(flag == 2){
		//Abrimos el archivo de texto con los datos
		ifstream archivo;
		archivo.open("EMPRESA.txt",ios::in); //Ahora procedemos a abrir nuestro archivo en modo de lectura solamente
		
		//validamos los posibles errores al abrir un archivo
		if(archivo.fail()){
			cout <<"Ups, No se pudo abrir el archivo";
			exit(1);
		}
		
		//numero de lineas
		int i = 0;
		
		while(!archivo.eof()){//Le decimos que hasta no termine de leer todo el archivo, haga lo siguiente
			
			string linea;
			getline(archivo,linea);//Para ignorar la primera fila donde se encuentra las columnas
			
			getline(archivo,Nombre, ',');
			NAME.push_back(Nombre);
			getline(archivo,apellido,',');
			LASTNAME.push_back(apellido);
			getline(archivo,edad,',');
			AGE.push_back(atoi(edad.c_str())+2);
			getline(archivo,cargo,',');
			TITLEJOB.push_back(cargo);
			
			i += 1;
		}
		
		archivo.close();//Cerramos el archivo para terminar la ejecucion
		cout << "Numero de empleados total: " << (i-1) << endl;
		
		//Visualizamos el archivo en la consola por columnas
		cout << "Nombres" << "\t" << "Apellidos" << "\t"<< "Edad" << "\t" << "Cargo" << endl;
		
		for(int j = 0; j < i; j++){
			cout << NAME[j] << "\t" << LASTNAME[j] << "\t\t" << AGE[j] << "\t" << TITLEJOB[j] << endl;
		}
	}
	else{
		cout << "Porfavor elija una opcion del menu....";
	}

	return 0;
}
```


- - -
## Diseñar un algoritmo para calucular el máximo común divisor de dos números basado en un subalgoritmo función mcd (máximo común divisor de dos números).

```c++
//Calculo de Maximo comun divisor de 2 numeros, 

#include <iostream>
#include <algorithm>

using namespace std;

int main(){
	//Declaracion de variables
	int num1, num2, max, min, divisor, flag;
	
	do{
		cout <<"\t\tMenu de Opciones\n";
		cout <<"1. Calculo de MCD\n";
		cout <<"2. Salir\n -> ";
		cin >> flag;
		
		switch(flag){
			case 1: //Entrada de datos
				cout <<"\n---------------------------------------\n\n";
				cout <<"Ingrese el primer Numero: \n -> ";
				cin >> num1;
				cout <<"Ingrese el segundo Numero: \n -> ";
				cin >> num2;
				cout <<"\n\n---------------------------------------";
				
				//Debemos identificar cual numero es el mayor de y menor respectivamente
				max = std::max(num1,num2);
				min = std::min(num1,num2);
				
				do{//Calculo del divisor
					divisor = min;
					min = max % min;
					max = divisor; // Lo que va haciendo es continuar dividiendo
				} while(min != 0);
				
				//Mostramos el resultado
				system("cls");
				cout <<"\n\n--------------------------------------------------------";
				cout <<"\n\n-->El Maximo Comun Divisor entre "<< num1 << " y " << num2 << " es: " << divisor << endl;
				cout <<"\n\n--------------------------------------------------------\n";
				break;
			case 2:
				cout <<"--------------------------------";
				cout <<"\n\nOk, saliendo ...";
				break;
			default:
				break;
		}
	} while(flag != 2);
	
	
	return 0;
}
```

- - -
## Diseñar un algoritmo que calcule el mayor valor de una lista L de N elementos

- - -

## Realizar un algoritmo que permute tres números enteros. n1, n2, n3 en orden creciente.

- - -

## Implementar una clase `Automóvil` (carro) dentro de una jerarquía de herencia múltiple. Considere que, además de ser un `Vehículo` es tambien una comodidadm un símbolo de estado social, un modo de transporte, etc. `Automóvil` debe tener al menos tres clases base y al menos 3 clases derivadas.