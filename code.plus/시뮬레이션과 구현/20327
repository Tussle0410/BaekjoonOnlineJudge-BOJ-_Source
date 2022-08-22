import java.io.*;
import java.util.*;

public class Main {
	static int N,R;	
	static int[][] arr;		//입력되는 배열 및 변경되는 배열
    public static void main(String[] args) throws IOException {
    	BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        //입력값 처리하는 BufferedReader
    	BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
        //결과값 출력하는 BufferedWriter
    	StringTokenizer st = new StringTokenizer(br.readLine()," ");
    	N = Integer.parseInt(st.nextToken());
    	R = Integer.parseInt(st.nextToken());
    	int size = (int)Math.pow(2,N);
    	arr = new int[size][size];
        //배열의 값 저장
    	for(int i=0;i<size;i++) {
    		st = new StringTokenizer(br.readLine()," ");
    		for(int j=0;j<size;j++)
    			arr[i][j] = Integer.parseInt(st.nextToken());
    	}
        //연산의 값 저장
    	for(int i=0;i<R;i++) {
    		st = new StringTokenizer(br.readLine()," ");
    		int k = Integer.parseInt(st.nextToken());
    		int l = Integer.parseInt(st.nextToken());
    		cal(k,l,size);		//배열 변경 함수 실행
    	}
        //R번 연산으로 변경된 배열 BufferedWriter 저장
    	for(int i=0;i<size;i++) {
    		for(int j=0;j<size;j++) 
    			bw.write(arr[i][j] + " ");
    		bw.newLine();
    	}
    	bw.flush();		//결과 출력
    	bw.close();
    	br.close();
    }
    //연산에 대한 함수를 호출하는 함수
    static void cal(int k, int l, int size) {
    	int arrDiv = (int)Math.pow(2, l);	//∂에 따른 구역의 크기 구하기
        //연산 번호에 따른 함수 호출
    	if(k==1) {
    		one(arrDiv,size);
    	}else if(k==2)
    		two(arrDiv,size);
    	else if(k==3)
    		three(arrDiv,size);
    	else if(k==4)
    		four(arrDiv,size);
    	else if(k==5)
    		five(arrDiv,size);
    	else if(k==6)
    		six(arrDiv,size);
    	else if(k==7)
    		seven(arrDiv,size);
    	else
    		eight(arrDiv,size);
    }
    //연산 1.
    static void one(int div,int size) {
    	int tempDiv = div/2;
    	for(int i=div;i<=size;i += div) {
    		int minus = 0;
    		for(int j = i-div;j<i-tempDiv;j++) {
				minus++;
    			for(int s = 0;s<size;s++) {
    				int temp = arr[j][s];
    				arr[j][s] = arr[i-minus][s];
    				arr[i-minus][s] = temp;
    			}
    		}
    	}
    	return;
    }
    //연산 2.
    static void two(int div, int size) {
    	int tempDiv = div/2;
    	for(int i=div;i<=size;i += div) {
    		int minus = 0;
    		for(int j=i-div;j<i-tempDiv;j++) {
    			minus++;
    			for(int s=0;s<size;s++) {
    				int temp = arr[s][j];
    				arr[s][j] = arr[s][i-minus];
    				arr[s][i-minus] = temp;
    			}
    		}
    	}
    }
    //연산 3.
    static void three(int div, int size) {
    	int[][] temp = new int[size][size];
    	for(int i=0;i<size;i++) {
    		for(int j = 0;j<size;j++) {
    			temp[(i/div)*div + j%div][((j/div+1)*div)-1 - i%div] = arr[i][j];
    		}
    	}
    	arr = temp;
    	return;
    }
    //연산 4.
    static void four(int div, int size) {
    	int[][] temp = new int[size][size];
    	for(int i=0;i<size;i++) {
    		for(int j=0;j<size;j++) {
    			temp[(i/div+1)*div -1 - j%div][(j/div)*div + i%div] = arr[i][j];
    		}
    	}
    	arr = temp;
    	return;
    }
    //연산 5.
    static void five(int div, int size) {
    	for(int i=0;i<size/2;i++) {
    		int row = ((size-i-1)/div)*div+i%div;
    		for(int j=0;j<size;j++) {
    			int temp = arr[i][j];
    			arr[i][j] = arr[row][j];
    			arr[row][j] = temp;
    		}
    	}
    	return;
    }
    //연산 6.
    static void six(int div,int size) {
    	for(int i=0;i<size/2;i++) {
    		int col = ((size-1-i)/div) * div + i%div;
    		for(int j=0;j<size;j++) {
    			int temp = arr[j][i];
    			arr[j][i] = arr[j][col];
    			arr[j][col] = temp;
    		}
    	}
    	return;
    }
    //연산 7.
    static void seven(int div, int size) {
    	int[][] temp = new int[size][size];
    	for(int i=0;i<size;i++) {
    		for(int j=0;j<size;j++) {
    			temp[(j/div)*div + i%div][((size-1-i)/div)*div + j%div] = arr[i][j];
    		}
    	}
    	arr = temp;
    	return;
    }
    //연산 8.
    static void eight(int div, int size) {
    	int[][] temp = new int[size][size];
    	for(int i=0;i<size;i++) {
    		for(int j=0;j<size;j++) {
    			temp[((size-1-j)/div)*div + i%div][(i/div)*div + j%div] = arr[i][j];
    		}
    	}
    	arr = temp;
    	return;
    }
}
