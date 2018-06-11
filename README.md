# Calculator
Final project Structure C#

//Because I am using my own library with functions
#include "Calculator_AndreaPinilla.h"



void main()
{
	char yesNo = ' ', title[50];
	string myStr;
	int choice = 0, NBAddition = 0, NBMulti = 0, i;
	float divisor = 0, divider = 0, quot, minuend = 0, substra = 0, differ, multi = 0, product, addend = 0, sum;

	DisplayMenu(&choice);
	ValiderChoice(&myStr, &choice);
	CalculAddition(&NBAddition, &addend, &sum, &yesNo, &choice);
	CalculDivision(&divisor, &divider, &quot, &yesNo, &choice);
	CalculSubstraction(&minuend, &substra, &differ, &yesNo, &choice);
	CalculMultiplication(&NBMulti, &multi, &product, &yesNo, &choice);
	Quit(&yesNo, &choice);

	
}

void DisplayTitle(char title[50])
{

	//Tabulate the title
	cout << "\t";
	//Loop to change each character in uppercase, depending on the length of the array of char
	for (int i = 0; i < strlen(title); i++)
	{
		//Make the changing to uppercase
		cout << char(toupper(title[i]));

	}
	//Next line and tabulate the underlining
	cout << "\n\t";
	for (int i = 0; i < strlen(title); i++)
	{
		//When the char is an space, void it and do not underline it
		if (isspace(title[i]))
		{
			cout << " ";
		}
		//Underline the rest
		else
		{
			cout << "-";
		}

	}
	//Next two lines
	cout << endl;
}

void DisplayMenu(int *ptrChoice)
{
	do
	{
		//Display menu of choices
		//Clear the screen
		system("Cls");
		DisplayTitle("calculator");
		DisplayTitle("by andrea pinilla");


		cout << "1- Addition\n";
		cout << "2- Division\n";
		cout << "3- Substraction\n";
		cout << "4- Multiplication\n";
		cout << "5- Quit\n\n";
	} while (*ptrChoice < 0 || *ptrChoice > 5);
}
void ValiderChoice(string *ptrMyStr, int *ptrChoice)
{
	//Validate if choice is a valid number
	cout << "Enter your choice: ";
	cin >> *ptrMyStr;
	stringstream(*ptrMyStr) >> *ptrChoice;
	//If is not possible is because is not a valid number
	if (!(stringstream(*ptrMyStr) >> *ptrChoice))
	{
		cout << "Invalid number\n";

	}
}
void CalculAddition(int *ptrNBAddition, float *ptrAddend, float *ptrSum, char *ptrYesNo, int *ptrChoice)
{
	if (*ptrChoice == 1)
	{
		do

		{
			do
			{
				//Clear the screen
				system("Cls");
				DisplayTitle("calculator");
				DisplayTitle("addition");
				cout << "Enter the number of values to add: ";
				cin >> *ptrNBAddition;
				cout << endl;
			} while (*ptrNBAddition < 2);
			//Loop for to ask the user to enter the values NBAddition
			*ptrSum = 0;
			for (int i = 0; i < *ptrNBAddition; i++)
			{
				cout << "Value " << (i + 1) << ": ";
				cin >> *ptrAddend;
				*ptrSum += *ptrAddend;

			}

			cout << "\nThe result is: " << *ptrSum << endl;
			// Ask the user if he/she wants to do another addition 
			//If the user enters Y or y, the menu Addition Calculator will appear again to do one more addition
			//If the user enters N or n, the program returns to the main menu
			//Loop until the user enters 'n' or 'y', lower or upper case
			do
			{
				cout << "Would you like to do another addition? (Y/N): ";
				cin >> *ptrYesNo;

			} while ((*ptrYesNo != 'Y' && *ptrYesNo != 'y') && (*ptrYesNo != 'N' && *ptrYesNo != 'n'));

		} while (*ptrYesNo == 'Y' || *ptrYesNo == 'y');
	}
	else
	{
		*ptrChoice == 2;
	}

}
void CalculDivision(float *ptrDivisor, float *ptrDivider, float *ptrQuot, char *ptrYesNo, int *ptrChoice)
{
	if (*ptrChoice == 2)
	{
		do

		{
			//Clear the screen
			system("Cls");
			//Display the Division Calculator
			DisplayTitle("calculator");
			DisplayTitle("division");

			cout << "Enter the value to divide: ";
			cin >> *ptrDivisor;
			*ptrQuot = 0;
			//Loop do to avoid the user enters a divider that equals to zero (exception error)
			do
			{
				cout << "Enter the divider: ";
				cin >> *ptrDivider;
			} while (*ptrDivider == 0);

			*ptrQuot = *ptrDivisor / *ptrDivider;
			cout << "\nThe result is: " << *ptrQuot << endl << endl;
			// Ask the user if he/she wants to do another division 
			//If the user enters Y or y, the menu Division Calculator will appear again to do one more division
			//If the user enters N or n, the program returns to the main menu
			//Loop until the user enters 'n' or 'y', lower or upper case
			do
			{
				cout << "Would you like to do another division? (Y/N): ";
				cin >> *ptrYesNo;

			} while ((*ptrYesNo != 'Y' && *ptrYesNo != 'y') && (*ptrYesNo != 'N' && *ptrYesNo != 'n'));

		} while (*ptrYesNo == 'Y' || *ptrYesNo == 'y');
	}
	else
	{
		*ptrChoice == 3;
	}
}

