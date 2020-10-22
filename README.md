# improved-guide
#include <iostream>
#include <iomanip>
#include <cstdlib>

using namespace std;

int main()
{
	float percent, num1, start_num, end_num, num2, x = 0, y = 0;
	char op, answer;
	bool flag = false;

	do
	{
		do
		{
			system("cls");
			cout << "\nEntre un numero del 0 al 10." << endl;
			cout << "> ";
			cin >> num1;
			cout << "\nEntre el numero desde donde desea comenzar:" << endl;
			cout << "> ";
			cin >> start_num;
			cout << "\nEntre el numero en donde desea terminar:" << endl;
			cout << "> ";
			cin >> end_num;
			cout << "\nEntre el operador con el que quiere practicar [+,-,*,/]:" << endl;
			cout << "> ";
			cin >> op;
			cout << endl;
			system("cls");
			switch (op)
			{
				case '+':
					for (start_num; start_num <= end_num; start_num++)
					{
						cout << num1 << " + " << start_num << " = ";
						cin >> num2;
						if (num2 == num1 + start_num)
						{
							cout << "Answer is correct!\n" << endl;
							y = y + 1;
						}
						else
							cout << "Answer is incorrect!\n" << endl;
						x = x + 1;
					}
					break;
				case '-':
					for (start_num; start_num <= end_num; start_num++)
					{
						cout << num1 << " - " << start_num << " = ";
						cin >> num2;
						if (num2 == num1 - start_num)
						{
							cout << "Answer is correct!\n" << endl;
							y = y + 1;
						}
						else
							cout << "Answer is incorrect!\n" << endl;
						x = x + 1;
					}
					break;
				case '*':
					for (start_num; start_num <= end_num; start_num++)
					{
						cout << num1 << " x " << start_num << " = ";
						cin >> num2;
						if (num2 == num1 * start_num)
						{
							cout << "Answer is correct!\n" << endl;
							y = y + 1;
						}
						else
							cout << "Answer is incorrect!\n" << endl;
						x = x + 1;
					}
					break;
				case '/':
					if (start_num == 0)
						flag = true;
					for (start_num; start_num <= end_num; start_num++)
					{
						cout << num1 << " / " << start_num << " = ";
						cin >> num2;
						if (num2 == num1 / start_num)
						{
							cout << "Answer is correct!\n" << endl;
							y = y + 1;
						}
						else
							cout << "Answer is incorrect!\n" << endl;
						x = x + 1;
					}
					break;
				default: flag = true;
			}
		} while (flag != false);

		percent = (y / x) * 100;

		system("cls");
		cout << "\nResults:" << endl;
		cout << "======================" << endl;
		cout << " Score              % " << endl;
		cout << "----------------------" << endl;
		cout << fixed << showpoint << setprecision(1);
		cout << "    " << y << "/" << x << "             " << percent << endl;
		if (percent >= 90)
			cout << "\n Grade: A" << endl;
		else if (percent >= 80)
			cout << "\n Grade: B" << endl;
		else if (percent >= 70)
			cout << "\n Grade: C" << endl;
		else if (percent >= 60)
			cout << "\n Grade: D" << endl;
		else
			cout << "\n Grade: F" << endl;
		cout << "======================" << endl;
		cout << "\n Would you like to practice again?[Y/y/N/n]" << endl;
		cout << " > ";
		cin >> answer;
	}while (answer != 'N' && answer != 'n');

	system("pause");
	return EXIT_SUCCESS;
}
