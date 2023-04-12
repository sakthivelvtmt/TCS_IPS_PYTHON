# TCS_IPS_PYTHON
class Headsets:
    def __init__(self,name,brand,price,avail):
        self.name=name
        self.brand=brand
        self.price=price
        self.avail=avail

class Solution:
    def __init__(self,hlist):
        self.hlist=hlist
        
    def findTotalPriceForGivenBrand(self,sbrand):
        fprice=0
        for i in self.hlist:
            if i.brand==sbrand:
                fprice+=i.price
        if fprice == 0:
            return "No headset Found at this brand"
        else:
            return fprice
                
    def findAvailableHeadsetWithSecondMinPrice(self):
        lst=[]
        for i in self.hlist:
            if i.avail=='true':
                lst.append(i.price)
        lst.sort()
        for i in self.hlist:
            if lst!=[]:
                if i.price==lst[1]:
                    return i
            else:
                return 0
        
hlist=[]      
for i in range(int(input())):
    n=input()
    b=input().lower()
    p=int(input())
    a=input()
    temp=Headsets(n,b,p,a)
    hlist.append(temp)
    
obj=Solution(hlist)
br=input().lower()

res1=obj.findTotalPriceForGivenBrand(br)
res2=obj.findAvailableHeadsetWithSecondMinPrice()

print(res1)
if res2==0:
    print("No Headsets Found")
else:
    print(res2.name)
    print(res2.price)
