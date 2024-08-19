# CT2
GroceryBills
package GroceryBills;
import java.util.Scanner;

public class GroceryBills {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        // Prompt user to enter the coupon amount
        System.out.print("Enter the coupon amount (as a decimal, e.g., 0.10): ");
        double couponAmount = scanner.nextDouble();
        
        // Validate coupon amount to ensure it's between 0 and 1 (10% if out of range)
        if (couponAmount > 1.0 || couponAmount <= 0.0) {
            couponAmount = 0.10;
        }
        
        // Initialize variables for grocery bills
        double totalGroceryBill = 0.0;
        int numberOfWeeks = 4;
        
        // Prompt user for weekly grocery bills
        System.out.print("Enter Grocery Bill for week: ");
        double weeklyBill = scanner.nextDouble();
        
        // Accumulate weekly bills until a non-positive value is entered
        while (weeklyBill > 0) {
            totalGroceryBill += weeklyBill;
            System.out.print("Enter Grocery Bill for week (input 0 or negative to stop): ");
            weeklyBill = scanner.nextDouble();
        }
        
        // Calculate the monthly total and weekly average without the coupon
        double weeklyAverageWithoutCoupon = totalGroceryBill / numberOfWeeks;
        double monthlyTotalWithoutCoupon = totalGroceryBill;
        
        // Calculate the monthly total and weekly average with the coupon
        double discountAmount = totalGroceryBill * couponAmount;
        double monthlyTotalWithCoupon = totalGroceryBill - discountAmount;
        double weeklyAverageWithCoupon = monthlyTotalWithCoupon / numberOfWeeks;
        
        // Display the results
        System.out.println("Monthly grocery bill total without coupon: $" + monthlyTotalWithoutCoupon);
        System.out.println("Weekly grocery bill average without coupon: $" + weeklyAverageWithoutCoupon);
        System.out.println("Monthly grocery bill total with coupon: $" + monthlyTotalWithCoupon);
        System.out.println("Weekly grocery bill average with coupon: $" + weeklyAverageWithCoupon);
        
        scanner.close();
    }
}
