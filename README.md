#include <iostream>
using namespace std;

class Counter
{
public:
    Counter() { }

    Counter(int num) {
        sum = num;
    }

    void ShowNum() {
    x:
        if (sum > 12) {
            sum -= 12;
            goto x;
        }

        if (sum < 1) {
            sum += 12;
            goto x;
        }

        switch (sum) {
        case 1:
            cout << "1 - Сiчень - Зимовий місяць\n";
            break;
        case 2:
            cout << "2 - Лютий - Зимовий місяць\n";
            break;
        case 3:
            cout << "3 - Березень - Весняний місяць\n";
            break;
        case 4:
            cout << "4 - Квiтень - Весняний місяць\n";
            break;
        case 5:
            cout << "5 - Травень - Весняний місяць\n";
            break;
        case 6:
            cout << "6 - Червень - Лiтнiй місяць\n";
            break;
        case 7:
            cout << "7 - Липень - Лiтнiй місяць\n";
            break;
        case 8:
            cout << "8 - Серпень - Лiтнiй місяць\n";
            break;
        case 9:
            cout << "9 - Вересень - Осінній місяць\n";
            break;
        case 10:
            cout << "10 - Жовтень - Осінній місяць\n";
            break;
        case 11:
            cout << "11 - Листопад - Осінній місяць\n";
            break;
        case 12:
            cout << "12 - Грудень - Зимовий місяць\n";
            break;
        default:
            cout << "Error\n";
            break;
        }
    }
    int sum = 0;
};

Counter operator + (Counter num1, Counter num2) {
    return Counter(num1.sum + num2.sum);
}

Counter operator - (Counter num1, Counter num2) {
    return Counter(num1.sum - num2.sum);
}

int main() {
    Counter c1, c2, c3;
    char temp;

    while (true) {
        cout << "Select + or -: "; cin >> temp;
        
        cout << "Write num #1: "; cin >> c1.sum;
        cout << "Write num #2: "; cin >> c2.sum;

        if (temp == '+')
            c3 = c1 + c2;
        else if (temp == '-')
            c3 = c1 - c2;
        
        c3.ShowNum();
    }

	return 0;
}

/*
Написати програму з перевантаженням операторів для переліків, яка би визначала
пору року на основі доданих або віднятих місяців.
Наприклад. Серпень — це літній місяць. Додамо дев’ять місяців, настане травень —
весняний місяць. Віднімемо тринадцять місяців — був квітень, весняний місяць.
*/
