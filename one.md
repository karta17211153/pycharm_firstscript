# pycharm_firstscript

# 77
# split
string1 = "My deliverable is due in May"
string1_list1 = string1.split() #將字串做分割的動作
string1_list2 = string1.split(" ", 2) #以一個空格為基準做3個區塊的分割:(0,1,2)
print("Output #21: {0}".format(string1_list1))
print("{0}".format(string1_list2))
print("Output #22: FIRST PIECE:{0} SECOND PIECE:{1} THIRD PIECE:{2}"\
.format(string1_list2[0], string1_list2[1], string1_list2[2]))

# 93
# strip
string3 = "   Remove unwanted characters from this string\t\t    \n"
print("Output #26: string3: {0:s}".format(string3)) #原始字串(有多餘的空白、tab、換行)
string3_lstrip = string3.lstrip() #移除字串左側的字元(默認為空格)
print("Output #27: lstrip: {0:s}".format(string3_lstrip))
string3_rstrip = string3.rstrip() #移除字串右側的字元(默認為空格)
print("Output #28: rstrip: {0:s}".format(string3_rstrip))
string3_strip = string3.strip() #移除字串中指定的字元(默認為空格)
print("Output #29: strip: {0:s}".format(string3_strip))

# 130
# REGULAR EXPRESSIONS / PATTERN MATCHING
# Count the number of times a pattern appears in a string
string = "The quick brown fox jumps over the lazy dog."
string_list = string.split()
pattern = re.compile(r"The", re.I) #利用compile檢查並尋找"The"這個字元
count = 0 #將出現次數的變數歸零
for word in string_list:
    if pattern.search(word): #在字串中如果與欲檢查的字元相符
    	count += 1 #出現次數累加一次
print("Output #38: {0:d}".format(count))

# 178
# Create a string with a specific format from a date object
today = date.today()
print(today) #原始日期形式:2018-XX-XX
print("Output #50: {:s}".format(today.strftime('%m/%d/%Y'))) #強制形式:月/日/年
print("Output #51: {:s}".format(today.strftime('%b %d, %Y'))) #強制形式:月份簡寫 日,年
print("Output #52: {:s}".format(today.strftime('%Y-%m-%d'))) #強制形式:年-月-日
print("Output #53: {:s}".format(today.strftime('%B %d, %Y'))) #強制形式:月份完整寫法 日,年

# 202
# LISTS
# Use square brackets to create a list
# len() counts the number of elements in a list
# max() and min() find the maximum and minimum numbers in numeric lists
# count() counts the number of times a value appears in a list
a_list = [1, 2, 3]
print("Output #58: {}".format(a_list))
print("Output #59: a_list has {} elements.".format(len(a_list))) #計算list裡的元素長度
print("Output #60: the maximum value in a_list is {}.".format(max(a_list))) #尋找list中最大的元素
print("Output #61: the minimum value in a_list is {}.".format(min(a_list))) #尋找list中最小的元素
another_list = ['printer', 5, ['star', 'circle', 9]] #只要是,隔開便是一個元素
print("Output #62: {}".format(another_list))
print("Output #63: another_list also has {} elements.".format(len(another_list))) #計算list裡的元素長度
print("Output #64: 5 is in another_list {} time.".format(another_list.count(5))) #計算括號裡的元素出現次數

# 217
# Use list indices to access specific values in a list
# [0] is the first value; [-1] is the last value
a_list = [1, 2, 3]
another_list = ['printer', 5, ['star', 'circle', 9]]
print("Output #65: {}".format(a_list[0])) #第一個元素
print("Output #66: {}".format(a_list[1])) #第二個元素
print("Output #67: {}".format(a_list[2])) #第三個元素
print("Output #68: {}".format(a_list[-1])) #從最後數的第一個元素(也就是最後一個)
print("Output #69: {}".format(a_list[-2])) #從最後數的第二個元素
print("Output #70: {}".format(a_list[-3])) #從最後數的第三個元素
print("Output #71: {}".format(another_list[2]))
print("Output #72: {}".format(another_list[-1]))

# 254
# Use append() to add additional values to the end of the list
# Use remove() to remove specific values from the list
# Use pop() to remove values from the end of the list
a_list = [1,2,3]
a_list.append(4) #append >> 增加新的元素(從原list最後面開始加入)
a_list.append(5)
a_list.append(6)
print("Output #83: {}".format(a_list))
a_list.remove(5) #remove >> 移除指定的元素
print("Output #84: {}".format(a_list))
a_list.pop() #pop >> 從原list最後面開始移除元素
a_list.pop() #pop兩次:移除兩次最後面的元素
print("Output #85: {}".format(a_list))

# 284
# Use sorted() to sort a collection of lists by a position in the lists
my_lists = [[1,2,3,4], [4,3,2,1], [2,4,1,3]]
my_lists_sorted_by_index_3 = sorted(my_lists, key=lambda index_value:index_value[1]) #lambda >> 定意函式的參數，比較利用index的位置判斷進行排序的動作(由小到大)
print("Output #91: {}".format(my_lists_sorted_by_index_3))

# 289
# Use itemgetter() to sort a collection of lists by two index positions
my_lists = [[123,2,2,444], [22,6,6,444], [354,4,4,678], [236,5,5,678], \
[578,1,1,290], [461,1,1,290]] #利用"\"將過長的字串結合起來(視覺上不會過於壟長)
my_lists_sorted_by_index_3_and_0 = sorted(my_lists, key=itemgetter(3,0)) #利用itemgetter獲得第3index與第0index進行排序，意思即先抓出3index先做比較，如果組中的該元素一樣大，再抓出0index做比較，來進行排序
print("Output #92: {}".format(my_lists_sorted_by_index_3_and_0))

# 314
# Convert tuples to lists and lists to tuples
my_list = [1, 2, 3] #list
my_tuple = ('x', 'y', 'z') #元組
print("Output #100: {}".format(tuple(my_list))) #list轉元組
print("Output #101: {}".format(list(my_tuple))) #元組轉list
