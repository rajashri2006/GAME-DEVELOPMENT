## EX 1: DDA ALGORITHM 

**Aim :**

To  implement the DDA algorithm to draw a line using a c coding

**Algorithms :**

Step 1 − Get the input of two end points (X0,Y0) and (X1,Y1)

Step 2 − Calculate the difference between two end points dx and  dy 

Step 3 − If dx > dy, then you need more steps in x coordinate; otherwise in y coordinate.

Step 4 − Calculate the increment in x coordinate and y coordinate

Step 5 − Plot the pixel by successfully incrementing x and y coordinates accordingly and complete the drawing of the line

**Program :**

```
#include <graphics.h>
#include <conio.h>
#include <dos.h>
#include <math.h>
#include <stdio.h>   

void DDA(int x1, int y1, int x2, int y2) {
    float dx, dy, steps;
    float x, y, xInc, yInc;
    int i;

    dx = x2 - x1;
    dy = y2 - y1;

    steps = (fabs(dx) > fabs(dy)) ? fabs(dx) : fabs(dy);

    xInc = dx / steps;
    yInc = dy / steps;

    x = x1;
    y = y1;

    for (i = 0; i <= steps; i++) {
        putpixel((int)(x + 0.5), (int)(y + 0.5), WHITE);
        x += xInc;
        y += yInc;
        delay(10);  
    }
}

int main() {
    int gd = DETECT, gm;
    int x1, y1, x2, y2;

   
    initgraph(&gd, &gm, "C:\\TURBOC3\\BGI"); 

    printf("Register Number:212224040261");
    printf("Name : RAJASHRI");
    printf("Enter x1, y1: ");
    scanf("%d %d", &x1, &y1);

    printf("Enter x2, y2: ");
    scanf("%d %d", &x2, &y2);

    
    DDA(x1, y1, x2, y2);

    getch();         
    closegraph();    

    return 0;
}
```

**Output :**

<img width="571" height="363" alt="image" src="https://github.com/user-attachments/assets/839f5a42-42d5-4df0-b4da-25cff800c77c" />


**Result :**

Thus, the implementation of  DDA algorithm to draw a line using a c coding is executed successfully.
