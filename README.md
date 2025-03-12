#include <iostream>
#include <vector>

class Person {
private:
    std::string name;
    int age;

public:
    Person(std::string name, int age) : name(name), age(age) {}

    std::string getName() const {
        return name;
    }

    int getAge() const {
        return age;
    }
};

int main() {
    std::vector<Person> people;

    for (int i = 0; i < 10; ++i) {
        std::string name;
        int age;

        std::cout << "Enter name for person " << i + 1 << ": ";
        std::cin >> name;

        std::cout << "Enter age for person " << i + 1 << ": ";
        std::cin >> age;

        people.emplace_back(name, age);
    }

    double totalAge = 0;
    for (const auto& person : people) {
        totalAge += person.getAge();
    }
    double averageAge = totalAge / people.size();

    std::cout << "Average age of 10 people: " << averageAge << std::endl;

    return 0;
}