import java.io.*;
import java.util.*;

public class Main{
    public static void main(String[] args) throws IOException {
        //입력값 처리하는 BufferedReader
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        //결과값 출력하는 BufferedWriter
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
        int N = Integer.parseInt(br.readLine());
        long answer = 0;
        int[] tips = new int[N];
        //각 손님의 팁 정보 저장
        for (int i = 0; i < N; i++)
            tips[i] = Integer.parseInt(br.readLine());
        Arrays.sort(tips);	//오름차순 정렬
        //팁 가격 높은 순으로 순서대로 입장
        for (int i = N-1; i >= 0 ; i--){
            int tip = tips[i] - (N-i-1);	//팁 구하기
            if(tip > 0)	//팁이 양수일 때 팁 받기
                answer += tip;
        }
        bw.write(answer + "");	//받은 팁의 합 BufferedWriter 저장
        bw.flush();		//결과 출력
        bw.close();
        br.close();
    }
}
