#include<iostream>
#include <iomanip>
bool IsEmpty();
void Enqueue();
void Traverse();
void samarey();
void payment();
void add();
void delet();
void order();
int custmer_bill;
double counts[4];
double total_bill = 0;
double total_sels = 0;
double unitprice[4] = { 8.00,2.00,9.00,5.00 };
double amountofsels[4];
double totalamountofsels[4];
int QUANTITY[4];
int TOTALQUANTITY[4];
int Queue[4];
int front = -1;
int rear = -1;
int countss = 0;

int main()
{

	int c;
	int q = 1;


	std::cout << "\n\n\t\t\t\t\t\t--------Menu--------\n\n";

	std::cout << "\t\t\t\t\t\t1) Order\n";
	std::cout << "\t\t\t\t\t\t2) Payment\n";
	std::cout << "\t\t\t\t\t\t3) samarey\n";
	std::cout << "\t\t\t\t\t\t4) exit\n";
	std::cout << "\n\t\t\t\t\t\tPlease Enter your Choice: ";

	while (q != 0) {
		std::cin >> c;
		switch (c)
		{


		case 1:
			order();
			return main();
			break;
		case 2:
			payment();
			return main();
			break;
		case 3:
			samarey();
			return main();
			break;


		case 4:

			return 0;
		}
	}
}

bool IsEmpty() { if (countss == 0)return true; else return false; }
void Enqueue()
{
	if (countss == 0) rear = front = 0; // first item to enqueue
	else if (rear == 4 - 1) rear = 0; // Circular, rear set to zero
	else rear++; //
	Queue[rear] = total_bill;
	countss++;

}

void Traverse()
{
	if (IsEmpty()) { std::cout << "\n\n\t\t\t\t\t\t QUEUE is empty\n"; return; }
	int i = front;
	for (int xc = 0; Queue[xc]; xc++) {

		std::cout << "\n\t\t\t\t\t\tthe coustmer " << i <<" cost: " << Queue[i] << "\n";
		i++;
	}
}

