# Tax
import javax.swing.JOptionPane;
public class Program_5_3
{
	public static void main(String[] args)
	{
		String input;
		String income;
		double income1 = 0;
		double tax = 0;
		
	final double tax_rate1 = 0.10;
	final double tax_rate2 = 0.15;
	final double tax_rate3 = 0.25;
	
	final double single_mrl = 8000;
	final double single_trl = 32000;
	final double single_mb = 800;
	final double single_hb = 4400;
	final double married_mrl = 16000;
	final double married_trl = 64000;
	final double married_mb = 1600;
	final double married_hb = 8800;
	boolean quit = false;

	while(!quit)
	{ 
		input = JOptionPane.showInputDialog("Enter s for single, m for married" + "; or q for quit:");
		while( !((input.equals("s")) || (input.equals("m")) || (input.equals("q"))))
		{
				input = JOptionPane.showInputDialog("Data Entry Error-Please enter s for single, m for married; or q for quit:");
		}
			if ((input.equals("s")) || (input.equals("m")))	
			{
		income = JOptionPane.showInputDialog("Please enter your income: ");
		income1 = Double.parseDouble(income);
		
		if (input.equals("s"))
		{
			if (income1 <= single_mrl)
				tax = income1 * tax_rate1;
			else if (income1 <= single_trl)
			tax = single_mb + (tax_rate2 * (income1 - single_mrl));
			else
				tax = single_hb + (tax_rate3 * (income1 - single_trl));
		}
		else
		{
			if (income1 <= married_mrl)
				tax = income1 * tax_rate1;
			else if (income1 <= married_trl)
				tax = married_mb + (tax_rate2 * (income1 - married_mrl));
			else 
				tax = married_hb + (tax_rate3 * (income1 - married_trl));
		}
	}
	else
	 quit = true;
	
	if(!quit)
	JOptionPane.showMessageDialog(null, String.format("Your tax is $%.2f",  tax));
	}
	}
}
	
