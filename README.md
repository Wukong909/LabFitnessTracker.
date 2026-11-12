# Employee Salary Calculator.

import java.util.Scanner;


class Employee {
    public double calculateSalary() {
        return 0.0;
    }
}


class FullTimeEmployee extends Employee {
    double basePay;
    double bonus;

    public FullTimeEmployee(double basePay, double bonus) {
        this.basePay = basePay;
        this.bonus = bonus;
    }

    @Override
    public double calculateSalary() {
        return basePay + bonus;
    }
}

// Child Class 2
class PartTimeEmployee extends Employee {
    double hourlyRate;
    double hoursWorked;

    public PartTimeEmployee(double hourlyRate, double hoursWorked) {
        this.hourlyRate = hourlyRate;
        this.hoursWorked = hoursWorked;
    }

    @Override
    public double calculateSalary() {
        return hourlyRate * hoursWorked;
    }
}

// Main Class
public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        for (int i = 0; i < 2; i++) {
            System.out.print("Enter employee type (full-time / part-time): ");
            String type = input.nextLine();

            Employee employee;

            if (type.equalsIgnoreCase("full-time")) {
                System.out.print("Enter base pay: ");
                double basePay = input.nextDouble();

                System.out.print("Enter bonus: ");
                double bonus = input.nextDouble();

                employee = new FullTimeEmployee(basePay, bonus);

            } else if (type.equalsIgnoreCase("part-time")) {
                System.out.print("Enter hourly rate: ");
                double hourlyRate = input.nextDouble();

                System.out.print("Enter hours worked: ");
                double hoursWorked = input.nextDouble();

                employee = new PartTimeEmployee(hourlyRate, hoursWorked);

            } else {
                System.out.println("Invalid employee type.");
                input.nextLine();
                continue;
            }

            System.out.println("Monthly Salary: $" +
                    employee.calculateSalary());

            input.nextLine();
            System.out.println();
        }

        input.close();
    }
}

## Code Review
- **Reviewed by:** [Alex Lam]
- **Status:** Checked code. Inheritance (`extends`), Scanner input, and salary calculations are all correct and working!
