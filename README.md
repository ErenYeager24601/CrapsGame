# CrapsGame
Coding my own version of craps. Where the player starts out with 100 points, if they can double their points, they win. If they reach zero, they lose. Game rules, roll 1 six sided dice, make a bet if the number is 2,3,4,5, lose 10 points if 1 or 6. Roll the dice again, numbers 1 &amp; 6 loses the bet you made, numbers[2...5] wins you the bet if the number is greater than the 1st dice number(i.e. dice1=2 &amp;&amp;dice2=5; you win).


import java.util.Scanner;

public class FinalProjDice {

	public static void main(String[] args) {

		System.out.println("Welcome to the Game: Dice Attack!");
		
		Scanner scr = new Scanner(System.in);
		System.out.println("Please enter your name: ");
		String name = scr.nextLine();
		System.out.println("\nWelcome " + name);
		
		System.out.println("\tHere are the Game Rules:"+"\nYou begin with $100 of betting money"+
		 "\nYou roll one six sided dice"+ "\nIf you roll a 1 or a 6, you lose Xamount of points"+
				"\nIf you roll a 2,3,4,5, you win Xamount of points");
		int dice = rollDice();
		
		for( int i =0; i <10; i++) {
			int dice1 = (int) rollDice();
			
		}
		
		int result = getResult(dice);
		
		if (isValidorInvalid(result))
			printResult(result);
		else {
			diceOff(result);
			
		System.out.println(pointCalc());
		}
	}
	
	public static int pointCalc() {
		
		int points1 = 100;
		
			
			
		
		
		
		return points1;
		
		
		
		
	}

	public static void diceOff(int num) {
		int result;
		
		do {
			
			result = rollDice();
		} while (result != 0);
		
		if (result ==0)
			printResult(0);
		else if (result ==1)
			printResult(1);
		
	}

	public static void printResult(int result) {
		if (result ==0)
			System.out.println("You Lose");
		else if ( result ==1)
			System.out.println("You Win");
		
		
	}

	public static boolean isValidorInvalid(int result) {
		return result == 0 || result ==1;

	}

	public static int getResult(int num) {
		//if point 1 or 6, return 0. [2...5] return 1
		//int num =0;
		switch (num) {
		
		case 1: num = 0; break;
		case 2:	num = 1; break;
		case 3: num = 1; break;
		case 4: num = 1; break;
		case 5: num = 1; break;
		case 6: num = 0; break;
		}
		
		return num;
	}

	public static int rollDice() {
		
		int x = (int)(1+Math.random()*6);
		System.out.println("You rolled a "+x);
		return x;

	}
	
	
	
 }
//instead of two dice like craps, it's only one
