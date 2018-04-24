# CurrencyCalculator
School project


    import java.util.*;
    import javax.swing.*;
    import java.awt.*;
    import java.awt.geom.*;
    import java.util.Scanner;

    public class main
    {
        public char selection; 
               
        public main()
        
        {
        int length = 0;
        System.out.println("Welcome to the Bank of Winterfell");
        Scanner in = new Scanner(System.in);
            do {
            showMenu();
            String menu = in.nextLine(); // read a line of input
            char selection;
            // ? operator instead of if? char selection = menu.isEmpty() ? ' ' : menu.charAt(0);
            
            if (menu.length() > 0) 
                {
                    selection = menu.toLowerCase().charAt(0); // extract the first char of the line read
                }
            else 
                {
                    selection = '\0';
                    System.out.println("invalid input:\t"+selection);
                    System.out.println("Press enter to continue...");
                    Scanner itScan = new Scanner(System.in);
                    String nextIt = itScan.nextLine();
                    // special char when input is empty...
                } 
            switch (selection)
            {
                case 'a':
                CalcChange();
                break;
                
                case 'b':
                FeastCalc();
                break;
                
                case 'c':
                drawWinterfell();
                break;
                
                case 'd':
                //parseCurrency();
                break;
                
                case 'e':
                //armyCost();
                break;
                
                case 'f':
                //armyCostList();
                break;
                
                case 'g':
                //conflictCost();
                break;
                
                case 'h':
                //drawArmy();
                break;
                                  
                case 'q':
                System.out.println("\nEnding Now\n");
                System.exit(0);
                break;
                    
                default: 
                System.out.println("Instruction is invalid");
            }
        } 
        while (selection != 'Q' && selection != 'q');
        {
            System.exit(0);
        }
        
    }
    
            // printing menu
    public static void showMenu() {
            System.out.print('\u000c');
            System.out.println("MT 1: \n");
            System.out.println("A - Compute Change \n");
            System.out.println("B - Estimate Feast \n");
            System.out.println("C - Draw Winterfell castle\n");
            System.out.println("\n----------------------------------------------------\n");
            System.out.println("MT 2: \n");
            System.out.println("D - Parse Currency\n");
            System.out.println("E - Army for a given cost\n");
            System.out.println("F - Army for a given cost list\n");
            System.out.println("\n----------------------------------------------------\n");
            System.out.println("Assignment: \n");
            System.out.println("G - Cost of the Conflict\n");
            System.out.println("H - Draw army\n");
            System.out.println("\n----------------------------------------------------\n");
            System.out.println("QQ - Bored? Enter qq to exit.\n");
            System.out.println("Select Option:\n");
        }
    
            // Parse Currency
    public void parseCurrency()
    {
        
    }
        
    public void armyCost()
    {
        
    }    
        
    public void armyCostList()
    {
        
    }    
        
            // change calculator
            
            // change calculator
            
    public void CalcChange()
    {
                // variables 
                // cost of item
        int dragons = 0;
        int stags = 0;
        int penies = 0;  
        int halfpenies = 0;
                // money received
        int dragonsReceived = 0;
        int stagsReceived = 0;
        int peniesReceived = 0;  
        int halfpeniesReceived = 0;
                // amount returned
        int dragonsReturned = 0;
        int stagsReturned = 0;
        int peniesReturned = 0;  
        int halfpeniesReturned = 0;
                // Half penies difference
        int difference;
        
                // program instructions
        
        System.out.print('\u000c');
        System.out.println("\nyou selected option 1, Compute Change"); 
        System.out.println("\nThis is where we will convert currency. You must enter some information. Please read instructions carefully.");
        System.out.println("\nNow you will enter the retail value of the item in the following order; Dragons, Stags, Penies, Halfpenies: ");
        System.out.println("\nPlease enter the Gold Dragons of the item: \n");
                
                // enter in the cost of the item 
                
        Scanner coinz = new Scanner(System.in);
        dragons = coinz.nextInt();
                        
        System.out.println("Please enter the Stags of the item: \n");
        stags = coinz.nextInt();
                        
        System.out.println("Please enter the Penies of the item: \n");
        penies = coinz.nextInt();
                                
        System.out.println("Please enter the halfpenies of the item: \n");
        halfpenies = coinz.nextInt();
                
                // enter money robbed from customer
                
        System.out.println("\n\nPlease enter the amount of currency given to you: \n"); //money taken
        System.out.println("Please enter the Gold Dragons received: \n");
        dragonsReceived = coinz.nextInt();
                
        System.out.println("Please enter the Stags received: \n");
        stagsReceived = coinz.nextInt();
                
        System.out.println("Please enter the Penies received: \n");
        peniesReceived = coinz.nextInt();
                
        System.out.println("Please enter the halfpenies received: \n");
        halfpeniesReceived = coinz.nextInt();
                
                // conversion to half pennies 
                
        int r1 = convertToHalfPenies(dragons, stags, penies, halfpenies);
        int r2 = convertToHalfPenies(dragonsReceived, stagsReceived, peniesReceived, halfpeniesReceived);
                
                // print cost of item
        System.out.println("----------------------------------------------------\n");
        System.out.println("Cost of item in common currency:\n");
        System.out.println("Number of Gold Dragons for item:\t "+dragons);
        System.out.println("Number of Stags for item:\t\t "+stags);
        System.out.println("Number of Penies for item:\t\t "+penies);
        System.out.println("Number of Halfpenies for item:\t\t "+halfpenies);
                
                

        System.out.println("\nCost of item in Halfpenies:\t\t "+r1);
                
                // print currency received
        System.out.println("----------------------------------------------------\n");
        System.out.println("Amount of common currency received:\n");
        System.out.println("Number of Gold Dragons received:\t "+dragonsReceived);
        System.out.println("Number of Stags received:\t\t "+stagsReceived);
        System.out.println("Number of Penies received:\t\t "+peniesReceived);
        System.out.println("Number of Halfpenies received:\t\t "+halfpeniesReceived);
                
        System.out.println("\nNumber of Halfpenies received:\t\t "+r2);
                
        System.out.println("----------------------------------------------------");
                
                // difference in half pennies
        difference=(r2)-(r1);        
        System.out.println("\nHalfpenies difference:\t\t\t "+(difference));
        System.out.println("----------------------------------------------------\n\n");

                
                // does the customer have sufficient funds?
        if (r2<r1){
                   
            System.out.println("Insufficient funds, try again"); // this is whre a currency highest common currency tool would be niiiice
        }
        else {
              System.out.println("----------------------------------------------------");
                    // currency conversion into lowest common currency 
              dragonsReturned=(difference)/(23520);
              difference = difference - (dragonsReturned*23520);
              stagsReturned=(difference)/(112);
              difference = difference - (stagsReturned*112);
              peniesReturned=(difference)/(2);
              difference = difference - (peniesReturned*2);
              halfpeniesReturned=difference;
                                   
                    // print currency returned 
              System.out.println("\nDragons returned:\t\t\t "+dragonsReturned);
              System.out.println("Stags returned:\t\t\t\t "+stagsReturned);
              System.out.println("Penies returned:\t\t\t "+peniesReturned);
              System.out.println("Half Penies returned:\t\t\t "+halfpeniesReturned);

        }
                // "pause" program to display results
        System.out.println("Press enter to continue...");
        Scanner itScan = new Scanner(System.in);
        String nextIt = itScan.nextLine();
    }
            // also needs to have input control
            // half penny conversion
    public int convertToHalfPenies(int num1, int num2, int num3, int num4)
    {
        int result=(((int) num1)*210*56*2)+(((int) num2)*56*2)+(((int) num3)*2)+((int) num4);
        return result;
    }
            // lowest common currency conversion
            
    public int convertToFullCurrency(int num1, int num2, int num3, int num4)
    {
        int result=(((int) num1)/210/56/2)+(((int) num2)/56/2)+(((int) num3)/2)+((int) num4);
        return result;
    }
    public int noble;
    public int retainer;
    public int tyrion;
    
    public int temp;
    public static void FeastCalc()
    {
        /**headCount headCountObject = new headCount();
        headCount headCountObject2 = new headCount(5);
        headCount headCountObject3 = new headCount(5,13);
        headCount headCountObject4 = new headCount(5,13,1);
        
        // this is silly 
        System.out.printf("%s\n", headCountObject.currentheadCount());
        System.out.printf("%s\n", headCountObject2.currentheadCount());
        System.out.printf("%s\n", headCountObject3.currentheadCount());
        System.out.printf("%s\n", headCountObject4.currentheadCount());
        */
        System.out.print('\u000c');
        System.out.println("\nFeast Calculator. \n"); 
        System.out.println("If you enter numbers outside the given parameters, the calculator will return 0. ie, 0 nobles will be in attendance if you enter 23 into the calculator.\n");
        
                
        System.out.println("Please enter the number of Nobles (0-20) to cater for. Please enter an integer: \n");
        Scanner sc = new Scanner(System.in);
        int noble= sc.nextInt();
        noble =((noble>=0 && noble<=20) ?noble:0);
        
        System.out.println("Please enter the number of Retainers (0-80) to cater for. Please enter an integer: \n");
        int retainer= sc.nextInt();
        retainer =((retainer>=0 && retainer<=80) ?retainer:0);
        
        System.out.println("Please enter the number of Tyrions (0-1) to cater for. Please enter an integer: \n");
        int tyrion= sc.nextInt();
        tyrion =((tyrion>=0 && tyrion<=1) ?tyrion:0);
        
        
        System.out.println("\n----------------------------------------------------\n");
        System.out.println("Number of nobles: \t\t\t"+noble);
        System.out.println("\nNumber of retainers: \t\t\t"+retainer);
        System.out.println("\nNumber of Tyrions: \t\t\t"+tyrion);
        System.out.println("\n----------------------------------------------------\n");
        
        
                // half penny amounts of the feast
        int nobleMeal = 254;
        int retainerMeal = 49;
        int tyrionMeal = 272;
        int nobleNEW = 0;
        
        int dragonsReturned = 0;
        int stagsReturned = 0;
        int peniesReturned = 0;
        int halfpeniesReturned = 0;
        int rawPenies = 0;
        
        if (tyrion == 1)
        {
            nobleNEW = noble -1;
            System.out.println("number of nobles without tyrion: \t"+nobleNEW);
            nobleNEW = nobleMeal * nobleNEW;
            System.out.println("cost of nobles meal w/o tyrion: \t"+nobleNEW);
            retainer = retainerMeal * retainer;
            System.out.println("cost of retainer meal: \t\t\t"+retainer);
            int temp = nobleNEW + retainer + tyrionMeal;
            System.out.println("Feast cost in half penies: \t\t"+temp);
            System.out.println("\n----------------------------------------------------\n");
            
            rawPenies = temp;
                // converting to lowest common currency - should probs use modulo
                
            dragonsReturned=(rawPenies)/(23520);
            rawPenies = rawPenies - (dragonsReturned*23520);
            stagsReturned=(rawPenies)/(112);
            rawPenies = rawPenies - (stagsReturned*112);
            peniesReturned=(rawPenies)/(2);
            rawPenies = rawPenies - (peniesReturned*2);
            halfpeniesReturned=rawPenies;
            
                    // print currency returned 
            System.out.println("\nDragons returned:\t\t\t "+dragonsReturned);
            System.out.println("Stags returned:\t\t\t\t "+stagsReturned);
            System.out.println("Penies returned:\t\t\t "+peniesReturned);
            System.out.println("Half Penies returned:\t\t\t "+halfpeniesReturned);
        }         
        else 
        {
            noble = nobleMeal * noble;
            System.out.println("number of nobles without tyrion: \t"+noble);
            retainer = retainerMeal * retainer;
            System.out.println("cost of retainer meal: \t"+retainer);            
            
            int temp = noble + retainer;
            System.out.println("Feast cost in half penies: \t\t"+temp);
            
            rawPenies = temp;
            
            System.out.println(rawPenies);
                    // converting to lowest common currency - should probs use modulo
            dragonsReturned=(rawPenies)/(23520);
            rawPenies = rawPenies - (dragonsReturned*23520);
            stagsReturned=(rawPenies)/(112);
            rawPenies = rawPenies - (stagsReturned*112);
            peniesReturned=(rawPenies)/(2);
            rawPenies = rawPenies - (peniesReturned*2);
            halfpeniesReturned=rawPenies;
            
            
                    // print currency returned 
            System.out.println("\nDragons returned:\t\t\t "+dragonsReturned);
            System.out.println("Stags returned:\t\t\t\t "+stagsReturned);
            System.out.println("Penies returned:\t\t\t "+peniesReturned);
            System.out.println("Half Penies returned:\t\t\t "+halfpeniesReturned);
            System.out.println("\n----------------------------------------------------\n");
        }
        
        // the if else objects output one number each, how do i run this through my existing currency converter?
        Scanner itScan1 = new Scanner(System.in);
        String nextIt1 = itScan1.nextLine(); 
    }
    } 
