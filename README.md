ifstream in("Dani.txt"); 
if (!in) 
{ 
cout « " Неможливо відкрити файл \n "; 
exit(1); 
} 

in » a » b » c; 
double x1 = 0, x2 = 0, d = 0; 
system("cls"); 
cout « "Запусити програму на виконання?" « endl; 
system("pause"); 
system("cls"); 
cout « "Розв'язок квадратного рівняння: " « endl; 
cout « "Змінні a, b, c :" « endl; 
cout « a « " " « b « " " « c « endl; 
d = b * b - 4 * a*c; 
cout « "Дискримінант = " « d « endl; 
if (d<0) 
{ 
cout « "Рівняння не має коренів"; 
} 
else 
{ 
if (d == 0) 
{ 
x1 = -b / (2 * a); 
cout « "Рівняння має один корінь: \n" « x1; 
} 
else 
{ 

x1 = -b / (2 * a) - (sqrt(d)) / (2 * a); 
x2 = -b / (2 * a) + (sqrt(d)) / (2 * a); 
cout « "Рівняння має два кореня:\n"; 
cout « "X1=" « x1 « "\n"; 
cout « "X2=" « x2 « "\n"; 
} 
}system("pause");
