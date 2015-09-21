import java.util.*;
import java.io.*;

public class knightsTour {
    int[][] chessboard = new int[8][8];
    Random rd = new Random();
    int currX = 0;
    int currY = 0;
    int addX = 0;
    int addY = 0;
    int countSteps = 1;
    final int DEBUG_MODE = 1;
    
    public void startProgram(){
        chessboard[currX][currY] = countSteps;
        countSteps++;
    }
    
    public void knightMove(){
        boolean noMovesPossible = false;
        while (noMovesPossible == false && countSteps <= 64){
            ArrayList <validPoints> validPoints = new ArrayList <validPoints> ();
            for (int runSwitch = 0; runSwitch < chessboard.length; runSwitch++){
                assignValues(runSwitch);
                boolean isInBounds = isInBounds(addX, addY);
                boolean notAnotherPoint = false;
                
                if (isInBounds == true){
                    notAnotherPoint = notAnotherPoint(addX, addY);
                }
                
                if (isInBounds == true && notAnotherPoint == true){
                    validPoints.add(new validPoints(addX, addY));
                }
            }
            if (validPoints.size() == 0){
                noMovesPossible = true;
            } else {
                int randomPoint = rd.nextInt(validPoints.size());
                int addToX = validPoints.get(randomPoint).getX();
                int addToY = validPoints.get(randomPoint).getY();
                currX += addToX;
                currY += addToY;
                chessboard[currX][currY] = countSteps;
                countSteps++;
            }
        }
    }
    
    public void assignValues(int key){
        switch (key){
            case 0: addX = 1;
                    addY = -2;
                    break;
            case 1: addX = 2;
                    addY = -1;
                    break;
            case 2: addX = 2;
                    addY = 1;
                    break;
            case 3: addX = 1;
                    addY = 2;
                    break;
            case 4: addX = -1;
                    addY = 2;
                    break;
            case 5: addX = -2;
                    addY = 1;
                    break;
            case 6: addX = -2;
                    addY = -1;
                    break;
            case 7: addX = -1;
                    addY = -2;
                    break;
        }
    }
        
    public boolean isInBounds(int addX, int addY){
        if ((((currX + addX) >= 0 && (currX + addX) <= 7) && ((currY + addY) >= 0 && (currY + addY) <= 7))){
            return true;
        } else {
            return false;
        }
    }
    
    public boolean notAnotherPoint(int addX, int addY){
        int totalX = currX + addX;
        int totalY = currY + addY;
        if (chessboard[totalX][totalY] == 0){
            return true;
        } else {
            return false;
        }
    }
    
    public void displayBoard(){       
        String boardDisplay = "";
        
        Formatter f = new Formatter();
        f.format("%-4s", "");
        boardDisplay += (f.toString());
        for (int i = 1; i <= 8; i++){
            Formatter f2 = new Formatter();
            f2.format("%-5d", i);
            boardDisplay += (f2.toString());
        }
        
        boardDisplay += "\n\n";
        
        for (int outer = 0; outer < chessboard.length; outer++){
            Formatter f3 = new Formatter();
            f3.format("%-4d", (outer + 1));
            for (int inner = 0; inner < chessboard[0].length; inner++){                
                f3.format("%-5d", chessboard[outer][inner]);
            }
            boardDisplay += (f3.toString() + "\n");
        }
        System.out.print(boardDisplay);
    }
    
    public static void main(String[] args){
        knightsTour kT = new knightsTour();
        kT.startProgram();
        kT.knightMove();
        kT.displayBoard();
        System.out.println("\n" + (kT.countSteps - 1) + " steps were traversed by this noble steed!");
    }
}
