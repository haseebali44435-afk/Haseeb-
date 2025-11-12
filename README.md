
#include <iostream>
#include <cmath>
using namespace std;

int main() {
    double a, b, result;
    char op, again;

    cout << "=== Simple Calculator ==="<<endl;
    cout << "Operations: +  -  *  /  ^  s(sqrt of a)  %"<<endl;

    do {
        cout << "\nEnter first number: ";
        cin >> a;

        cout << "Enter operation: ";
        cin >> op;

        if (op == 's') {
            if (a < 0) cout << "Error: Negative number."<<endl;
            else cout << "sqrt(" << a << ") = " << sqrt(a) << endl;
        } else {
            cout << "Enter second number: ";
            cin >> b;

            if (op == '+') result = a + b;
            else if (op == '-') result = a - b;
            else if (op == '*') result = a * b;
            else if (op == '/') result = (b == 0) ? NAN : a / b;
            else if (op == '^') result = pow(a, b);
            else if (op == '%') result = fmod(a, b);
            else { cout << "Invalid operation.\n"; continue; }

            if (op == '/' && b == 0)
                cout << "Error: Division by zero."<<endl;
            else if (op == '%' && b == 0)
                cout << "Error: Modulo by zero."<<endl;
            else
     cout << a << " " << op << " " << b << " = " << result << endl;
        }

        cout << "Do another Enter (y) and Exit (n) ? (y/n): ";
        cin >> again;
    } while (again == 'y' || again == 'Y');

    cout << "Goodbye."<<endl;
    return 0;
}
    
