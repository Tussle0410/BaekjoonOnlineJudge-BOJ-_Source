import java.io.*;
import java.util.ArrayList;
import java.util.PriorityQueue;
import java.util.StringTokenizer;
public class Main {
    //현재 도시 정보 및 비용 관련 클래스
    static class info implements Comparable<info>{
        int node, value;
        public info(int node, int value){
            this.node = node;
            this.value = value;
        }

        //비용 관련 오름차순 정렬
        @Override
        public int compareTo(info o) {
            return this.value - o.value;
        }
    }
    public static void main(String[] args) throws IOException{
        //입력값 처리하는 BufferedReader
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        //결과값 출력하는 BufferedWriter
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
        int N = Integer.parseInt(br.readLine());
        int M = Integer.parseInt(br.readLine());
        StringTokenizer st;
        ArrayList<ArrayList<info>> graph = new ArrayList<>();
        for(int i=0;i<=N;i++)
            graph.add(new ArrayList<>());
        //버스에 대한 정보 그래프 형태로 저장!
        for(int i=0;i<M;i++){
            st = new StringTokenizer(br.readLine()," ");
            int s = Integer.parseInt(st.nextToken());
            int e = Integer.parseInt(st.nextToken());
            int value = Integer.parseInt(st.nextToken());
            graph.get(s).add(new info(e, value));
        }
        st = new StringTokenizer(br.readLine()," ");
        int s = Integer.parseInt(st.nextToken());
        int e = Integer.parseInt(st.nextToken());
        int answer = search(s, e, graph, N);	//최단 거리 탐색
        bw.write(answer + "");	//최단 거리 BuffredWriter 저장
        bw.flush();		//결과 출력
        bw.close();
        br.close();
    }
    //BFS에서 PriorityQueue를 이용해서 최단거리 탐색 진행하는 함수
    static int search(int start, int end, ArrayList<ArrayList<info>> graph, int size){
        PriorityQueue<info> pq = new PriorityQueue<>();
        boolean[] visited = new boolean[size+1];
        pq.add(new info(start, 0));	//시작 도시 저장!
        //최단 거리 탐색
        while(!pq.isEmpty()){
            info cur = pq.poll();
            if(cur.node == end)	//최초 목적 도시 도착!
                return cur.value;
            visited[cur.node] = true;	//현재 도시 방문!
            //버스 경로 탐색!
            for(info next : graph.get(cur.node)){
                if(!visited[next.node])	//방문하지 않았던 도시일 때
                    pq.add(new info(next.node, cur.value + next.value));
            }
        }
        return -1;		//해당 도시에 도달하지 못할 때
    }
}
