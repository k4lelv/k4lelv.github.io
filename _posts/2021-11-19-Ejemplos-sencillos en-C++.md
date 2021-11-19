---
layout: single
title: Ejmeplos sencillos para practicar en C++
excerpt: "Recordando los viejos tiempos, aqui te muestro algunos ejercicios buenos para practicar logica de programacion en el lenguaje de C++, Veamos de cuantos eres capaz de resolver"
date: 2021-11-19
classes: wide
header:
  teaser: https://k4lelv.github.io/assets/images/c++-examples/vs-code-in-a-computer
  teaser_home_page: true
categories:
  - Ejercicios
tags:
  - Practica
  - C++
---

<center>
<img src="https://k4lelv.github.io/assets/images/c++-examples/vs-code-in-a-computer">
</center>

## Lista de ejercicios

Antes que nada, quiero recordar que estos ejercicios son sacado de un libro de texto que no recuerdo muy bien xd, si lo encuentro, mas tarde, les dejare un link por si estan interesados.

Comenzamos abriendo algun editor de texto a tu gusto, en este caso lo trabaje con el programa `Dev C++`.

El primer Ejericio nos dice:

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
	
	cout << "Author: https://k4alelv.github.io ";
	
	return 0;
}
```