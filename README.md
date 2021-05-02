# tic-tac-toeimport 
java.util.ArrayList;
import java.util.Random;

import com.sun.java_cup.internal.runtime.Symbol;
import com.sun.tools.javac.util.List;

import jdk.nashorn.internal.parser.Scanner;
import sun.jvm.hotspot.utilities.SystemDictionaryHelper;

public class TicTacToe{

    static ArrayList<aInteger> playerPositions = new ArrayList<Integer>();
    static ArrayList<aInteger> cpuPositions = new ArrayList<Integer>();

    public static void main(string[]args) {
        
        char[] [] gameBoard= {{' ','|', ' ', '|',' '},
        {'-','+', '-', '+','-'},
        {' ','|', ' ', '|',' '},
        {'-','+', ' ', '+','-'},
        {' ','|', ' ', '|',' '},};

        printGameBoard(gameBoard);

        java.util.Scanner scan = new Scanner(System.in);

        while(true){
            system.out.println("Enter your placement (1-9:");
            int playerPos = scan.nextInt();
        }
        placePiece(gameBoard, playerPos, "player");

        Random rand = new Random();
        int cpuPos = rand.nextInt(9) + 1;
        placePiece(gameBoard, cpuPos, "cpu");

        printGameBoard(gameBoard);

        checkWinner();

    }

    public static void printGameBoard(char[] [] gameBoard) {
        for (char [] row : gameBoard) {
            for (char c : row) {
                systemm.out.print(c);
            }
            System.out.println();
        }
    }

    public static void placePiece(char [] [] gameBoard, int pos, String user) {
       
        if( user.equals("player")) {
          char  sysmbol = ' ';
        }else if(user.equals("cpu")){
            symbol = '0';
        }

        switch (pos) {
            case 1 :
                gameBoard [0] [0] = symbol;
                break;
             case 2 :
                gameBoard [0] [2] = symbol;
                break;
             case 3 :
                gameBoard [0] [4] = symbol;
                break;
            case 4 :
                gameBoard [0] [0] = symbol;
                break;
            case 5 :
                gameBoard [2] [0] = symbol;
                break;
            case 6 :
                gameBoard [2] [2] = symbol;
                break;                
            case 7 :
                gameBoard [2] [4] = symbol;
                break;
            case 8 :
                gameBoard [4] [2] = symbol;
                break;
            case 9 :
                gameBoard [4] [4] = symbol;
                break;
            default:
                break;
        }

    }

    public static String checkWinner() {

        List topRow = Array.asList(1, 2, 3);
        List middleRow = Array.asList(4, 5, 6);
        List botRow = Array.asList(7, 8, 9);
        List leftCol = Array.asList(1, 4, 7);
        List midCol = Array.asList(2, 5, 6);
        List rightCol = Array.asList(3, 6, 9);
        List cross1 = Array.asList(1, 5, 9);
        List cross2 = Array.asList(7, 5, 3);
        
        List<List> winning = new ArrayList<List>();
        winning.add(topRow);
        winning.add(middleRow);
        winning.add(botRow);
        winning.add(leftCol);
        winning.add(midCol);
        winning.add(rightCol);
        winning.add(cross1);
        winning.add(cross2);

        for (List l : winning) {
            if(playerPositions.containsAll(l)) {
                return "congratulations you won";
            }else if (cpuPositions.containsAll(l)) {
                return "CPU wins! Sorry :(";
            }else if (playerPositions.size() + cpuPosition.size() == 9) {
                return "CAT!";
            }
        }


        return "";
    }
}  
