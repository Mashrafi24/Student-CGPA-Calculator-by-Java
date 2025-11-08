# Student-CGPA-Calculator-by-Java

import java.util.Scanner;

public class StudentCGPACalculator {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

     
        System.out.print("Enter Student ID: ");
        String studentID = sc.nextLine();

     
        System.out.print("Enter Number of Courses: ");
        int n = sc.nextInt();

        double totalCredit = 0;
        double totalWeightedCGPA = 0;


        for (int i = 1; i <= n; i++) {
            System.out.println("\nCourse " + i + ":");

            System.out.print("Enter Credit (Max 3): ");
            double credit = sc.nextDouble();

            System.out.print("Enter Class Test (CT out of 30): ");
            double ct = sc.nextDouble();

            System.out.print("Enter Attendance (AT out of 10): ");
            double at = sc.nextDouble();

            System.out.print("Enter Final Exam (FE out of 60): ");
            double fe = sc.nextDouble();

            double totalMarks = ct + at + fe; 
            double cgpa = 0;

           
            if (totalMarks >= 80)
                cgpa = 4.00;
            else if (totalMarks >= 75)
                cgpa = 3.75;
            else if (totalMarks >= 70)
                cgpa = 3.50;
            else if (totalMarks >= 65)
                cgpa = 3.25;
            else if (totalMarks >= 60)
                cgpa = 3.00;
            else if (totalMarks >= 55)
                cgpa = 2.75;
            else if (totalMarks >= 50)
                cgpa = 2.50;
            else if (totalMarks >= 45)
               cgpa = 2.25;
            else if (totalMarks >= 40)
                cgpa = 2.00;
            else
                cgpa = 0.00; // Fail

            totalCredit += credit;
            totalWeightedCGPA += cgpa * credit;
        }

       
        double cgpa = totalWeightedGPA / totalCredit;


        String grade;
        if (cgpa >= 4.00)
            grade = "A+";
        else if (cgpa >= 3.75)
            grade = "A";
        else if (cgpa >= 3.50)
            grade = "A-";
        else if (cgpa >= 3.25)
            grade = "B+";
        else if (cgpa >= 3.00)
            grade = "B";
        else if (cgpa >= 2.75)
            grade = "B-";
        else if (cgpa >= 2.50)
            grade = "C+";
        else if (cgpa >= 2.25)
            grade = "C";
        else if (cgpa >= 2.00)
            grade = "D";
        else
            grade = "F (Fail)";


        System.out.println("\n------------------------------------");
        System.out.println("Student ID: " + studentID);
        System.out.println("Credit Taken: " + totalCredit);
        System.out.println("Credit Earned: " + totalCredit);
        System.out.printf("CGPA: %.2f\n", cgpa);
        System.out.println("Grade: " + grade);
       
        sc.close();
    }
}