void add() {
	int e;
	std::cout << "\n\t\t\t\t\t\t               Menu Food                 Price:         \n";
	std::cout << "\t\t\t\t\t\t1) Burger                                 8  SAR        \n";
	std::cout << "\t\t\t\t\t\t2) Cola                                   2  SAR        \n";
	std::cout << "\t\t\t\t\t\t3) Shawerma                               9  SAR        \n";
	std::cout << "\t\t\t\t\t\t4) Flafel                                 5  SAR        \n";
	std::cout << "\t\t\t\t\t\tEnter your order number: ";
	std::cin >> e;
	switch (e) {

	case 1:
		std::cout << "\n\t\t\t\t\t\tHow Many Burger Do You Want: ";
		std::cin >> QUANTITY[0];
		amountofsels[0] = unitprice[0] * QUANTITY[0];
		total_bill = total_bill + amountofsels[0];
		break;

	case 2:
		std::cout << "\n\t\t\t\t\t\tHow Many Cola Do You Want: ";
		std::cin >> QUANTITY[1];
		amountofsels[1] = unitprice[1] * QUANTITY[1];
		total_bill = total_bill + amountofsels[1];
		break;
	case 3:

		std::cout << "\n\t\t\t\t\t\tHow Many Shawerma Do You Want: ";
		std::cin >> QUANTITY[2];
		amountofsels[2] = unitprice[2] * QUANTITY[2];
		total_bill = total_bill + amountofsels[2];
		break;
	case 4:

		std::cout << "\n\t\t\t\t\t\tHow Many Flafel Do You Want: ";
		std::cin >> QUANTITY[3];
		amountofsels[3] = unitprice[3] * QUANTITY[3];
		total_bill = total_bill + amountofsels[3];
		break;
	default: std::cout << "\t\t\t\t\t\tPlease Choose A Valid Item\n";
		return;
	}

}
void delet() {
	int a;
	std::cout << "\t\t\t\t\t\t___________________________________________________________\n";
	std::cout << "\t\t\t\t\t\t" << std::left << std::setw(15) << "ITEM" << std::right << std::setw(10) << "QUANTITY" << std::right << std::setw(15) << "UNIT PRICE" << std::right << std::setw(20) << "AMOUNT OF SALE\n";
	std::cout << "\t\t\t\t\t\t___________________________________________________________\n";
	if (QUANTITY[0] > 0) {

		std::cout << "\n\t\t\t\t\t\tBurger\t" << std::setw(12) << std::right << QUANTITY[0] << std::setw(15) << std::right << unitprice[0] << std::setw(20) << std::right << amountofsels[0] << std::endl;
	}
	if (QUANTITY[1] > 0) {

		std::cout << "\n\t\t\t\t\t\tCola\t" << std::setw(12) << std::right << QUANTITY[1] << std::setw(15) << std::right << unitprice[1] << std::setw(20) << std::right << amountofsels[1] << std::endl;
	}
	if (QUANTITY[2] > 0) {

		std::cout << "\n\t\t\t\t\t\tShawerma" << std::setw(12) << std::right << QUANTITY[2] << std::setw(15) << std::right << unitprice[2] << std::setw(20) << std::right << amountofsels[2] << std::endl;
	}
	if (QUANTITY[3] > 0) {

		std::cout << "\n\t\t\t\t\t\tFlafel\t" << std::setw(12) << std::right << QUANTITY[3] << std::setw(15) << std::right << unitprice[3] << std::setw(20) << std::right << amountofsels[3] << std::endl;
	}
	std::cout << "\n\t\t\t\t\t\tEnter the number of Meal you want to delete\n\t\t\t\t\t\t1)Burger\n\t\t\t\t\t\t2)Cola\n\t\t\t\t\t\t3)Shawerma\n\t\t\t\t\t\t4)Flafel\n\t\t\t\t\t\tYour Choice:  ";



	std::cin >> a;
	switch (a)
	{
	case 1:
		if (QUANTITY[0] > 0) {
			QUANTITY[0] = 0;
			amountofsels[0] = 0;
			std::cout << "\n\t\t\t\t\t\tBurger Deleted!!\n";
		}
		else {
			std::cout << "\t\t\t\t\t\t\t\tPlease Choose A Valid Item\n";
		}
		break;
	case 2:
		if (QUANTITY[1] > 0) {
			QUANTITY[1] = 0;
			amountofsels[1] = 0;
			std::cout << "\n\t\t\t\t\t\tCola Deleted!!\n";
		}
		else {
			std::cout << "\t\t\t\t\t\tPlease Choose A Valid Item\n";
		}
		break;
	case 3:
		if (QUANTITY[2] > 0) {
			QUANTITY[2] = 0;
			amountofsels[2] = 0;
			std::cout << "\n\t\t\t\t\t\tShawerma Deleted!!\n";
		}
		else {
			std::cout << "\t\t\t\t\t\tPlease Choose A Valid Item\n";
		}
		break;
	case 4:
		if (QUANTITY[3] > 0) {
			QUANTITY[3] = 0;
			amountofsels[3] = 0;
			std::cout << "\n\t\t\t\t\t\tFlafel Deleted!!\n";
		}
		else {
			std::cout << "\t\t\t\t\t\tPlease Choose A Valid Item\n";
		}
		break;

	default:
		std::cout << "\t\t\t\t\t\tPlease Choose A Valid Item\n";
		break;
	}

	return order();
}
void payment() {
	int f;
	int pin;
	std::cout << "\t\t\t\t\t\tYou Have Ordered:\n\n";
	std::cout << "\t\t\t\t\t\t___________________________________________________________\n";
	std::cout << "\t\t\t\t\t\t" << std::left << std::setw(15) << "ITEM" << std::right << std::setw(10) << "QUANTITY" << std::right << std::setw(15) << "UNIT PRICE" << std::right << std::setw(20) << "AMOUNT OF SALE\n";
	std::cout << "\t\t\t\t\t\t___________________________________________________________\n";
	if (QUANTITY[0] > 0) {

		std::cout << "\n\t\t\t\t\t\tBurger\t" << std::setw(12) << std::right << QUANTITY[0] << std::setw(15) << std::right << unitprice[0] << std::setw(20) << std::right << amountofsels[0] << std::endl;
	}
	if (QUANTITY[1] > 0) {

		std::cout << "\n\t\t\t\t\t\tCola\t" << std::setw(12) << std::right << QUANTITY[1] << std::setw(15) << std::right << unitprice[1] << std::setw(20) << std::right << amountofsels[1] << std::endl;
	}
	if (QUANTITY[2] > 0) {

		std::cout << "\n\t\t\t\t\t\tShawerma" << std::setw(12) << std::right << QUANTITY[2] << std::setw(15) << std::right << unitprice[2] << std::setw(20) << std::right << amountofsels[2] << std::endl;
	}
	if (QUANTITY[3] > 0) {

		std::cout << "\n\t\t\t\t\t\tFlafel\t" << std::setw(12) << std::right << QUANTITY[3] << std::setw(15) << std::right << unitprice[3] << std::setw(20) << std::right << amountofsels[3] << std::endl;
	}

	std::cout << "\n\t\t\t\t\t\tThe Total Cost is: " << total_bill << std::endl;

	if (total_bill > 0) {
		std::cout << "\n\t\t\t\t\t\tEnter Your PIN Card to Pay: ";
		std::cin >> pin;
	}
	Enqueue();
	total_sels = total_sels + total_bill;
	for (int t = 0; t < 4; t++) {

		totalamountofsels[t] = totalamountofsels[t] + amountofsels[t];
		TOTALQUANTITY[t] = TOTALQUANTITY[t] + QUANTITY[t];
		amountofsels[t] = 0;
		QUANTITY[t] = 0;
		total_bill = 0;
	}
	std::cout << "\n\t\t\t\t\t\tThank You for Ordring ";

	std::cout << "\n\t\t\t\t\t\tEnter Any number To Back To The Main Menu: ";
	std::cin >> f;

}
void samarey() {
	int b;
	int x = 0;
	std::cout << "\t\t\t\t\t\t The total order for today\n\n";
	std::cout << "\t\t\t\t\t\t____________________________________________________________________\n";
	std::cout << "\t\t\t\t\t\t" << std::left << std::setw(15) << "ITEM" << std::right << std::setw(10) << "TOTAL QUANTITY" << std::right << std::setw(15) << "UNIT PRICE\t" << std::right << std::setw(20) << "TOTAL AMOUNT OF SALE\n";
	std::cout << "\t\t\t\t\t\t____________________________________________________________________\n";
	if (TOTALQUANTITY[0] > 0) {

		std::cout << "\n\t\t\t\t\t\tBurger\t" << std::setw(12) << std::right << TOTALQUANTITY[0] << std::setw(15) << std::right << unitprice[0] << std::setw(20) << std::right << totalamountofsels[0] << std::endl;
	}
	if (TOTALQUANTITY[1] > 0) {

		std::cout << "\n\t\t\t\t\t\tCola\t" << std::setw(12) << std::right << TOTALQUANTITY[1] << std::setw(15) << std::right << unitprice[1] << std::setw(20) << std::right << totalamountofsels[1] << std::endl;
	}
	if (TOTALQUANTITY[2] > 0) {

		std::cout << "\n\t\t\t\t\t\tShawerma" << std::setw(12) << std::right << TOTALQUANTITY[2] << std::setw(15) << std::right << unitprice[2] << std::setw(20) << std::right << totalamountofsels[2] << std::endl;
	}
	if (TOTALQUANTITY[3] > 0) {

		std::cout << "\n\t\t\t\t\t\tFlafel\t" << std::setw(12) << std::right << TOTALQUANTITY[3] << std::setw(15) << std::right << unitprice[3] << std::setw(20) << std::right << totalamountofsels[3] << std::endl;
	}

	Traverse();

	std::cout << "\n\t\t\t\t\t\tThe Total Sells Today is: " << total_sels << std::endl;


	std::cout << "\n\t\t\t\t\t\tEnter Any number To Back To The Main Menu:  ";
	std::cin >> b;
}


void order() {
	int j;
	int b = 1;
	int zz;
	int r;
	std::cout << "\n\t\t\t\t\t\t---ORDER PAGE--\n";
	std::cout << "\t\t\t\t\t\t1) Add Order\n";
	std::cout << "\t\t\t\t\t\t2) Delete Order\n";
	std::cout << "\t\t\t\t\t\t3) Back To Main Menu\n\n\n\n\n";
	std::cout << "\t\t\t\t\t\tEnter your choise: ";
	while (b != 0) {
		std::cin >> j;

		switch (j) {

		case 1:
			add();
			std::cout << "\n\t\t\t\t\t\tEnter 1 to cuntenue and 0 to back:";
			std::cin >> zz;
			if (zz != 1) {
				return order();
			}
			break;
		case 2:
			delet();


			break;
		case 3:
			b = 0;
			break;


		}
	}
}
