# Python_Scripts
#using python Built-in functions
def anagram(s1,s2):
    s1= s1.replace(' ','').lower()
    s2 = s2.replace(' ','').lower()
    return sorted(s1)==sorted(s2)
print(anagram('dog','god'))
print(anagram('clint eastwood','old west action'))

# Work around without the built-in functions
def anagram1(s1,s2):
    s1 = s1.replace(' ','').lower()
    s2 = s2.replace(' ','').lower()

    if len(s1)!=len(s2):
        return False
    count = {}

    for letter in s1:
        if letter in count:
            count[letter]+=1
        else:
            count[letter] = 1
    print("\n",count)
    for letter in s2:
        if letter in count:
            count[letter]-=1
        else:
            count[letter]=1
    for i in count:
        if count[i]!=0:
            return False
    return True
#print(anagram1('dog','god'))
print(anagram1('clint eastwood','old west action'))
