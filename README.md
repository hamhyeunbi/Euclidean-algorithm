# Euclidean-algorithm
유클리드 재귀, 반복적 최대공약수 알고리즘

//재귀적 알고리즘//

#include <stdio.h>

int gcd(int x, int y)
{
    if (y == 0)
        return x;
    else
        return gcd(y, (x % y));
}

int main(void)
{
    int a, b, big, small;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    if (a < b) {
        big = b;
        small = a;
    }

    else {
        big = a;
        small = b;
    }

    printf("%d와 %d의 최대공약수는 %d\n", a, b, gcd(big, small));
}

//반복적 알고리즘//

#include <stdio.h>

int gcd(int x, int y)
{
    int tmp, n;
    if (x < y) {
        tmp = x;
        x = y;
        y = tmp;
    }
    while (y != 0) {
        n = x % y;
        x = y;
        y = n;
    }
    return x;
}
int main(void)
{
    int a, b, big, small;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    if (a < b) {
        big = b;
        small = a;
    }

    else {
        big = a;
        small = b;
    }
    printf("%d와 %d의 최대공약수는 %d\n", a, b, gcd(big, small));
}
