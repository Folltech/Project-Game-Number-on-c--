#include <iostream>
using namespace std;
int main()
{
	setlocale(LC_ALL, "RU");
	srand(time(NULL));
	int a = 0;
	int blis = 1;
	int shag = 0;
	int randNum = 1 + rand() % 100;
	bool stop = false;
	cout << "Угадайте случайное число от 1 до 100: " << endl;
	cin >> a;
	while (!stop)
	{
		if (a != randNum && (randNum - a ) < (randNum - blis))
		{
			if (randNum - a > 0)
			{
				blis = a;
				cout << "Больше" << endl;
				cin >> a;
			}
			else if (randNum - a < 0)
			{
				cout << "Меньше" << endl;
				cin >> a;
			}
		}
		else if (a == randNum)
		{
			cout << "Поздраляем! Вы победили!" << endl;
			stop = true;
		}
		else
		{
			cout << "Больше" << endl;
			cin >> a;
		}
		shag++;
	}
	cout << "Всего попыток: " << shag << endl;
	return 0;
}
