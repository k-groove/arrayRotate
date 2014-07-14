import java.util.*;

public class ArrayRotate {
	
	private static int [][] array;
	private static int arraySize;
	
	
	public static void main (String[]args){
		
	Scanner input = new Scanner(System.in);
	System.out.println("What size array?");
	arraySize = input.nextInt();
	System.out.println("Your array will be "+arraySize+" x "+arraySize+".");
	array = new int [arraySize][arraySize];
	
	for(int i = 0; i < arraySize; i++) {
        Scanner line = new Scanner(System.in);
        System.out.println("enter "+ arraySize +" numbers for array row "+i);
        for(int j = 0; j < arraySize; j++) {
           array[i][j] = line.nextInt();
          
        }
     
     }
	input.close();
	printArray();
	rotateArray();
	printArray();
	rotateArray();
	printArray();
	rotateArray();
	printArray();
		
	}
	public static void printArray(){
		for(int i = 0; i < arraySize; i++){
			for(int j = 0; j < arraySize; j++){
				if (j == arraySize-1){
				System.out.print(array[i][j] +" \n");
				}else
					System.out.print(array[i][j]+" ");
			}
		}
	}
	// rotates array 90 degrees clockwise
	public static void rotateArray(){
		int [][] array2 = new int [arraySize][arraySize];
		for (int x = 0; x < arraySize; x++){
			for (int y = 0; y < arraySize; y++){
				array2[x][y] = array [arraySize - y - 1][x];				
			}
		}
		array = array2;
		System.out.println("rotate clockwise 90 degrees");
	}
}


