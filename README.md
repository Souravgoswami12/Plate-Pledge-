#include <iostream>
#include <vector>
#include <string>
#include <algorithm>

using namespace std;

// Struct to represent food items
struct FoodItem {
    string name;
    int quantity;
};

// Function to add a food item to the list
void addFoodItem(vector<FoodItem> &foodList) {
    string name;
    int quantity;
    cout << "Enter food name: ";
    cin >> name;
    cout << "Enter quantity: ";
    cin >> quantity;
    foodList.push_back({name, quantity});
}

// Function to display all food items
void displayFoodItems(const vector<FoodItem> &foodList) {
    cout << "Food items:\n";
    for (const auto &item : foodList) {
        cout << item.name << ": " << item.quantity << " units\n";
    }
}

// Function to calculate total quantity of food items
int totalFoodQuantity(const vector<FoodItem> &foodList) {
    int total = 0;
    for (const auto &item : foodList) {
        total += item.quantity;
    }
    return total;
}

int main() {
    vector<FoodItem> foodList;
    char choice;
    
    do {
        cout << "1. Add Food Item\n";
        cout << "2. View Food Items\n";
        cout << "3. View Total Food Quantity\n";
        cout << "4. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;
        
        switch (choice) {
            case '1':
                addFoodItem(foodList);
                break;
            case '2':
                displayFoodItems(foodList);
                break;
            case '3':
                cout << "Total food quantity: " << totalFoodQuantity(foodList) << " units\n";
                break;
            case '4':
                cout << "Exiting...\n";
                break;
            default:
                cout << "Invalid choice. Please try again.\n";
        }
    } while (choice != '4');

    return 0;
}
