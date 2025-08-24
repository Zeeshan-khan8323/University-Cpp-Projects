#include <iostream>
#include <fstream>
#include <string>
#include <ctime> 

using namespace std;


const int MAX_ITEMS = 100;
int itemCount = 0;
int itemIDs[MAX_ITEMS];
string itemNames[MAX_ITEMS];

int itemQuantities[MAX_ITEMS];
float itemPrices[MAX_ITEMS];

void addItem();
void displayInventory();
void saveInventoryToFile();

int main() {
    char choice;
    time_t currentTime = time(0);
        char* dt = ctime(&currentTime); 
        cout << "Current Time: " << dt << endl;;
    
    do {
        cout << "Inventory Management System" << endl;
        cout << "1. Add new item" << endl;
        cout << "2. Display inventory" << endl;
        cout << "3. Save inventory to file" << endl;
        cout << "4. Exit" << endl;
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case '1':
                addItem();
                break;
            case '2':
                displayInventory();
                break;
            case '3':
                saveInventoryToFile();
                break;
            case '4':
                cout << "Exiting program. Goodbye!" << endl;
                break;
            default:
                cout << "Invalid choice. Please try again." << endl;
        }
    } while (choice != '4');
   
    return 0;
}

void addItem() {
    if (itemCount < MAX_ITEMS) {
        cout << "Enter item details:" << endl;
        cout << "ID: ";
        cin >> itemIDs[itemCount];
        cout << "Name: ";
        cin >> itemNames[itemCount];
        cout << "Quantity: ";
        cin >> itemQuantities[itemCount];
        cout << "Price: ";
        cin >> itemPrices[itemCount];
        itemCount++;
    } else {
        cout << "Inventory is full. Cannot add more items." << endl;
    }
}

void displayInventory() {
    if (itemCount == 0) {
        cout << "Inventory is empty." << endl;
    } else {
        cout << "Inventory:" << endl;
        for (int i = 0; i < itemCount; i++) {
            cout << "ID: " << itemIDs[i] << ", Name: " << itemNames[i] << ", Quantity: " << itemQuantities[i] 
			<< ", Price: $" << itemPrices[i] << endl;
        }
    }
}


void saveInventoryToFile() {
    ofstream outFile("inventory.csv");
    if (outFile.is_open()) {
        for (int i = 0; i < itemCount; i++) {
            outFile << "Item ID: "  << itemIDs[i] << endl <<"Item Name: "<< itemNames[i] << endl<<
		 "Item Quantities: "       << itemQuantities[i] << endl << "Item Pricee: "<< itemPrices[i] << endl;
        }
  

        cout << "Inventory saved to file successfully." << endl;
    } else {
        cout << "Error: Unable to open file for writing." << endl; 
    }
    outFile.close();
}
