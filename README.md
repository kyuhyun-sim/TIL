# Troubleshooting
항해 6주차부터는 매니저님의 추천으로 README에 troubleshooting을 작성해 보려고 한다.
앞으로 Til 파일이 아닌 이곳에다가 프로젝트를 진행 중 troubleshooting을 한 내역들을 적어보려고 한다.

## 1대N 매핑시 순환참조 오류
게시글 테이블과 댓글 테이블을 1대N, N대1로 매핑할시 순환 참조하는 오류가 발생했다.
처음에는 @JsonIgnore를 걸어주어 순환참조를 방지했지만, 매핑에 대해 추가적으로 알아봄으로서 1대N, N대1 매핑에는 그보다 일반적으로 @JsonManagedReference와 @JsonBackReference를 각각 
부모클래스(연관관계의 반대편)와 자식클래스(연관관계의 주인으로 FK를 가지고 있는 쪽)에 걸어주면 된다는걸 알게 되었다.

## Cors 오류
처음 프론트엔드와 협업을 하며 발생한 문제로 클라이언트에서 정보를 보냈지만 서버쪽에 request가 제대로 전해지지 않았다.
검색을 통해 해당 문제를 찾아보니 개발자라면 흔히 접하게 되는 Cors 문제라고 한다.
임시로 모두 허용해주게 하였는데 이 Cors 제약조건에 의해  authorization을 무조건 명시해야만 된다는 걸 알게 되었다.

## 깃허브 공유시 properties 파일은 ignore 해야한다.
매니저님의 피드백을 통해 알게 된 사실로 properties의 아이디와 비밀번호를 다른 사람이 악용할수 있게 되기에 ignore 처리를 해주어야 한다고 한다.
이제와 properties를 날려버린다해도 이전까지의 커밋내역들에 정보가 남겨져 있기 때문에 5주차 프로젝트는 레포를 날려버리기로 했다.
