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
// Hexadecimal to Decimal
int hexToDecimal(string s) {
    string hexMap = "0123456789ABCDEF";
    bool negative = false;
    if (!s.empty() && s[0] == '-') {
        negative = true;
        s = s.substr(1);
    }
    for (char &c : s) c = toupper(c);

    int value = 0;
    for (char c : s) {
        int digit = hexMap.find(c);
        if (digit == string::npos) {
            cout << "Invalid hex number\n";
            return 0;
        }
        value = value * 16 + digit;
    }
    return negative ? -value : value;
}

void showMenu() {
    cout << "\n--- MENU ---\n";
    cout << "1. Decimal to Binary\n";
    cout << "2. Binary to Decimal\n";
    cout << "3. Hexadecimal to Decimal\n";
    cout << "4. Decimal to Hexadecimal\n";
    cout << "5. Demo (random number)\n";
    cout << "6. Exit\n";
}

void demo() {
    int n = rand() % 100;
    cout << "Random number: " << n << "\n";
    cout << "Binary: " << decimalToBinary(n) << "\n";
    cout << "Hex: " << decimalToHex(n) << "\n";
}

    value = value * 16 + digit;
    }
    return negative ? -value : value;
}

void showMenu() {
    cout << "\n--- MENU ---\n";
    cout << "1. Decimal to Binary\n";
    cout << "2. Binary to Decimal\n";
    cout << "3. Hexadecimal to Decimal\n";
    cout << "4. Decimal to Hexadecimal\n";
    cout << "5. Demo (random number)\n";
    cout << "6. Exit\n";
}

void demo() {
    int n = rand() % 100;
    cout << "Random number: " << n << "\n";
    cout << "Binary: " << decimalToBinary(n) << "\n";
    cout << "Hex: " << decimalToHex(n) << "\n";
}

int main() {
    srand(time(0));
    cout << "Welcome to the converter!\n";

    while (true) {
        showMenu();
        int choice;
        cout << "Enter choice (1-6): ";
        cin >> choice;

        if (choice == 1) {
            int n; cout << "Enter decimal: "; cin >> n;
            cout << "Binary: " << decimalToBinary(n) << "\n";
        } else if (choice == 2) {
            string s; cout << "Enter binary: "; cin >> s;
            cout << "Decimal: " << binaryToDecimal(s) << "\n";
        } else if (choice == 3) {
            string s; cout << "Enter hex: "; cin >> s;
            cout << "Decimal: " << hexToDecimal(s) << "\n";
        } else if (choice == 4) {
            int n; cout << "Enter decimal: "; cin >> n;
            cout << "Hex: " << decimalToHex(n) << "\n";
        } else if (choice == 5) {
            demo();
        } else if (choice == 6) {
            cout << "Goodbye!\n";
            break;
        } else {
            cout << "Invalid choice\n";
        }
    }
    return 0;
}