void CalculSubstraction(float *ptrMinuend, float *ptrSubstra, float *ptrDiffer, char *ptrYesNo, int *ptrChoice)
{
	if (*ptrChoice == 3)
	{
		do
		{
			//Clear the screen
			system("Cls");
			//Display the Division Calculator
			DisplayTitle("calculator");
			DisplayTitle("substraction");
			*ptrDiffer = 0;
			cout << "Enter the first value to substract: ";
			cin >> *ptrMinuend;

			cout << "Enter the second value to substract: ";
			cin >> *ptrSubstra;


			*ptrDiffer = *ptrMinuend - *ptrSubstra;
			cout << "\nThe result is: " << *ptrDiffer << endl << endl;
			// Ask the user if he/she wants to do another substraction 
			//If the user enters Y or y, the menu Substraction Calculator will appear again to do one more substraction
			//If the user enters N or n, the program returns to the main menu
			//Loop until the user enters 'n' or 'y', lower or upper case
			do
			{
				cout << "Would you like to do another substraction? (Y/N): ";
				cin >> *ptrYesNo;

			} while ((*ptrYesNo != 89 && *ptrYesNo != 121) && (*ptrYesNo != 78 && *ptrYesNo != 110));//ASCII numbers

		} while (*ptrYesNo == 'Y' || *ptrYesNo == 'y');

	}
	else
	{
		*ptrChoice == 4;
	}


}
void CalculMultiplication(int *ptrNBMulti, float *ptrMulti, float *ptrProduct, char *ptrYesNo, int *ptrChoice)
{
	if (*ptrChoice == 4)
	{

		do
		{
			//Clear the screen
			system("Cls");
			//Display the Division Calculator
			DisplayTitle("calculator");
			DisplayTitle("multiplication");
			//Loop do while the user enters less than two values
			do
			{
				cout << "Enter the number of values to multiply: ";
				cin >> *ptrNBMulti;
			} while (*ptrNBMulti < 2);
			//Loop for to ask the user to enter the values NBMulti
			*ptrProduct = 1;

			for (int i = 0; i < *ptrNBMulti; i++)
			{
				cout << "Value " << (i + 1) << ": ";
				cin >> *ptrMulti;

				*ptrProduct *= *ptrMulti;

			}
			cout << "\nThe result is: " << *ptrProduct << endl;
			// Ask the user if he/she wants to do another multiplication 
			//If the user enters Y or y, the menu Multiplication Calculator will appear again to do one more multiplication
			//If the user enters N or n, the program returns to the main menu
			//Loop until the user enters 'n' or 'y', lower or upper case
			do
			{
				cout << "Would you like to do another multiplication? (Y/N): ";
				cin >> *ptrYesNo;

			} while ((*ptrYesNo != 'Y' && *ptrYesNo != 'y') && (*ptrYesNo != 'N' && *ptrYesNo != 'n'));


		} while (*ptrYesNo == 'Y' || *ptrYesNo == 'y');
	}
	else
	{
		*ptrChoice == 4;

	}
}
void Quit(char *ptrYesNo, int *ptrChoice)
{
	//to quit
	if (*ptrChoice == 5)
	{
		
		*ptrYesNo = 'Y';//this line makes the statement equal to yes to quit the program 
	}
	else
	{
		//call main for be able to return to main when the operation is finish
		main();
	}
}
