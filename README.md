
def max_distance(str,n):
    c=[0]*256
    for i in range(n):
        c[ord(str[i])]+=1
    max_len=0
    for i in range(256):
        if(c[i]!=0):
            max_len+=1
    return max_len
def substr(str):
    n=len(str)
    max_len1=max_distance(str,n)
    min_len=n
    for i in range(n):
        for j in range(n):
            sub_str=str[i:j]
            sub_len=len(sub_str)
            distinct_char=max_distance(sub_str,sub_len)
            if(sub_len<min_len and max_len1==distinct_char):
                min_len=sub_len
    return min_len
str="aabbcda"
res=substr(str)
print(res)
