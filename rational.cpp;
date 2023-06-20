#include <iostream>
#include <algorithm>
using namespace std;

class rational 
{
    friend ostream& operator<<(ostream& out, rational& robj);
    friend istream& operator>>(istream& in, rational& robj);
public:
    rational(int n = 0, int d = 1);
    rational operator+(const rational& r2) const;
    rational operator-(const rational& r2) const;
    rational operator*(const rational& r2) const;
    rational operator/(const rational& r2) const;
    bool operator>(const rational& r2) const;
    int GCD();
private:
    int num;
    int denom;
};

int fillArray(rational r[], int capacity);
void displayArray(rational r[], int n);
void sortArray(rational r[], int n);

int main() {
    const int SIZE = 5;
    rational array[SIZE];
    int n = fillArray(array, SIZE);
    displayArray(array, n);
    sortArray(array, n);
    displayArray(array, n);
    return 0;
}

rational::rational(int n, int d) {
    num = n;
    denom = d;
}

rational rational::operator+(const rational& r2) const {
    int n = num * r2.denom + denom * r2.num;
    int d = denom * r2.denom;
    return rational(n, d);
}

rational rational::operator-(const rational& r2) const {
    int n = num * r2.denom - denom * r2.num;
    int d = denom * r2.denom;
    return rational(n, d);
}

rational rational::operator*(const rational& r2) const {
    int n = num * r2.num;
    int d = denom * r2.denom;
    return rational(n, d);
}

rational rational::operator/(const rational& r2) const {
    int n = num * r2.denom;
    int d = denom * r2.num;
    return rational(n, d);
}

bool rational::operator>(const rational& r2) const {
    return num * r2.denom > r2.num * denom;
}

ostream& operator<<(ostream& out, rational& robj) {
    int gcd = robj.GCD();
    out << robj.num/gcd << "/" << robj.denom/gcd;
    return out;
}

istream& operator>>(istream& in, rational& robj) {
    cout << "Enter numerator: ";
    in >> robj.num;
    cout << "Enter denominator: ";
    in >> robj.denom;
    return in;
}

int rational::GCD() {
    int a = num;
    int b = denom;
    while (b != 0) {
        int temp = b;
        b = a % b;
        a = temp;
    }
    return a;
}

int fillArray(rational r[], int capacity) {
    int n;
    cout << "How many rational numbers do you want to enter? (up to " << capacity << ")\n";
    cin >> n;
    if (n > capacity) {
        n = capacity;
    }
    for (int i = 0; i < n; i++) {
        cin >> r[i];
    }
    return n;
}

void displayArray(rational r[], int n) {
    for (int i = 0; i < n; i++) {
        cout << r[i] << " ";
    }
    cout << endl;
}

void sortArray(rational r[], int n) {
    sort(r, r+n, greater<rational>());
}
