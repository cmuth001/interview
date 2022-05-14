1. Given grid position(i, j), count how many are present in the grid with same value, should always be adjacent. 
```
/*
While your players are waiting for a game, you've developed a solitaire game for the players to pass the time with.
The player is given an NxM board of tiles from 0 to 9 like this:
  4   4   4   4
  5   5   5   4
  2   5   7   5
The player selects one of these tiles, and that tile will disappear, along with any tiles with the same number that are connected with that tile (up, down, left, or right), and any tiles with the same number connected with those, and so on. For example, if the 4 in the upper left corner is selected, these five tiles disappear
 >4< >4< >4< >4<
  5   5   5  >4<
  2   5   7   5
If the 5 just below it is selected, these four tiles disappear. Note that tiles are not connected diagonally.
  4   4   4   4
 >5< >5< >5<  4
  2  >5<  7   5
Write a function that, given a grid of tiles and a selected row and column of a tile, returns how many tiles will disappear.
grid1 = [[4, 4, 4, 4],
         [5, 5, 5, 4],
         [2, 5, 7, 5]]
disappear(grid1, 0, 0)  => 5
disappear(grid1, 1, 1)  => 4
disappear(grid1, 1, 0)  => 4
This is the grid from above.

Additional Inputs
grid2 = [[0, 3, 3, 3, 3, 3, 3],
         [0, 1, 1, 1, 1, 1, 3],
         [0, 2, 2, 0, 2, 1, 4],
         [0, 1, 2, 2, 2, 1, 3],
         [0, 1, 1, 1, 1, 1, 3],
         [0, 0, 0, 0, 0, 0, 0]]

grid3 = [[0]]

grid4 = [[1, 1, 1],
         [1, 1, 1],
         [1, 1, 1]]

All Test Cases
disappear(grid1, 0, 0)  => 5
disappear(grid1, 1, 1)  => 4
disappear(grid1, 1, 0)  => 4
disappear(grid2, 0, 0)  => 12
disappear(grid2, 3, 0)  => 12
disappear(grid2, 1, 1)  => 13
disappear(grid2, 2, 2)  => 6
disappear(grid2, 0, 3)  => 7
disappear(grid3, 0, 0)  => 1
disappear(grid4, 0, 0)  => 9

N - Width of the grid
M - Height of the grid
*/
````
2. Find valid string is valid tMahjong.

```
import java.io.*;
import java.util.*;

public class Solution {
  public static void main(String[] argv) {
      String tiles1 = "11133555";
      String tiles2 = "111333555";
      String tiles3 = "00000111";
      String tiles4 = "13233121";
      String tiles5 = "11223344555";
      String tiles6 = "99999999";
      String tiles7 = "999999999";
      String tiles8 = "9";
      String tiles9 = "99";
      String tiles10 = "000022";
      String tiles11 = "888889";
      String tiles12 = "889";
      String tiles13 = "88888844";
      String tiles14 = "77777777777777";
      String tiles15 = "1111111";
      String tiles16 = "1111122222";
      // boolean result = isItMahjong(tiles1);
      System.out.println(isItMahjong(tiles1));
      System.out.println(isItMahjong(tiles2));
      System.out.println(isItMahjong(tiles3));
      System.out.println(isItMahjong(tiles4));
      System.out.println(isItMahjong(tiles5));
      System.out.println(isItMahjong(tiles6));
      System.out.println(isItMahjong(tiles7));
      System.out.println(isItMahjong(tiles8));
       System.out.println(isItMahjong(tiles9));
      System.out.println(isItMahjong(tiles10));
      System.out.println(isItMahjong(tiles11));
      System.out.println(isItMahjong(tiles12));
      System.out.println(isItMahjong(tiles13));
      System.out.println(isItMahjong(tiles14));
      System.out.println(isItMahjong(tiles15));
      System.out.println(isItMahjong(tiles16));

  }
  public static boolean isItMahjong(String s){
    Map<Character, Integer> map = new HashMap<>();
    for(char ch: s.toCharArray()){
      map.put(ch, map.getOrDefault(ch, 0)+1);
    }
    int pairCount = 0;
    for(int val: map.values()){
      if(val%3!=0 || val>3){
        while(val>2) val-=3;
        if(val==1){
            return false;
        }else if(val==2){
          pairCount++;
        }
        if(pairCount>1) return false;

      }else if(val==2){
        pairCount++;
        if(pairCount>1) return false;
      }

    }
    return pairCount!=1? false:true;
  }
}
```
