# 1 Operations for the right sum-try
def solution(m, n, num): 
 maxNum = sum([i + 1 for i in range(m)]) + m * (n - 1) 
 minNum = sum([i + 1 for i in range(m)]) + 1 * (n - 1) 
 if num < minNum or num > maxNum: 
 return "false" 
 # corner case 
 if n == 1: 
 if num == maxNum: 
 return "D" * (m - 1) 
 else: 
 return "" 
 if m == 1: 
 if num == minNum: 
 return "R" * (n - 1) 
 else: 
 return "" 
   diff = num - minNum 
 # move one "D" to the first 
 minus = n - 1 
 # count how many 
 move = diff // minus 
 # count residue, 1 or 0 
 single = int((diff % minus + minus - 1) / minus) 
 ans = "D" * move + "R" * (n - 1 - diff % minus) + "D" * single + "R" * (diff % minus) + "D" * ( 
 m - 1 - move - single) 
 return ans 
 f = open('/Users/zhaochen/Desktop/output_question_1.txt','w') 
 print(solution(9,9,65),file = f) 
 print(solution(9,9,72),file = f) 
 print(solution(9,9,90),file = f) 
 print(solution(9,9,110),file = f) 
 print(solution(90000,100000,87127231192),file = f) 
 print(solution(90000,100000,5994891682),file = f) 
 f.close() 
