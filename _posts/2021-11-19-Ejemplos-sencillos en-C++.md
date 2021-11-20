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
<p align="center">
<img src="https://k4lelv.github.io/assets/images/c++-examples/tablaCalificaciones.png">
</p>

Utilizando esta información, escribir un algoritmo que acepte una calificación numeérica del estudiante (0-100), convierta esta calificación a su equivalente en letra y visualice la calificación correspondiente en letra.

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

<a href="https://drive.google.com/file/d/1U9p4Oa2G0M14Qgj96Wuf-ViVoQtg3Hy9/view?usp=sharing" target="_blank">Descarga EMPRESA.txt</a>

- - -
## Diseñar un algoritmo para calucular el máximo común divisor de cuatro números basado en un subalgoritmo función mcd (máximo común divisor de dos números).

- - -

## Diseñar un algoritmo que calcule el mayor valor de una lista L de N elementos

- - -

## Realizar un algoritmo que permute tres números enteros. n1, n2, n3 en orden creciente.

- - -

## Implementar una clase `Automóvil` (carro) dentro de una jerarquía de herencia múltiple. Considere que, además de ser un `Vehículo` es tambien una comodidadm un símbolo de estado social, un modo de transporte, etc. `Automóvil` debe tener al menos tres clases base y al menos 3 clases derivadas.