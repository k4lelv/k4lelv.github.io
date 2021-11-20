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

## Lista de ejercicios

Antes que nada, quiero recordar que estos ejercicios son sacado de un libro de texto que no recuerdo muy bien xd, si lo encuentro, mas tarde, les dejaré un link por si lo quieren ir a ver mas detalladamente.

Comenzamos abriendo algun editor de texto a tu gusto, en este caso, yo trabajaré con el programa `Dev C++`.

El primer Ejercicio nos dice:

* Calcular los N primeros multiplos de 4 (4 inclusive), donde N es un valor introducido por teclado.

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
	
	//Agregamos un loop para que el usuario si desea seguir probando el codigo lo pueda hacer sin necesidad de volverlo a correr
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

* El sistema de calificación americano (de Estados Unidos) se suele calcular de acuerdo al siguiente cuadro:


Utilizando esta información, escribir un algoritmo que acepte una calificación numeérica del estudiante (0-100), convierta esta calificación a su equivalente en letra y visualice la calificación correspondiente en letra.


* Se pretende leer todos los empleados de una empresa situados en un archivo `EMPRESA` y a la terminación de la lectura del archivo se debe visualizar un mensaje <<existen trabajadores mayores de 65 años en un número de ...>> y el número de trabajadores mayores de 65 años.


* Diseñar un algoritmo para calucular el máximo común divisor de cuatro números basado en un subalgoritmo función mcd (máximo común divisor de dos números).


* Diseñar un algoritmo que calcule el mayor valor de una lista L de N elementos


* Realizar un algoritmo que permute tres números enteros. n1, n2, n3 en orden creciente.


* Implementar una clase `Automóvil` (carro) dentro de una jerarquía de herencia múltiple. Considere que, además de ser un `Vehículo` es tambien una comodidadm un símbolo de estado social, un modo de transporte, etc. `Automóvil` debe tener al menos tres clases base y al menos 3 clases derivadas.