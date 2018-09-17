# Matrices
package exercises;

import java.util.Arrays;

import static java.lang.StrictMath.round;
import static java.lang.StrictMath.sqrt;
import static java.lang.System.out;

/*
 * Methods with array/matrix params and/or return value. Implement methods.
 *
 * See:
 * - Matrices
 */
public class Ex3MatrixMethods {

    public static void main(String[] args) {
        new Ex3MatrixMethods().program();
    }

    void program() {
        int[][] m = {           // Hard coded test data
                {-1, 0, -5, 3},
                {6, 7, -2, 0},
                {9, -2, -6, 8},
                {0, 0, 5, -6}
        };

        // TODO uncomment one at a time and implement

        // Return array with all negatives in m
        int[] negs = getNegatives(m);
        out.println(negs.length == 6);
        //out.println(Arrays.toString(negs).equals("[-1, -5, -2, -2, -6, -6]")); // Possibly other ordering!

        // Mark all negatives with a 1, others as 0
        // (create matrix on the fly)
        int[][] marked = markNegatives(new int[][]{
                {1, -2, 3,},
                {-4, 5, -6,},
                {7, -8, 9,},
        });
        /* marked should be
        { {0, 1, 0},
          {1, 0, 1},
          {0, 1, 0} }
        */
        out.println(Arrays.toString(marked[0]).equals("[0, 1, 0]"));
        out.println(Arrays.toString(marked[1]).equals("[1, 0, 1]"));
        out.println(Arrays.toString(marked[2]).equals("[0, 1, 0]"));

        int[] arr = {1, 2, 3, 4, 5, 6, 7, 8, 9};
        // Create matrix from array
        //int[][] matrix = toMatrix(arr);
        /* matrix should be
        { {1, 2, 3},
          {4, 5, 6},
          {7, 8, 9} }
        */
        //plot(matrix);  // If manual inspection
        //out.println(Arrays.toString(matrix[0]).equals("[1, 2, 3]"));
        //out.println(Arrays.toString(matrix[1]).equals("[4, 5, 6]"));
        //out.println(Arrays.toString(matrix[2]).equals("[7, 8, 9]"));

        // Sum of all directly surrounding elements to some element in matrix
        // (not counting the element itself)
        // NOTE: Should be possible to expand method to include more distant neighbours
        //out.println(sumNeighbours(matrix, 0, 0) == 11);
        //out.println(sumNeighbours(matrix, 1, 1) == 40);
        //out.println(sumNeighbours(matrix, 1, 0) == 23);
    }

    int[][] markNegatives(int[][] ints) {
        int[][] marked = new int[3][3];
        int i = 0;
        for (int r = 0; r < ints.length; r++){
            for (int c = 0; c < ints.length; c++){
                if (ints[r][c] < 0){
                    marked[r][c] = 1;
                    i++;
                } else {
                    marked[r][c] = 0;
                    i++;

                }
            }
        }
        return marked;

    }

    // -------- Write methods below this -----------------------


   int[][] toMatrix(int[] arr) {
        int[][] nMatrice = new int[3][3];
        int i = 0;

        for (i = 0; i < arr.length; i++){
            int u = i % 3;
            int r = i % 3;
            nMatrice[r][u] = arr[i];
            out.println(nMatrice[r][u]);

        }
        return nMatrice;
    }

    // Use if you like (during development)
    void plot(int[][] matrix) {
        for (int row = 0; row < matrix.length; row++) {
            out.println(Arrays.toString(matrix[row]));
        }
    }
    int []getNegatives(int [][] m) {
        int[] negs = new int[6];
        int i = 0;
        for (int r = 0; r < m.length; r++){
            for (int c = 0; c < m.length; c++){
                if (m[r][c] < 0){
                    negs[i] = m[r][c];
                    i++;
                }
            }
        }
        return negs;
    }

    int count(int[][] m) {
        int[] negs = new int[count(m)];
        int i = 0;
        for (int r = 0; r < m.length; r++){
            for (int c = 0; c < m.length; c++){
                if (m[r][c] < 0){
                    negs[i] = m[r][c];
                    i++;
                }
            }
        }
        return i;
    }


}
