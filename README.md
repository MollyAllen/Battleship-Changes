# Battleship-Changes
This set up files uses the original battleship game and changes the methods below to modify the game to 
use an 8 x 8 board. I also call this version of the game BAttleship Exclamation (Battleship!) because that's how Dan
titled the assignment sheet.

Edits to make Battleship! work
(A to H, 1 to 8, ships AC, BS, C, 2 x D, 2 x S)

BattleshipModel

Change private class constant values below

// Private class constant values
	private static final int BOARD_WIDTH = 8;
	private static final int BOARD_HEIGHT = 8;
	private static final String LETTERS = "ABCDEFGH";
	

// change
private Ship getShip(char shipReference) {
		if (shipReference == Carrier.REFERENCE) {
			return new Carrier();
		} else if (shipReference == Battleship.REFERENCE) {
			return new Battleship();
		} else if (shipReference == Cruiser.REFERENCE) {
			return new Cruiser();
		} else if (shipReference == Destroyer.REFERENCE) {
			return new Destroyer();
		} else {
			return null;
		}
	}

//add
class for submarine




// change in PlayGame
 public boolean validateSquare (String in) {
        String[] validRowChar = {"A","B","C","D","E","F","G","H","I","J"}; // valid row
        int[] validColNum = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10}; // valid column

        String rowChar = in.substring(0,1); // get row from input string
        String colNum = in.substring(1); // get column from input string

        return Arrays.binarySearch(validRowChar, rowChar) >= 0 &&
        		Arrays.binarySearch(validColNum, Integer.parseInt(colNum)) >= 0;
    }


// change in getShipChar - PlayGame

    public char getShipChar (String item) { 
        char s = ' ';
        if (item.equals("aircraft carrier")) { s = 'A'; }
        else if (item.equals("battleship"))  { s = 'B'; }
        else if (item.equals("cruiser"))     { s = 'C'; }
        else if (item.equals("destroyer1"))   { s = 'D'; }
        else if (item.equals("destroyer2"))   { s = 'D'; }
        else if (item.equals("submarine1"))   { s = 'S'; }
        else if (item.equals("submarine2))   { s = 'S'; }
        return s;
    }


// change place - PlayGame
 public void place (String playerID, boolean playerNum,BattleshipModel game) 


// change play - PlayGame
public boolean play

// change printBoard
public static void printBoard(char[] gridVals)

