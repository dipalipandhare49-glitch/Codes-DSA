#include <iostream>
using namespace std;

int main()
{
    int n;
    float salary[100], a[100], b[100];

    cout << "Enter number of employees: ";
    cin >> n;

    for (int i = 0; i < n; i++)
    {
        cout << "Enter salary: ";
        cin >> salary[i];

        a[i] = salary[i];
        b[i] = salary[i];
    }

    // Selection Sort
    for (int i = 0; i < n - 1; i++)
    {
        int minIndex = i;

        for (int j = i + 1; j < n; j++)
        {
            if (a[j] < a[minIndex])
                minIndex = j;
        }

        swap(a[i], a[minIndex]);
    }

    cout << "\nSelection Sort:\n";

    for (int i = 0; i < n; i++)
        cout << a[i] << " ";

    // Bubble Sort
    for (int i = 0; i < n - 1; i++)
    {
        for (int j = 0; j < n - i - 1; j++)
        {
            if (b[j] > b[j + 1])
                swap(b[j], b[j + 1]);
        }
    }

    cout << "\n\nBubble Sort:\n";

    for (int i = 0; i < n; i++)
        cout << b[i] << " ";

    // Top Five Highest Salaries
    cout << "\n\nTop Five Highest Salaries:\n";

    for (int i = n - 1; i >= 0 && i >= n - 5; i--)
        cout << b[i] << endl;

    return 0;
}
