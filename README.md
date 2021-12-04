package adean4;

import java.util.ArrayList;
import java.util.Scanner;
public class Main {

    public static void main(String[] args) {
	// write your code here
                //creating ArrayLists
                ArrayList<String> products = new ArrayList<String>();
                ArrayList<Double> prices = new ArrayList<Double>();

                //taking input from user
                Scanner input = new Scanner(System.in);

                //Adding products and prices
                products.add("Bison Sweater");
                prices.add(55.99);
                products.add("Bison Tee");
                prices.add(14.99);
                products.add("Bison Hoodie");
                prices.add(23.99);
                products.add("Bison Bumpersticker");
                prices.add(4.99);

                String answer = "";
                ArrayList<String> purchases = new ArrayList<String>();

                do {
                    System.out.println("What action would you like to complete?          ");
                    System.out.println("1) add item 2) change purchase 3) show cart 4) finish transaction");

                    answer = input.nextLine();
                    if (answer.equals("1"))
                    {
                        System.out.println("What item would you like to add to your cart?");
                        System.out.println("Select from these options: Bison Sweater, Bison Tee, Bison Hoodie, Bison Bumpersticker");
                        answer = input.nextLine();
                        purchases.add(answer);
                    }

                    else if (answer.equals("2"))
                    {
                        System.out.println("What purchase you want to change?");
                        String change = input.nextLine();

                        System.out.println("What you want to change with?");
                        String changewith = input.nextLine();

                        purchases.set(purchases.indexOf(change), changewith);
                    }

                    //displaying the purchases information
                    else if (answer.equals("3"))
                    {
                        for(int i = 0; i < purchases.size(); i++)
                        {
                            System.out.println(purchases.get(i));
                        }
                    }
                } while (! answer.equals("4"));


                double totalcost = 0.0; //calculates total cost
                int j = 0;
                for (int i = 0; i < purchases.size(); i++)
                {
                    j=0;
                    do {
                        if (purchases.get(i).equals(products.get(j)) )
                        {
                            totalcost = totalcost + prices.get(j);
                        }
                        j++;
                    } while (j < products.size());
                }
                System.out.println("Total Cost: "+totalcost);
            }
        }
