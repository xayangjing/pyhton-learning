for i in range(arr_length - 1):
	# firs round compare metas and move bigger one to end of list
	print 'Compare round %s' % (i+1)
	# print 'Start compare arr %s : %s ' % (arr[i+1], arr[i])
	#

	for j in range(arr_length - 1 - i):
		# 2）对每一对相邻元素作同样的工作，从开始第一对到结尾的最后一对。这步做完后，最后的元素会是最大的数。
		#
		# 3）针对所有的元素重复以上的步骤，除了最后一个。
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
