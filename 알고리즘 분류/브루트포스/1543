import java.io.*;

public class Main{
    public static void main(String[] args) throws IOException {
        //입력값 처리하는 BufferedReader
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        //결과값 출력하는 BufferedWriter
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
        String text = br.readLine();
        String word = br.readLine();
        //문서에 찾는 단어 1로 변경하기
        text = text.replaceAll(word, "1");
        int answer = 0;
        //1의 개수 구하기
        for(int i=0;i<text.length();i++){
            if(text.charAt(i) == '1')
                answer++;
        }
        bw.write(answer + "");	//1의 개수 BufferedWriter 저장
        bw.flush();		//결과 출력
        bw.close();
        br.close();
    }
}
