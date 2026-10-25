# 실습과제 #1 : 영화 보드 완성판
- 이름 / 학번 : 김기송 / 2551005
- 사이트 주소 : https://kimkisongasd7-droid.github.io/web-hw1/
- 사용한 API 1 : TMDB (포스터, 영화 정보)
1. <img class="poster" src="https://image.tmdb.org/t/p/w342/5TMyytCI5Pfc9c1eNsljiCdiB05.jpg" alt="극장판 치이카와: 인어 섬의 비밀 포스터">
2. <img class="poster" src="https://image.tmdb.org/t/p/w342/w5OX3u2SpMVRU0sol0mtIaf4LSI.jpg" alt="타짜: 벨제붑의 노래 포스터">
3. <img class="poster" src="https://image.tmdb.org/t/p/w342/uL4cIrNi2uaUnWIOQQ28EVnkETG.jpg" alt="클레이페이스 포스터">
4. <img class="poster" src="https://image.tmdb.org/t/p/w342/8Qybglcd5IqksU7rNRvpvodtrpQ.jpg" alt="실낙원 포스터">
5. <img class="poster" src="https://image.tmdb.org/t/p/w342/mCUZLymzVjfYJXEON4wg8ilx2H8.jpg" alt="암살자(들) 포스터">
6. <img class="poster" src="https://image.tmdb.org/t/p/w342/gDN2NWtHbs8ZWEBQM8Dh5OVXdb4.jpg" alt="인터스텔라 포스터">
7. <img class="poster" src="https://image.tmdb.org/t/p/w342//e7ABYg2KnI0QBBYSrLYiTljtmpd.jpg" alt="미션 임파서블 포스터">
8. <img class="poster" src="https://image.tmdb.org/t/p/w342//s2426EIW0arpjN0R0qErJfXQxZD.jpg" alt="미션 임파서블: 로그네이션">
9. <img class="poster" src="https://image.tmdb.org/t/p/w342/iNJsojTGQoOWL9f9U23jsibONVu.jpg" alt="미션 임파서블: 파이널 레코닝">
10. <img class="poster" src="https://image.tmdb.org/t/p/w342/5jnoAA74Qwb5w6B9FMvnc20n6Ie.jpg" alt="미션 임파서블: 폴아웃">
- 사용한 API 2 : KOBIS 일별 박스오피스 (기준일 2026-10-24)

## 구현 항목 체크
- [ok] 1. CSS 변수: style.css 맨 위 :root에 색 5개 이상, 글꼴 2개(구글 폰트), 간격 1개. 글자색, 배경색,
테두리색은 모두 var()로 씁니다(그림자와 오버레이의 반투명 검정 rgba(0, 0, 0, ...)은 예외).

- [ok]2. 섹션 2개: <section id="mine"> 내 인생 영화 5편, <section id="boxoffice"> 일별 박스오피스 TOP
5(기준일 표시). 섹션마다 <h2>, 카드 제목은 <h3>.

- [ok]3. 카드 10장의 포스터: TMDB 포스터 w342, alt에 "제목 포스터". 포스터가 없는 영화는 대체 표지.

- [ok]4. 박스오피스 배지: 순위 배지 .rank(왼쪽 위), 누적 관객 수(천 단위 콤마, "명"), 순위
변동 .up, .down, .new(::before로 ▲, ▼, NEW와 색).

- [ok]5. 6주차 효과 유지: 평점 배지 .badge(오른쪽 위), :hover에서 0.3초 동안 8px 떠오르고 노란빛 그림자가
생김.

- [ ]6. 보드 격자: display: grid, 폭 360px 1열, 768px 2열, 1280px 4열. 미디어 쿼리 2개(min-width: 600px, minwidth: 1024px)가 각각 눈에 보이는 변화를 만듦. 360px에서 가로 스크롤 없음.
360px에서 가로스크롤 없음아 무엇을 말하는지 모르겠습니다...

- [ok]7. 헤더: flex로 제목 왼쪽, 내비 오른쪽. 내비 링크 3개(#mine, #boxoffice, detail.html). 본문 max-width:
1100px 가운데 정렬.

- [ok]8. 히어로: backdrop_path의 w1280 배경 + 어두운 그라데이션 오버레이, 제목과 한 줄 소개.

- [ok]9. 상세 페이지 detail.html: 내 인생 영화 1편. 600px 이상에서 2단 grid(왼쪽 포스터 w500, 오른쪽 <dl>에
제목, 원제, 개봉일, 평점, 줄거리 전문), 배경에 backdrop_path 오버레이, "보드로 돌아가기" 링크,
헤더와 푸터는 index.html과 같음.

- [ok]10. 캡처 3장: w360.png, w768.png, w1280.png(디바이스 모드, 저장소 루트).

- [ok]11. 푸터(두 쪽 모두): TMDB 고지 두 줄 + KOBIS 출처와 기준일.

- [ok]12. 검증과 README: W3C 검증기에서 두 쪽 모두 Error 0, README는 아래 양식대로. 

## 어려웠던 점 3가지와 해결
1. <p class="change up">2</p> 부분에서 이 구문이뜻하는 바를 몰라서 제미나이에게 물어봄. 순위변동에대한 부분이라는 답변을 받고 이어갔으나 바로 뒤에 과제 안내서 pdf에서 이 부분에 대하여 자세이 설명되어있음을 보고 좀 더 고민해보고 찾아봐야겠다는 생각을 함.
2. 상세 페이지 부분에서 dt와 dd의 줄 정렬이 되지 않아 제미나이를 통해 알아봤으나 잘 이해를 못함. 최후의 수단으로 코드도 받아 사용해봤으나 달라지는 부분이 없어 포기.
3. 박스오피스 부분에서 카드 왼쪽 위에 빨간색으로 순위가 표시되는 부분에서 안내서에는 나오지 않는 부분이라 당황했으나 전 주차에 평점부분을 참고하여 해결.
4. 상세페이지 부분에서 dt부분을 파랗게 나오게 하는 부분이 안내서 pdf에는 없어 해결하기까지 시간이 좀 걸림. detail과 dt를 조합하여 css에서 해결하는거까진 생각했지만 중간에 - 없이 그냥 한칸띄고 적어야 한다는걸 깨닫기까지 오랜 시간이 걸림.

## 참고한 자료 (교재 절, MDN 페이지 제목, 검색어)
교재와 생성형 ai참고
## 생성형 AI 사용 내역 (없으면 "없음")
1. 
- 질문 요지 : <p class="change up">2</p> 이 구문이 뜻하는 바는 무엇인가?
- 답변 요약 : 위 구문은 순위 변동을 나타내는 부분으로 rankInten 부분을 참고.
- 채택 여부 : O

2. 
- 질문 요지 : 상세페이지에서 제목과 인터스텔라 부분이 정렬이되어 끝부분이 맞춰지면 좋겠는데 이부분은 어떻게 해결하는게 좋겠는가?
- 답변 요약 : 내용과 라벨의 시작점이나 끝선을 완벽하게 딱 맞추고 싶다면, dt 요소에 고정 너비(width)를 주거나 Grid 레이아웃을 사용해 라벨 영역과 내용 영역의 칸을 딱 나누어 주어야 합니다.
- 채택 여부 : x (ai의 지시를 따라 해보고 발전이 없어 코드를 받기까지 했지만 해결불가...)