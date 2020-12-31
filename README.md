## Python 练习册，每天一个小程序 ##
**第一题**求一个数中数字的和:
def main():
    
    while True:
        a = int(input("任意输入一个数:"))
        sum = 0
        for i in range(len(a)):
            sum = sum + int(a[i])
        print('{}'.format(sum))

if __name__ == '__main__':

    main()
   
**第二题**在列表中按规定去除重复的内容：


def main():
    
    list = [1, 2, 1, 2, 1, 1, 1]
    for i in list[::]:    #切片
        if i == 1:  #去除重复出现的1或者可以list1 = [i for i in list if i != 1]
            list.remove(i)
	    #list1 = set（list）#去除重复出现的项。
    print(list)
    
if __name__ == '__main__':

    main()
    
**第三题**判断一个数是否为素数：

def main():
    
    while True:
        x = int(input("请输入一个数:"))
        if x < 2:
            print("{}不是素数".format(x))
            continue
        if x == 2:
            # print("%d是最小的素数！！！"% (x))
            print('{}是最小的素数！！！'.format(x))
        i = 2
        while i < x:
            if x % i == 0:
                print('{}不是素数'.format(x))
                break
            i += 1
        else:
            print('{}是素数'.format(x))
if __name__ == '__main__':

    main()
    
 **第四题**计算最大公约数：
 
 def gys(a, b):
 
 
    if a > b:

        smaller = b
    else:
        smaller = a
    for i in range(1, smaller+1):
        if (a % i == 0) and (b % i == 0):

            gys = i
    return gys

while True:
    
    num1 = int(input("请随意输入第一个数:"))
    num2 = int(input("请随意输入第二个数:"))
    print(num1, "和", num2, "的最大公约数为", gys(num1, num2))
    
**第五题**线性查找：

def sequential_search(lis, val):
    
    length = len(lis)
    for i in range(length):
        if lis[i] == val:
            return i
    else:
        return -1

if __name__ == '__main__':
    
    LIST = [1, 2, 5, 6, 3, 8, 9, 16]
    print(sequential_search(LIST, 2))
    
**第六题**折半查找：

def binary_search(lis, key):

    low = 0
    high = len(lis) - 1
    time = 0
    while low < high:
        time += 1
        mid = int((low + high) / 2)
        if key < lis[mid]:
            high = mid - 1
        elif key > lis[mid]:
            low = mid + 1
        else:
            # 打印折半的次数
            print("times: %s" % time)
            return mid
    print("times: %s" % time)
    return False


if __name__ == '__main__':

    LIST = [1, 5, 7, 8, 22, 54, 99, 123, 200, 222, 444]
    result = binary_search(LIST, 99)
    print(result)
    
    
    
    
**第七题**选择排序：
A = [64, 25, 12, 22, 11]

for i in range(len(A)):

    for j in range(i + 1, len(A)):
        if A[i] < A[j]:#从大到小，改变符号则相反，
            i = j

    A[i], A[i] = A[i], A[i]

print("排序后的数组：{}".format(A))

**第八题**递归求和，求阶乘：
def sum_recu(n):

    '''
    1 to n,The sum function
    '''
    if n <= 0:
        return 1
    else:
        return n * sum_recu(n - 1)#调用函数自身

print("递归求和：",sum_recu(4))


阶乘：
def fact(n):

    if n == 1:
        return 1
    return n * fact(n - 1)
    
print(fact(4))
