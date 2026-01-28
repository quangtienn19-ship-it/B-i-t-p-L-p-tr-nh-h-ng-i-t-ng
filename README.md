#include <iostream>
#include <vector>
#include <string>
#include <iomanip>

using namespace std;

// --- 1. Tính Đóng Gói (Encapsulation) ---
class Person {
protected:
    string name;
    int age;
public:
    Person(string n = "", int a = 0) : name(n), age(a) {}
    virtual void display() {
        cout << "Ten: " << left << setw(20) << name << " | Tuoi: " << age;
    }
};

// --- 2. Tính Kế Thừa (Inheritance) ---
class Student : public Person {
private:
    string studentID;
    float gpa;
public:
    Student(string n, int a, string id, float score) 
        : Person(n, a), studentID(id), gpa(score) {}

    // --- 3. Tính Đa Hình (Polymorphism) ---
    void display() override {
        Person::display();
        cout << " | MSSV: " << setw(10) << studentID << " | GPA: " << gpa << endl;
    }

    string getID() { return studentID; }
};

class StudentManager {
private:
    vector<Student> list;
public:
    void addStudent() {
        string name, id;
        int age;
        float gpa;
        
        cout << "Nhap ten: "; cin.ignore(); getline(cin, name);
        cout << "Nhap tuoi: "; cin >> age;
        cout << "Nhap MSSV: "; cin >> id;
        cout << "Nhap GPA: "; cin >> gpa;

        list.push_back(Student(name, age, id, gpa));
        cout << "=> Them thanh cong!\n";
    }

    void showList() {
        cout << "\n--- DANH SACH SINH VIEN ---\n";
        for (auto &s : list) {
            s.display();
        }
    }
};

int main() {
    StudentManager sm;
    int choice;

    do {
        cout << "\n1. Them sinh vien\n2. Hien thi danh sach\n0. Thoat\nChon: ";
        cin >> choice;

        switch (choice) {
            case 1: sm.addStudent(); break;
            case 2: sm.showList(); break;
        }
    } while (choice != 0);

    return 0;
}
