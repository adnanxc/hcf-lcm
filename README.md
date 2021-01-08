# hcf-lcm
 Write a C++ code with functions “hcf()” and “lcm()” which takes two arguments and return Highest Common factor and Least Common Multiple.


#include <iostream>
using namespace std;

int hcf(int a , int b){
    int x , y , j;

    if (a<0){a = -a;}
    if (b<0){b = -b;}

    if (a==0){j = b;}
    else if (b==0){j = a;}

    else{

        while (b != 0){

        x = b;
        b = a % b;
        a = x;
        }

        j = x;

    }
    return j;
}


int lcm(int a , int b){
    int i , flag = 0;
    if(a<0) {a = -a;}
    if(b<0) {b = -b;}

    if(a==0 || b==0){
        return 0;
    }
    else{
        i = b;
        while(flag==0){
            if(i%a==0 && i%b==0){
                flag = 1;
            }
            i++;
        }
    return i-1;
    }
}


int main(){

    int a , b , temp;
    cout << "Enter the first number: ";
    cin >> a;
    cout << "Enter the second number: ";
    cin >> b;
    if(a > b){
        temp = a;
        a = b;
        b = temp;
    }
    int h = hcf(a , b);
    int l = lcm(a , b);
    cout << "Highest Common Factor: " << h << endl;
    cout << "Lowest Common Multiple: " << l;
    return 0;

}
