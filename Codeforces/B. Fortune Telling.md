# B. Fortune Telling Div 2 (Est rating 1400)
---
## My Code :
        '''java

        import java.util.Arrays;
        import java.util.Scanner;

        public class Main {
            public static void main(String[] args) {
                Scanner n = new Scanner(System.in);
                int frags = n.nextInt();
                int[] arr = new int[frags];
                int evencounter = 0;
                int oddcounter = 0;
                int sum = 0;

                

                for (int i = 0; i < frags; i++) {
                    arr[i] = n.nextInt();
                    if (arr[i] % 2 != 0) oddcounter++;
                    else evencounter++;
                }

                if (arr.length == 1) {
                    if (arr[0] % 2 == 0)
                        System.out.println("0");
                    else
                        System.out.println(arr[0]);
                } 
                else {
                    Arrays.sort(arr);
                    for (int k = frags - 1; k >= 0; k--) {
                        if (arr[k] % 2 == 0 && evencounter > 0) {
                            sum += arr[k];
                            evencounter--;
                        } else if (arr[k] % 2 != 0 && oddcounter > 0) {
                            sum += arr[k];
                            oddcounter--;
                        }
                    }

                    if (sum % 2 == 0) {
                        for (int j = 0; j < arr.length; j++) {
                            if (arr[j] % 2 != 0) {
                                sum -= arr[j];
                                break;
                            }
                        }
                    }
                    if (sum % 2 == 0){
                        sum = 0;
                        System.out.println(sum);
                    }
                    else{
                    System.out.println(sum);
                    }
                }
            }
        }
---
Greedy Approach where you just sum it all up and then subtract the minium odd at the end and that works because of number theory. Also if there is no odd just return 0. 