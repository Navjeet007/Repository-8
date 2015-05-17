# Repository-8
Create class SavingsAccount. Use a static variable annualInterestRate to store the annual interest rate for all account holders. Each object of the class contains a private instance variable savingsBalance indicating the amount the saver currently has on deposit. Provide method calculateMonthlyInterest to calculate the monthly interest by multiplying the savingsBalance by annualInterestRate divided by 12—this interest should be added to savings- Balance. Provide a static method modifyInterestRate that sets the annualInterestRate to a new value. Write a program to test class SavingsAccount. Instantiate two savingsAccount objects, saver1 and saver2, with balances of $2000.00 and $3000.00, respectively. Set annualInterestRate to 4%, then calculate the monthly interest for each of 12 months and print the new balances for both savers. Next, set the annualInterestRate to 5%, calculate the next month’s interest and print the new balances for both savers.

public class SavingsAccount 
{
	private static double annualInterestRate;
	private  double savingsBalance;
	public SavingsAccount(double savingsB)
	{
		savingsBalance=savingsB;
	}
	public void setSavingsBalance(double TotalSavingAmount) 
	{
		savingsBalance=TotalSavingAmount;
	}
	public void calculateMonthlyInterest()
	{
		double MonthlyInterest=savingsBalance*(annualInterestRate/12);
		savingsBalance+=MonthlyInterest;
	}
	public static void modifyInterestRate(double newRate)
	{
		annualInterestRate=newRate;
	}
	 public String toString()
	 {
	    return String.format("$%.2f",savingsBalance);
	 }
}
// Test program
public class SavingsAccountTest 
{
	   public static void main(String args[])
	   {	   
	      SavingsAccount saver1=new SavingsAccount(2000.00);
	      SavingsAccount saver2=new SavingsAccount(3000.00);
	      
	      SavingsAccount.modifyInterestRate(0.04);
	      System.out.println("Balances with interest 0.04");
	      System.out.printf("%29s%20s\n","Account 1","Account 2");
	      System.out.printf("Base");
	      System.out.printf("%25s",saver1.toString());
	      System.out.printf("%20s",saver2.toString());
	      
	      for(int m=1;m<=12;m++)
	      {
	        System.out.printf("\nMonth: %02d",m); 
	        saver1.calculateMonthlyInterest();
	        saver2.calculateMonthlyInterest();
	        System.out.printf("%20s%20s",saver1.toString(),saver2.toString());
	      }
	 
	      SavingsAccount.modifyInterestRate(0.05);
	      saver1.setSavingsBalance(2000.00);
	      saver2.setSavingsBalance(3000.00);
	      System.out.println();
	      System.out.println("\nBalances with interest 0.05");
	      System.out.printf("%29s%20s\n","Account 1","Account 2");
	      System.out.printf("Base");
	      System.out.printf("%25s",saver1.toString());
	      System.out.printf("%20s",saver2.toString());
	      
	      for(int m=1;m<=12;m++)
	      {
	        System.out.printf("\nMonth: %02d",m); 
	        saver1.calculateMonthlyInterest();
	        saver2.calculateMonthlyInterest();
	        System.out.printf("%20s%20s",saver1.toString(),saver2.toString());
	      }
	   }
	      
}
