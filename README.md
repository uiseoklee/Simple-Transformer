# Simple-Transformer

Q = (B, M, H) -> (B, M, N, K) -> (B, N, M, K)

K = (B, M, H) -> (B, M, N, K) -> (B, N, M, K)

V = (B, M, H) -> (B, M, N, K) -> (B, N, M, K)

SCORE = Q * K(T) -> (B, N, M, K) * (B, N, K, M) -> (B, N, M, M)

PROB = SCORE/루트(K) -> (B, N, M, M) -> 텐서사이즈에 변화없음

ATTN = PROB * V = (B, N, M, M) * (B, N, M, K) -> (B, N, M, K)

단,

B = 배치사이즈

M = 토큰 개수

H = 토큰을 표현하는 벡터 사이즈

N = 멀티헤드개수

K = H/N(항상 H가 나눠 떨어지도록 N을 설정해야 함. 즉 K는 항상 정수)

K(T) = 행렬 Transpose 연산. K의 마지막 두 차원의 순서를 바꾼 벡터

ATTN = 어텐션 결과


*출처: 도서<안녕, 트랜스포머 / 이진기 저>
