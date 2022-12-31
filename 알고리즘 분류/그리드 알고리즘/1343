import java.io.*;

public class Main{
    static StringBuilder answer = new StringBuilder();
    public static void main(String[] args) throws IOException{
        //입력값 처리하는 BufferedReader
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        //결과값 출력하는 BufferedWriter
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
        String str = br.readLine();
        int count = 0;
        //보드의 각 글자 탐색
        for(int i=0;i<str.length();i++){
            char temp = str.charAt(i);
            if(temp == 'X')	//'X'일 때 연속된 개수 더하기!
                count++;
            else{	//'.'일 때 지금까지 연속된 'X'의 개수에 따라 덮어쓰기 진행!
                if(!check(count))		//폴리오미노로 덮어쓰기 불가능시 종료
                    break;
                answer.append(".");
                count = 0;	//연속된 개수 0으로 초기화
            }
        }
        //마지막 글자가 'X'로 끝날 때 남은 연속된 개수 폴리오미노로 덮기
        if(!answer.equals("-1") && str.charAt(str.length()-1) == 'X')
            check(count);
        bw.write(answer.toString());	//결과 BufferedWriter 저장
        bw.flush();		//결과 출력
        bw.close();
        br.close();
    }
    //폴리오미노 덮기 진행하는 함수
    static boolean check(int count){
        String A = "AAAA", B = "BB";	//폴리오미노 정보
        if(count % 4 == 0){	//4의 배수로 떨어질 때 "AAAA"만 사용!
            for(int j=0;j<count/4;j++)
                answer.append(A);
        }else if(count % 4 == 2){	//"AAAA"을 최대한 사용한 뒤 남은 칸 "BB"로 덮기
            for (int j = 0; j < count / 4; j++)
                answer.append(A);
            answer.append(B);
        }else if(count == 2)	//연속된 개수가 2개일 때 "BB" 한 번 사용
            answer.append(B);
        else {		//폴리오미노로 덮을 수 없을 때
            answer = new StringBuilder("-1");
            return false;
        }
        return true;
    }
}
