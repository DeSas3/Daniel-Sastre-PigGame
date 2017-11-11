 //  # Daniel-Sastre-PigGame
Daniel Sastre APCS PigGame Lab //
import java.util.*; //importing all java packages because i do not want to write to separate ones :v
 
 
public class playGame{
     
    public static void main(String[] args){
         
        Random rand = new Random();
        Scanner scan = new Scanner(System.in);
         
        System.out.println("Welcome to the PIG game!");
        System.out.println("Both players start off with zero points, to add to their score they must roll a dice. The score of the dice will be added to the player scores. The only number you can not get is 1. If you roll a one your turn will automatically end and your score resets to 0."); 	//Instructions of the game
        System.out.println("First player to 100 points or more wins");	//GAME INSTRUCTIONS
      
         

        int playerScore = 0;  //defining the variables that will be used during the game and giving them a value of zero
        int player2Score = 0;
        int playerToss = 0;
        int player2Toss = 0;
      
         
  
            while(!(playerScore >= 100 || player2Score >= 100)) //I used a giant while loop to be the entire, only to be broken when a player gets more than 100 points.
            {
                System.out.println("Player 1 turn");
                System.out.print("Press any button to roll: ");
                String rollOrNot = scan.next(); 
                 if(rollOrNot.equals("x")){  
                    playerToss = (int)rand.nextInt(6)+1; // I used the java random class, supposedly you do not have to use the int cast but my program was acting weird without it
                    System.out.println("Player 1 rolled a " + playerToss);
                 	}
                 	while(playerToss != 1){  // another while loop so that the player can roll as many times as he wants as long as he does not get 1.
                 		playerScore = playerScore + playerToss; // adding the rolling total to the player's score
                 		System.out.println("Player 1 score is now: " + playerScore); //always reminding the score to the player
                 		System.out.print("Press any button to roll or \'end\' to end turn: ");
                 		rollOrNot = scan.next();
                    	if(rollOrNot.equals("end"))
                    	{
                    		break; //typing 'end' will break this small while loop, therefore going to the next player
                    	}
                    		else //typing anything other than 'end' will keep the player rolling
                    		{
                    			playerToss = (int)rand.nextInt(6)+1;
                        		System.out.println("Player 1 rolled a " + playerToss);
                    		}
                    }
                     
                    	if(playerToss == 1) // if player gets a one his turn ends and score resets to zero
                    		{
                    			playerScore = 0;
                    			System.out.println("Player 1 has rolled a 1! Score resets to 0, Player 2 turn now");
                    		}
                    	
                    	System.out.println("Player 2 turn"); //Player 2 turn comes after, player 1 either decides to end turn or rolls a 1
                        System.out.print("Press any button to roll: "); //the exact same code used for player 1 is used for player, but using player's 2 variables
                        String rollOrNot1 = scan.next();
                         if(rollOrNot1.equals("x")){
                            player2Toss = (int)rand.nextInt(6)+1;
                            System.out.println("Player 2 rolled a " + player2Toss);
                         }
                         
                         	while(player2Toss != 1){
                         		player2Score = player2Score + player2Toss;
                         		System.out.println("Player 2 score is now: " + player2Score);
                         		System.out.print("Press any button to roll or \'end\' to end turn: ");
                         		rollOrNot1 = scan.next();
                            if(rollOrNot1.equals("end"))
                            	{
                            		break;
                            	}
                            		else
                            		{
                            			player2Toss = (int)rand.nextInt(6)+1;
                            			System.out.println("Player 2 rolled a " + player2Toss);
                            		}
                            }
                             
                            	if(player2Toss == 1)
                            	{
                            		player2Score = 0;
                            		System.out.println("Player 2 has rolled a 1! Score resets to 0, Player 1 turn now");
                            	}
                            	
                                            
            }// while loop to simulate the game end here. It should break only when either player 1 or player 2 gets 100 points.
            
            if(playerScore > player2Score){ // finally, we only tell the players who won. I used an if else statement. The player with more point should win as that player must have gotten to 100 to end the game.
				System.out.println("Player 1 is the winner!");
                }
                
				else {
					System.out.println("Player 2 is the winner!");
                }
        }
}


    
