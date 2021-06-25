# approximation1

#include <iostream>
#include <math.h>
using namespace std;

int main()
{
	setlocale(LC_ALL, "Rus");
	int n = 0;
	double a = 0, b = 0, c = 0;
	double s1 = 0, s2 = 0, s3 = 0, s4 = 0;
	double x[10000], y[10000];

	cout << "Введите количество элементов " << endl;
	cin >> n;

	cout << "Введите все Х " << endl;
	for (int i = 0; i < n; i++)
	{
		cin >> x[i];
	}

	cout << "Введите все Y " << endl;
	for (int i = 0; i < n; i++)
	{
		cin >> y[i];
	}


	for (int i = 0; i < n; i++)
	{
		s1 += x[i]; // сумма всех х
	}

	for (int i = 0; i < n; i++)
	{
		s2 += y[i]; // сумма всех y
	}

	for (int i = 0; i < n; i++)
	{
		s3 += x[i] * y[i]; // сумма  произведений х и y
	}

	for (int i = 0; i < n; i++)
	{
		s4 += pow(x[i], 2); // сумма всех х^2
	}


	a = (n*s3 - s1 * s2) / (n*s4 - pow(s1, 2));

	b = (s2 - a * s1) / n;

	for (int i = 0; i < n; i++)
	{
		c += pow((y[i] - (a*x[i] + b)),2); // рассчет погрешности
	}

	// округление значений
	a = round(a * 10000) / 10000;
	b = round(b * 10000) / 10000;
	c = round(c * 10000) / 10000;

	cout << endl << "Для данных значений формула аппроксимирующей прямой равна: y=" << a << "x + " << b << endl << "Погрешность равна " << c << endl;

	system("pause");
}
                                                                                                                                                  
