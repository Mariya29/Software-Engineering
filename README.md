#include <iostream>
#include <fstream>
#include <string>
#include <windows.h>
using namespace std;
void register_1();
void read (string login, string parol);
void login();
void Urovnenie(double a, double b, double c)
{
	
	system("cls");
	cout << "Вийти?" << endl;
	in.close();
}
struct Users
{
	string login;
	string parol;
}users[100];

void main() {
	SetConsoleOutputCP(1251);
	SetConsoleCP(1251);
	system("cls");
	cout << "1.Реєстрація" << endl;
	cout << "2.Вхід" << endl;
	cout << "3.Ввійти, як гість" << endl;
	cout << "4.Вихід" << endl;
	double a = 0, b = 0, c = 0;
	int k;
	cin >> k;
	switch (k) {
	case 1: register_1();
	case 2: {login();
		Urovnenie(a, b, c);
		cout << "1.Повернутись у головне меню" << endl;
		cout << "2.Вихід" << endl;
		system("pause");
		int g;
		cin >> g;
		switch (g)
		{
		case 1: main();
		case 2: exit(0);
		}}
	case 3: {Urovnenie(a, b, c);
		cout << "1.Повернутись у головне меню" << endl;
		cout << "2.Вихід" << endl;
		system("pause");
		int g;
		cin >> g;
		switch (g)
		{
		case 1: main();
		case 2: exit(0);
		}}
	case 4: exit(0);
	}
}

void register_1() {
	string login, parol;
	system("cls");
	cout << "Введіть логін" << endl;
	cin >> login;
	cout << "Введіть пароль" << endl;
	cin >> parol;
	ofstream fout("users.txt", ios::app);
	fout << login << " " << parol << endl;
	cout << "" << endl;
	main();
}

void read(string login, string parol) {
	ifstream fin("users.txt");
	for (int i = 0; i<100; i++) {
		fin >> users[i].login >> users[i].parol;
	}
}

void login() {
	string login, parol;
	system("cls");
	cout << "Введіть логін" << endl;
	cin >> login;
	cout << "Введіть пароль" << endl;
	cin >> parol;
	read(login, parol);
	bool flag = true;
	for (int i = 0; i< 100; i++) {
		if (login == users[i].login && parol == users[i].parol) {
			cout << "Ви ввійшли!" << endl;
			flag = false;
			break;
		}
	}
	if (flag == true) {
		cout << "Не правильний логін або пароль" << endl;
		system("pause");
		main();
	}
	system("pause");
}
