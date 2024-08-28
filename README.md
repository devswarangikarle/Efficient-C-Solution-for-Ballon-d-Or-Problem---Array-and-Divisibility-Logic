# Efficient-C-Solution-for-Ballon-d-Or-Problem---Array-and-Divisibility-Logic

Gaurav has already won the Ballon d'Or 8 times, so he is really impressed with it (is he?).
Gaurav has an array A containing N integers. Each element of this array is either 1 or 2. He wants to figure out if the product of all the elements of the array can be written as an 8-th power of some integer, i.e, k8 for some integer k.
Print Yes if it can and No if it can't.

Constraints
1 ≤ T ≤ 105
1 ≤ N ≤ 2x105
1 ≤ Ai ≤ 2


#include <iostream>
#include <vector>
using namespace std;

void can_be_eighth_power(int T, const vector<vector<int>>& test_cases) {
    for (int i = 0; i < T; ++i) {
        int N = test_cases[i][0];
        const vector<int>& A = test_cases[i];
        int count_2s = 0;

        // Count the number of 2s in the array
        for (int j = 1; j <= N; ++j) {
            if (A[j] == 2) {
                count_2s++;
            }
        }

        // Check if the count of 2s is divisible by 8
        if (count_2s % 8 == 0) {
            cout << "Yes" << endl;
        } else {
            cout << "No" << endl;
        }
    }
}

int main() {
    int T;
    cin >> T;
    
    vector<vector<int>> test_cases(T);

    for (int i = 0; i < T; ++i) {
        int N;
        cin >> N;
        test_cases[i].resize(N + 1);
        test_cases[i][0] = N;
        for (int j = 1; j <= N; ++j) {
            cin >> test_cases[i][j];
        }
    }

    can_be_eighth_power(T, test_cases);

    return 0;
}
