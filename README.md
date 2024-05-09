#include <iostream>
#include <iomanip>
#include <string>
#include <fstream>

using namespace std;


int BRAND();
int KEYS();
int COLORS();
int PANELS();
int MODE();



int main() {

    string customer_name;
    float date;
    int customers;
    int count;

    cout<< "How many customers are there?" << endl;
    cin>> customers;
    cout << endl;

for(count = 0; count < customers; count++) {

    cout<< "Hello! Welcome to Goode Synthesizers." << endl << endl;

    cout << "What Brand of synthesizer would you like to purchase?" << endl;
    cout << "#1. Korg starts at $500." << endl;
    cout << "#2. Roland starts at $900" << endl;
    cout << "#3. Moog starts at $1100" << endl;
    cout << "#4. Nord starts at $2000" << endl;

    double brand_total;
    brand_total = BRAND();

    cout << "How many keys would you like your synthesizer to have?" << endl;
    cout << "#1.  29 Keys for no extra cost." << endl;
    cout << "#2.  32 Keys for $50 more." << endl;
    cout << "#3.  37 Keys for $75 more." << endl;
    cout << "#4.  44 Keys for $100 more." << endl;
    cout << "#5.  49 Keys for $125 more." << endl;
    cout << "#6.  61 Keys for $150 more." << endl;

    double key_total;
    key_total = KEYS();

    cout << "What color would you like your syntheziser to be?" << endl;
    cout << "#1. Black for no extra cost." << endl;
    cout << "#2. Red for $20 more." << endl;
    cout << "#3. Blue for $20 more." << endl;
    cout << "#4. Grey for $30 more." << endl;

    double color_total;
    color_total = COLORS();

    cout << "What style of side panels would you like?" << endl;
    cout << "#1. Black Plastic for no extra cost." << endl;
    cout << "#2. Acrylic for $30 more." << endl;
    cout << "#3. Wood for $50 more." << endl;

    double panel_total;
    panel_total = PANELS();

    cout << "Would you like an Analog synthesizer or a Digital synthesizer?" << endl;
    cout << "#1. Digital for no extra cost" << endl;
    cout << "#2. Analog for $100 more." << endl;

    double mode_total;
    mode_total = MODE();

    double total;
    double tax;
    double grand_total;

    total = brand_total + key_total + color_total + panel_total + mode_total;
    cout << fixed << showpoint << setprecision(2);

    tax = total * 0.08;
    grand_total = total + tax;

    cout << "Subtotal    $" << total << endl;
    cout << "Tax         $" << tax << endl;
    cout << "Grand Total $" << grand_total << endl << endl;

    cout << "May I have your name so we can add it to our mailing list?" << endl;
    cin >> customer_name;
    cout<< endl;

    ofstream outputFile;
    outputFile.open("name.txt");

    outputFile << customer_name << endl;

    outputFile.close();

    cout<< "would you like a receipt?" << endl;

    int choice;

    cout<< "1. Yes,  #2. No" << endl;
    cin>> choice;

    if (choice == 1){
        ofstream outputFile;
        outputFile.open("numbers.txt");

        outputFile << customer_name << endl;
        outputFile << brand_total << endl;
        outputFile << key_total << endl;
        outputFile << color_total << endl;
        outputFile << panel_total << endl;
        outputFile << mode_total << endl;
        outputFile << total << endl;
        outputFile << tax << endl;
        outputFile << grand_total << endl;

        outputFile.close();
    }
    else
        cout<< "Thank you." << customer_name << endl << endl;

    cout<< "See previous purchase?" << endl;
    cout<< "#1. Yes.   #2. No" << endl;
    int receipt;
    cin>> receipt;

    if (receipt == 1){
        ifstream inputFile;
        inputFile.open("numbers.txt");

        inputFile >> customer_name >> date;
        cout<< customer_name << " made this purchase." << endl;
        inputFile >> brand_total;
        cout<< "Brand        $" << brand_total << endl;
        inputFile >> key_total;
        cout<< "Keys         $" << key_total << endl;
        inputFile >> color_total;
        cout<< "Color        $" << color_total << endl;
        inputFile >> panel_total;
        cout<< "Panels       $" << panel_total << endl;
        inputFile >> mode_total;
        cout<< "Mode         $" << mode_total << endl;
        inputFile >> total;
        cout<< "Total        $" << total << endl;
        inputFile >> tax;
        cout<< "Tax          $" << tax << endl;
        inputFile >> grand_total;
        cout<< "Grand Total  $" << grand_total << endl << endl;

        inputFile.close();
    }
    else
        cout<< "Have a good day!" << endl << endl;
}

    const int Mailing_list = customers;
    int name[Mailing_list];
    int countt;

    for(countt = 0; countt < Mailing_list; countt++) {
        cin >> customer_name[count];
    }

    for(countt =0; countt < Mailing_list; countt++)
        cout << customer_name[count] << endl;



    return 0;
}
int BRAND(){

    int brand;
    double price = 0;
    double brand_total;

    cin >> brand;
    cout<< endl;

    if( brand ) {

        if (brand == 1) {
            cout << "You chose a Korg synthesizer." << endl << endl;
            brand_total = price + 500;
        }
        if (brand == 2) {
            cout << "You chose a Roland synthesizer" << endl << endl;
            brand_total = price + 900;
        }
        if (brand == 3) {
            cout << "You chose a Moog synthesizer." << endl << endl;
            brand_total = price + 1100;
        }
        if (brand == 4) {
            cout << "You chose a Nord synthesizer." << endl << endl;
            brand_total = price + 2000;
        }
    }
    else
        cout<< "You did not pick an appropriate option." << endl;

    return brand_total;
}

