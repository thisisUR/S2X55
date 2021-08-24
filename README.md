# S2X55
## About
A tool to convert string to ascii code for `String.fromCharCode()` function.
Its used in `eval()` function for Xss vulnerability payloads when `alert()` is been block.

#### Source code 
``` source code
import java.util.*;

// String to UTF_16
//Tool to generate Xss payloads for String.fromCharCode(" ")
//fromCharCode takes UTF_16
class S2X55{
	public static void main(String args[]) {
		Scanner sc = new Scanner(System.in);
		//System.out.println("Enter the payload to be converted");
		//String user_input = sc.nextLine();
		try {
		String user_input = args[0]; // comment this line and uncomment line no. 9 &10
		int len1 = user_input.length(); // if you face any error.
		char[] ch_arr = user_input.toCharArray();
		int count = 0;
		System.out.print("String.fromCharCode(");
		for(int a=0; a<len1; a++) {
			 count = ch_arr[a];
			if(a == len1-1) {
					System.out.printf("%d)",count);
			} else {
			System.out.printf("%d, ",count);
			}
		}
		} catch(ArrayIndexOutOfBoundsException E){
			System.out.println("Following the syntax give below to generate payload");
			System.out.printf("java S2X55 [payload]\n");
			System.out.println("Example : java S2X55 XSS");
			System.out.println("String.fromCharCode(88, 83, 83)");
			System.out.printf("\nAuthor - thisisUR \n");
		}
    }
}
```
## Installing
- Requirement - Install java JDK 

git clone https://github.com/thisisUR/S2X55.git
cd to directory
`$ javac S2X55.java`

## Run
`$ java S2X55 [Payload]`
**Sample command**
`$ java S2X55 XSS`
##### O/P 
`String.fromCharCode(88, 83, 83)` //ascii code for X - 88, S - 83

