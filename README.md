# stock-prices
# The stock price in seconds is recorded in prices and the period during which the price does not fall is listed in each second. 초단위의 주식가격이 prices에 기록되어있고 가격이 떨어지지 않는 기간이 각초에 리스트로 나타내기
# python
def solution(prices):
    p=len(prices)
    answer=[0]*len(prices) #리스트안을 0으로 초기화
    for i in range(p):   #리스트안에 있는 i가 처음부터 끝까지 돌아감
        for j in range(i+1,p):  #j는 p번 다음 숫자를 비교 
            answer[i]+=1
            if prices[i]>prices[j]: #위에서 1을 더해 나갔기 때문에 뒤에 숫자가 앞의 숫자보다 크다면 바로 break해야됨
                break
    return answer
prices=[1,2,3,2,3]
a=solution(prices) 
print(a)
# result--> [4,3,1,1,0]