int KEYS() {

    int keys;
    double price = 0;
    double key_total;

    cin >> keys;

    if ( keys ) {

        if (keys == 1) {
            cout << "You chose 29 keys." << endl << endl;
            key_total = price;
        }
        if (keys == 2){
            cout << "You chose 32 keys." << endl << endl;
            key_total = price + 50;
        }
        if (keys == 3) {
            cout << "You chose 37 keys." << endl << endl;
            key_total = price + 75;
        }
        if (keys == 4) {
            cout << "You chose 44 keys." << endl << endl;
            key_total = price + 100;
        }
        if (keys == 5) {
            cout << "You chose 49 keys." << endl << endl;
            key_total = price + 125;
        }
        if (keys == 6) {
            cout << "You chose 61 keys." << endl << endl;
            key_total = price + 150;
        }
    }
    else
        cout<< "You did not pick an appropriate option." <<endl;
    return key_total;
}

int COLORS(){

    int color;
    double price =0;
    double color_total;

    cin>> color;

    if (color){

        if (color==1) {
            cout << "You chose black." << endl << endl;
            color_total = price;
        }
        if (color==2){
            cout<< "You chose Red." << endl << endl;
            color_total = price + 20;
        }
        if (color==3){
            cout<< "You chose Blue." << endl << endl;
            color_total = price + 20;
        }
        if (color==4){
            cout<< "You chose Grey." << endl << endl;
            color_total = price + 30;
        }
    }
    else
        cout<< "You did not pick an appropriate option." <<endl;


    return color_total;
}

int PANELS(){

    int panels;
    double price = 0;
    double panel_total;

    cin>> panels;

    if(panels){

        if(panels == 1) {
            cout << "You chose black plastic." << endl << endl;
            panel_total = price;
        }
        if (panels == 2) {
            cout << "You chose Acrylic." << endl << endl;
            panel_total = price + 30;
        }
        if (panels == 3){
            cout<< "You chose Wood." << endl << endl;
            panel_total = price + 50;
        }
    }
    else
        cout<< "You did not pick an appropriate option." << endl;

    return panel_total;
}

int MODE(){

    int mode;
    double price = 0;
    double mode_total;

    cin>> mode;

    if (mode){

        if(mode == 1) {
            cout << "You chose a Digital synthesizer." << endl << endl;
            mode_total = price;
        }
        if (mode == 2){
            cout << "You chose an Analog synthesizer." << endl << endl;
            mode_total = price + 100;
        }
    }
    else
        cout<< "You did not pick an appropriate option." << endl;

    return mode_total;
}
