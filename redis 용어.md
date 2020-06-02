RPUSH : 목록 끝에 새 요소를 넣습니다.
RPUSH friends "Alice"
RPUSH friends "Bob"

LPUSH : 목록 시작 부분에 새 요소를 넣습니다.
LPUSH friends "Sam"

LLEN

LRANGE : 목록의 하위 세트 제공. 첫번째요소의 색인과 두번째 매개변수로 검색하려는 마지막 요소의 색인을 사용
두 번째 매개 변수의 값 -1은 목록이 끝날 때까지 요소를 검색하는 것을 의미하고 -2는 최대 한도까지 포함하는 등을 의미합니다.
LRANGE friends 0 -1 => 1) "Sam", 2) "Alice", 3) "Bob"
LRANGE friends 0 1 => 1) "Sam", 2) "Alice"
LRANGE friends 1 2 => 1) "Alice", 2) "Bob"

LPOP : Redis 목록의 기본 기능은 목록의 머리 부분이나 꼬리 부분의 요소를 제거하고 동시에 클라이언트로 되돌리는 기능입니다.
목록에서 첫 번째 요소를 제거하고 리턴합니다.
LPOP friends => "Sam"

RPOP : 목록에서 마지막 요소를 제거하고 반환합니다.
RPOP friends => "3"

RPOP 키
시간 복잡성 : O (1)

DESCRIPTION : 목록의 첫 번째 (LPOP) 또는 마지막 (RPOP) 요소를 원자 적으로 리턴하고 제거합니다. 예를 들어 목록에 "a", "b", "c"요소가 포함 된 경우 LPOP는 "a"를 반환하고 목록은 "b", "c"가됩니다.

경우 키가 존재하지 않거나 목록이 이미 특수 값 '전무'을 비어 반환됩니다.

반환 값 : 대량 회신.