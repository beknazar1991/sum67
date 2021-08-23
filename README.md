# sum67
Return the sum of the numbers in the array, except ignore sections of numbers starting with a 6 and extending to the next 7 (every 6 will be followed by at least one 7). Return 0 for no numbers.   
sum67([1, 2, 2]) → 5 
sum67([1, 2, 2, 6, 99, 99, 7]) → 5 
sum67([1, 1, 6, 7, 2]) → 4

def sum67(nums):
    l = len(nums)
    s = 0
    k = 0
    for i in range(0, l):
        if s != 0:
            if nums[i] != 7:
                nums[i] = 0
                continue
            else:
                s = 0
                nums[i] = 0
        if nums[i] == 6:
            s += 1
            nums[i] = 0
    for j in range(0, l):
        k += nums[j]
    return k
