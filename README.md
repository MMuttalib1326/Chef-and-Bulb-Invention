# Chef-and-Bulb-Invention
Chef is trying to invent the light bulb that can run at room temperature without electricity. So he has N gases numbered from 0 to N−1 that he can use and he doesn't know which one of the N gases will work but we do know it.  Now Chef has worked on multiple search algorithms to optimize search. For this project, he uses a modulo-based search algorithm that he invented himself. So first he chooses an integer K and selects all indices i in increasing order such that imodK=0 and test the gases on such indices, then all indices i in increasing order such that imodK=1, and test the gases on such indices, and so on.  Given N, the index of the gas p that will work, and K, find after how much time will he be able to give Chefland a new invention assuming that testing 1 gas takes 1 day.  For example, consider N=5,p=2 and K=3.  On the 1st day, Chef tests gas numbered 0 because 0mod3=0. On the 2nd day, Chef tests gas numbered 3 because 3mod3=0. On the 3rd day, Chef tests gas numbered 1 because 1mod3=1. On the 4th day, Chef tests gas numbered 4 because 4mod3=1. On the 5th day, Chef tests gas numbered 2 because 2mod3=2. So after 5 days, Chef will be able to give Chefland a new invention



for _ in range (int(input())):
    n,p,k = input().split(' ')
    n=int(n)
    p=int(p)
    k=int(k)
    ans = 0
    a = p%k - 1
    b =((n-1)//k)*k
    b = n-1-b
    
    if(a>b):
        ans+= (b+1)*((n-1)//k + 1) + (a-b)*((n-1)//k)
    else:
        ans+= ((n-1)//k + 1)*(a+1)
    for i in range(a+1,n,k):
        ans+=1
        if (i==p):
            print(ans)
            break
