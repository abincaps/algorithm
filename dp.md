# 状态规划
# AcWing 278.数字组合
`
#include <iostream>
using namespace std;

const int N = 110;
const int M = 10010;

int w[N];
int dp[M][M];
int res;

int main(void)
{
    int n, m;

    cin >> n >> m;

    for (int i = 1; i <= n; i++)
        cin >> w[i];
    
    for (int i = 1; i <= n; i++)
    {
        for (int j = 0; j <= m; j++)
        {
            dp[i][j] = dp[i - 1][j];
            if (w[i] <= j)
                dp[i][j] += dp[i - 1][j - w[i]];
        }

    }

    cout << dp[n][m] << endl;

    return 0;
}
`
