# CurrencyCalculator


School project

    import java.util.*;
    import javax.swing.*;
    import java.awt.*;
    import java.util.Scanner;
    import java.util.Arrays;


    public class parseStack
    {
    
    public parseStack()
    {
        System.out.print('\u000c');
        String CurrencyFormat = "xD xS xP xH";
        System.out.println("Please enter currency in the following format: \""+CurrencyFormat+"\" where x is any integer");
        System.out.println("\nPlease take care to use the correct spacing enter the exact integer plus type of coin\n\n");
         
        Scanner scan = new Scanner(System.in);
        String currencyIn = scan.nextLine();
        currencyIn = currencyIn.toUpperCase();
        System.out.println("This is the currency you entered: "+currencyIn);
        
        String[] tokens = currencyIn.split(" ");
        final String input = tokens[0];
        final String regex = "([0-9]+)[D|d]\\ ([0-9]+)[S|s]\\ ([0-9]+)[P|p]\\ ([0-9]+)[H|h]";

        if (input.matches(regex) == false) {
            throw new IllegalArgumentException("Input is malformed.");
            
        }
        
            long[] values = Arrays.stream(input.replaceAll(regex, "$1 $2 $3 $4").split(" "))
                    .mapToLong(Long::parseLong)
                    .toArray();

                    System.out.println(Arrays.toString(values));
        
    }
    }
