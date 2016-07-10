# coding=utf-8

# 冒泡排序（Bubble Sort）也是一种简单直观的排序算法。它重复地走访过要排序的数列，一次比较两个元素，如果他们的顺序错误就把他们交换过来。走访数列的工作是重复地进行直到没有再需要交换，也就是说该数列已经排序完成。这个算法的名字由来是因为越小的元素会经由交换慢慢“浮”到数列的顶端。
#
# 算法步骤：
#
# 1）比较相邻的元素。如果第一个比第二个大，就交换他们两个。
#
# 2）对每一对相邻元素作同样的工作，从开始第一对到结尾的最后一对。这步做完后，最后的元素会是最大的数。
#
# 3）针对所有的元素重复以上的步骤，除了最后一个。
#
# 4）持续每次对越来越少的元素重复上面的步骤，直到没有任何一对数字需要比较。

arr = [6, 5, 4, 3, 2, 1]

seq_number = 0
arr_length = len(arr)


#  print meta of list

print 'Original arr is : %s' %arr

print 'arr length is : %s' %arr_length

# print sequence numbers one by one

# while seq_number < arr_length:
# 	print seq_number
# 	seq_number += 1


# print all numbers in arr

# while seq_number < arr_length:
# 	# print seq_number
# 	print 'arr %s is: %s' %(seq_number,arr[seq_number])
# 	seq_number += 1

# first round

# use range to replace 'while script' to create sequence numbers

# seq_number = 0
# while seq_number < arr_length:
# 	print seq_number
# 	seq_number += 1

# use range to replace 'while script' to create sequence numbers

# for i in range(arr_length):
# 	print 'arr %s is: %s ' %(i, arr[i])

# 比较相邻的元素。如果第一个比第二个大，就交换他们两个。



# for i in range(arr_length - 1):
# 	# firs round compare metas and move bigger one to end of list
# 	print 'Start compare arr %s : %s ' % (arr[i+1], arr[i])
# 	if arr[i] > arr[i+1]:
# 		print '%s is smaller than %s' %(arr[i+1], arr[i])
# 		print 'move %s to next' % arr[i]
# 		arr[i], arr[i+1] = arr[i+1], arr[i]
# 	else:
# 		print '%s is smaller than %s, %s won`n move' %(arr[i], arr[i+1], arr[i])
#
# 	print 'First round compare result: %s' % arr

# C:\Python27\python.exe C:/Users/jyang3/PycharmProjects/python10/bubblestore.py
# arr length is : 6
# Original arr is : [5, 6, 4, 1, 2, 3]
# Start compare arr 6 : 5
# 5 is smaller than 6, 5 won`n move
# First round compare result: [5, 6, 4, 1, 2, 3]
# Start compare arr 4 : 6
# 4 is smaller than 6
# move 6 to next
# First round compare result: [5, 4, 6, 1, 2, 3]
# Start compare arr 1 : 6
# 1 is smaller than 6
# move 6 to next
# First round compare result: [5, 4, 1, 6, 2, 3]
# Start compare arr 2 : 6
# 2 is smaller than 6
# move 6 to next
# First round compare result: [5, 4, 1, 2, 6, 3]
# Start compare arr 3 : 6
# 3 is smaller than 6
# move 6 to next
# First round compare result: [5, 4, 1, 2, 3, 6]

# 增加处理剩余序列

# for i in range(arr_length - 1):
# 	# firs round compare metas and move bigger one to end of list
# 	print 'Compare round %s' % (i+1)
# 	# print 'Start compare arr %s : %s ' % (arr[i+1], arr[i])
# 	#
#
# 	for j in range(arr_length - 1):
# 		# 2）对每一对相邻元素作同样的工作，从开始第一对到结尾的最后一对。这步做完后，最后的元素会是最大的数。
# 		#
# 		# 3）针对所有的元素重复以上的步骤，除了最后一个。
# 		#
# 		# 4）持续每次对越来越少的元素重复上面的步骤，直到没有任何一对数字需要比较。
# 		if arr[j] > arr[j+1]:
# 			# 1）比较相邻的元素。如果第一个比第二个大，就交换他们两个。
# 			# print '%s is smaller than %s' %(arr[j+1], arr[j])
# 			# print 'move %s to next' % arr[i]
# 			arr[j], arr[j+1] = arr[j+1], arr[j]
# 		else:
# 			print '%s is smaller than %s, %s won`n move' %(arr[j], arr[j+1], arr[j])
#
# 		print '%s round compare result: %s' % (j+1, arr)


#  代码优化

for i in range(arr_length - 1):
	# firs round compare metas and move bigger one to end of list
	print 'Compare round %s' % (i+1)
	# print 'Start compare arr %s : %s ' % (arr[i+1], arr[i])
	#

	for j in range(arr_length - 1 - i):
		# 2）对每一对相邻元素作同样的工作，从开始第一对到结尾的最后一对。这步做完后，最后的元素会是最大的数。
		#
		# 3）针对所有的元素重复以上的步骤，除了最后一个。
		#    代码优化关键：因为最大的数值已经在第一次排序的时候移动到了序列末端，所以后续比较只需要需要比较n-1 长度的序列。，可以通过增加-i 来实现获得剩余序列。
		#
		# 4）持续每次对越来越少的元素重复上面的步骤，直到没有任何一对数字需要比较。
		if arr[j] > arr[j+1]:
			# 1）比较相邻的元素。如果第一个比第二个大，就交换他们两个。
			# print '%s is smaller than %s' %(arr[j+1], arr[j])
			# print 'move %s to next' % arr[i]
			arr[j], arr[j+1] = arr[j+1], arr[j]
		else:
			print '%s is smaller than %s, %s won`n move' %(arr[j], arr[j+1], arr[j])

		print '%s round compare result: %s' % (j+1, arr)
