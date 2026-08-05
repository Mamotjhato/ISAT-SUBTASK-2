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

// Binary to Decimal
int binaryToDecimal(string s) {
    bool negative = false;
    if (!s.empty() && s[0] == '-') {
        negative = true;
        s = s.substr(1);
    }
    int value = 0;
    for (char c : s) {
        if (c != '0' && c != '1') {
            cout << "Invalid binary number\n";
            return 0;
        }
        value = value * 2 + (c - '0');
    }
    return negative ? -value : value;
}

// Decimal to Hexadecimal
string decimalToHex(int num) {
    if (num == 0) return "0";
    string hexMap = "0123456789ABCDEF";
    bool negative = num < 0;
    num = abs(num);

    string result = "";
    while (num > 0) {
        result = hexMap[num % 16] + result;
        num /= 16;
    }
    if (negative) result = "-" + result;
    return result;
}


