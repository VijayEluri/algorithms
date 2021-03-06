##Pesudocodes of the Alogrithms :

#I List of sorting algorithms with complexity O( n^2 )

#0. Bubble Sort :

		repeat
			hasChanged := false
			decrement itemCount
			repeat with index from 1 to itemCount
			if (item at index) > (item at (index + 1))
				swap (item at index) with (item at (index + 1))
            hasChanged := true
		until hasChanged = false

#1. Insertion Sort :

		function insertionSort(array A)
			for i from 1 to length[A]-1 do
				value := A[i] 
				j := i-1
				while j >= 0 and A[j] > value do
					A[j+1] := A[j]
					j := j-1
				done
				A[j+1] = value
		done

#2. Selection Sort :

		function selectionSort(array A)
			max = length(A) - 1

			for i from 0 to max
				key = A[i]
				keyj = i

				for j from i+1 to max
				 if A[j] < key
						key = A[j]
						keyj = j

			 lst[keyj] = A[i]
			 lst[i] = key
		 done
	

## II Algorithms with complexity as O(n log n) 

#0. Heap Sort :

		function heapSort(a, count) is
		input: an unordered array a of length count
 
		(first place a in max-heap order)
		heapify(a, count)
 
		end := count - 1
		while end > 0 do
			(swap the root(maximum value) of the heap with the
			last element of the heap)
			swap(a[end], a[0])
			(put the heap back in max-heap order)
			siftDown(a, 0, end-1)
			(decrement the size of the heap so that the previous
			max value will stay in its proper place)
		end := end - 1
 
		function heapify(a,count) is
		(start is assigned the index in a of the last parent node)
		start := (count - 2) / 2
   
		while start ≥ 0 do
			 (sift down the node at index start to the proper place
			such that all nodes below the start index are in heap
			order)
			siftDown(a, start, count-1)
			start := start - 1
		(after sifting down the root all nodes/elements are in heap order)
 
		function siftDown(a, start, end) is
		(end represents the limit of how far down the heap to sift)
		root := start

		while root * 2 + 1 ≤ end do       (While the root has at least one child)
			child := root * 2 + 1           (root*2+1 points to the left child)
			(If the child has a sibling and the child's value is less than its sibling's...)
			if child + 1 ≤ end and a[child] < a[child + 1] then
				child := child + 1           (... then point to the right child instead)
			if a[root] < a[child] then     (out of max-heap order)
				swap(a[root], a[child])
				root := child                (repeat to continue sifting down the child now)
			else
				 return

# 1. Merge Sort:

		function mergesort(m)
		var list left, right, result
		if length(m) ≤ 1
			return m
		else
			 var middle = length(m) / 2
			for each x in m up to middle - 1
				add x to left
			for each x in m at and after middle
				add x to right
			left = mergesort(left)
			right = mergesort(right)
			if last(left) ≤ first(right) 
				append right to left
				return left
			result = merge(left, right)
			return result

		function merge(left,right)
		var list result
		while length(left) > 0 and length(right) > 0
			if first(left) ≤ first(right)
				append first(left) to result
				 left = rest(left)
			 else
				append first(right) to result
				right = rest(right)
		if length(left) > 0 
			append rest(left) to result
		if length(right) > 0 
			append rest(right) to result
		return result

# 2. Quick Sort:
 
		function quicksort(array)
			var list lessOrEqual, greater
			if length(array) ≤ 1  
				return array  
			pivot := select a pivot value
			for each x in array
				if x ≤ pivot then add x to lessOrEqual
				if x > pivot then add x to greater
			return concatenate(quicksort(lessOrEqual), pivot, quicksort(greater))


##III Alogrithm with O(n log^2 n)

#0. Shell Sort

		input: an array a of length n with array elements numbered 0 to n − 1

		inc ← round(n/2)
		while inc > 0 do:
			for i = inc .. n − 1 do:
			 temp ← a[i]
				j ← i
				while j ≥ inc and a[j − inc] > temp do:
					a[j] ← a[j − inc]
					j ← j − inc
				a[j] ← temp
			inc ← round(inc / 2.2)


