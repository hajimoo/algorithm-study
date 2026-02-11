Lambda & map(Python) 
 <br />  Lambda: 정렬 key로 자주 사용

함수로 key 지정<br />

array = [('홍길동', 50), ('이순신', 32), ('아무도', 74)]<br />
def my_key(x):
    return x[1]<br />
print(sorted(array, key=my_key))<br />

lambda로 축약<br />
print(sorted(array, key=lambda x: x[1]))

사용 기준:
재사용 필요 없음 → lambda
재사용 필요<br />가독성 중요 → 함수

map: 여러 리스트에 함수 적용<br />
list1 = [1,2,3,4,5]
<br />
list2 = [6,7,8,9,10]
<br />
result = map(lambda a, b: a + b, list1, list2)
<br />
print(list(result))
<br />
map은 “각 원소에 함수 적용”할 때 유용
