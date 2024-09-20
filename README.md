#include <stdio.h>
#include <stdlib.h>
#include <time.h>
int stonepaperscissor(int you, int comp)
{
    if (you == comp)
    {
        return 0;
    }
    if (you == 's' && comp == 'p')
    {
        return 1;
    }
    else if (you == 'p' && comp == 's')
    {
        return -1;
    }
    if (you == 's' && comp == 'c')
    {
        return 1;
    }
    else if (you == 'c' && comp == 's')
    {
        return -1;
    }
    if (you == 'p' && comp == 'c')
    {
        return 1;
    }
    else if (you == 'c' && comp == 'p')
    {
        return -1;
    }
}
int main()
{
    char you, comp;
    int number;
    srand(time(0));
    number = rand() % 100 + 1;
    if (number < 33)
    {
        comp = 's';
    }
    else if (number > 33 && number < 66)
    {
        comp = 'p';
    }
    else
    {
        comp = 'c';
    }
    printf("'s' for stone, 'p' for paper, 'c' for scissor.\t");
    scanf("%c", &you);
    printf("you choose %c and computer choose %c \n", you, comp);
    int result = stonepaperscissor(you, comp);
    if (result == 1)
    {
        printf("congratulations! YOU WON THE GAME");
    }
    else if (result == 0)
    {
        printf("Draw game! \n");
    }
    else
    {
        printf("YOU LOSE THE GAME. \n");
    }
    return 0;
}
