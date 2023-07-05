#include <stdio.h>

// Функція для знаходження найбільшого спільного дільника (НСД)
int gcd(int a, int b) {
    if (b == 0)
        return a;
    return gcd(b, a % b);
}

// Функція для знаходження найменшого спільного кратного (НСК)
int lcm(int a, int b) {
    return (a * b) / gcd(a, b);
}

int main() {
    int r;
    printf("Введіть кількість чисел: ");
    scanf("%d", &r);

    int numbers[r];
    printf("Введіть числа, розділені пробілом: ");
    for (int i = 0; i < r; i++) {
        scanf("%d", &numbers[i]);
    }

    // Ініціалізація НСК з першого числа
    int result = numbers[0];

    // Обчислення НСК для решти чисел
    for (int i = 1; i < r; i++) {
        result = lcm(result, numbers[i]);
    }

    printf("Найменше спільне кратне: %d\n", result);

    return 0;
}
