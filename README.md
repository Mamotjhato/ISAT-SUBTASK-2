//0506060564081

#include <iostream>
#include <string>
#include <cstdlib>
#include <ctime>
using namespace std;

// Decimal to Binary
string decimalToBinary(int num) {
    if (num == 0) return "0";
    bool negative = num < 0;
    num = abs(num);

    string result = "";
    while (num > 0) {
        result = char((num % 2) + '0') + result;
        num /= 2;
    }
    if (negative) result = "-" + result;
    return result;
}


