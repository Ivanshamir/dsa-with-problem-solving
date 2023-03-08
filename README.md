# Problem Solving In Leetcode
This repository is mainly for learning purpose. I will try to solve different types of problems as well as in different type of languages in leetcode IN SHA ALLAH. 

# Link and strategy
| Problem | Link | Description | Complexity |
| ------------ | ------------- | ------------- | ------------- |
| 121.Best Time to Buy and Sell Stock | [Link](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/) | Solved can be using sliding window algorithm, two pointers use: i and i+1, loop will be continuing i+1 < len(prices). If i > i+1 then change the position otherwise differentiate the current i and i+1 and track the max | Time: O(N), Space: O(1) |
| 283. Move Zeroes | [Link](https://leetcode.com/problems/move-zeroes/) | Solved can be using quick sort or quick select algorithm, one pointers use: left. If i != 0 then swap the position with left and only for that inecrement left by 1 | Time: O(N), Space: O(1) |
| 122. Best Time to Buy and Sell Stock II | [Link](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/) | Same as 121. We keep track left and right, if right < left then swap left and right otherwise differentiate between left and right and add with total | Time: O(N), Space: O(1) |
| 347. Top K Frequent Elements | [Link](https://leetcode.com/problems/top-k-frequent-elements/) | Using bucket sort algorithm. First count total numbers appear and save in hashmap(dictionary).Then create another hashmap for frequency. Finally loop over frequency and found out top K elements | Time: O(N), Space: O(N) |
| 14. Longest Common Prefix | [Link](https://leetcode.com/problems/longest-common-prefix/) | We compare the letters of first element of array with others. First loop for letters of first element of array and 2nd loop for compare the specific letter with current element letter. If the letter is not silimar then return otherwise add the letter with final result | Time: O(M.N) where M is the total chracter of first element and N is the total elements of array, Space: O(1) |
| 28. Implement strStr() | [Link](https://leetcode.com/problems/implement-strstr/) | **Naive Approach:** Just cut the string from i to i+len(needle) and compare this with needle. <br/> **KMP Algo:** First we need to store the length of a portion of string(needle) which is prefix and also suffix. In lps 1st position will always be 0. We will use 2 pointers approach(Example: prevlps, i). If 2nd index str is similar to 1st then increment 1 so [0,1]. If not then: if prevlps == 0 then increment i otherwise prevlps will be lps[prevlps-1]. Now going to the main part. In here we will also use two pointers: one for haystack, one for needle. If haystack[i] == needle[j] then increment by 1 in both i and j. If not then: if j=0 then incremnt i by 1 otherwise j = lps[j-1] | Time: In Naive: time complexity O(N^2),space O(1) and KMP: time complexity O(M+N),space O(N) |
| 3. Longest Substring Without Repeating Characters | [Link](https://leetcode.com/problems/longest-substring-without-repeating-characters/) | we will use **sliding window** approach. For check duplicate value we are using a set. If value is already added in set then removes the left most value until all unique values are found in set. Otherwise value add in set and get max value: max(maxSize, i-left+1) | Time: time complexity O(N) there are loop inside loop but the inner loop only run if there is any duplicate so it is O(N) ,space O(N) |
| 8. String to Integer (atoi) | [Link](https://leetcode.com/problems/string-to-integer-atoi/) | Convert string to ASCII code using ord(). Then add the result with base 10 by multipliplication.Before for loop add corner cases | Time: time complexity O(N) ,space O(1) |
| 20. Valid Parentheses | [Link](https://leetcode.com/problems/valid-parentheses/) | Use heap. Create dictionary like: { ')':'(' } etc. and empty list for heap. Check item exists in dictionary if then check last item of heap is similar to current dict val. If not then False. Finally return true if stack is empty | Time: time complexity O(N) ,space O(N) |
| 2013. Detect Squares | [Link](https://leetcode.com/problems/detect-squares/) | The main trick is that first we need to calculate the difference of points diagonally. If we found that these points are not same and there is an equal difference between abs(x2-x4) and abs(y2-y4) then we need to find x4y2 and x2y4 exists in hashmap(dictionary). When we add point then we calculate the hash and save that in hashmap. Hash formula for this problem: (x * self.BASE) + y where BASE = max prime number as possible: 1000000007 | Time: time complexity O(N) ,space O(1) |
| 208. Implement Trie (Prefix Tree) | [Link](https://leetcode.com/problems/implement-trie-prefix-tree/) | First create class is for making node with dictionary. then loop over the dict, if val is already inserted in dict then skip it and goto the next val | Time: time complexity O(N) ,space O(26N),26 for each node.There can be at most N nodes where N = sum of all chars|
| 139. Word Break | [Link](https://leetcode.com/problems/word-break/) | We are using DP solution with bottom-up approach. We are looking by the worldDict with every character of s. | O(N*M*N) time, where N is the length of s, M is the length of worldDict and as we match the every world of dict so we need another N and O(1) space |
| 2089. Find Target Indices After Sorting Array | [Link](https://leetcode.com/problems/find-target-indices-after-sorting-array/description/) | First we sort then find out the solution from simple for loop | probably O(N logN) time, O(N) space |
| 704. Binary Search | [Link](https://leetcode.com/problems/binary-search/) | simple binary search. find middle index. if nums[mid] > target then decrese last index to 1 otherwise increse start value to 1 |  O(logN) time, O(1) space |
| 268. Missing Number | [Link](https://leetcode.com/problems/missing-number/description/) | first we sum the total by 1 to arr length, then get total by sum of elements in arr and compare them to get missing number |  O(N) time, O(1) space |
| 1539. Kth Missing Positive Number | [Link](https://leetcode.com/problems/kth-missing-positive-number/description/) | used binary search. for move left or right just used this logic: arr[mid] - (mid + 1) < k. because we want to check the value exists if arr[mid] - (mid + 1) === 0. suppose we have array [1,2,3] so if arr[mid] = 2 and mid = 1 then arr[mid] - (mid + 1) will be 0 |  O(logN) time, O(1) space |
| 374. Guess Number Higher or Lower | [Link](https://leetcode.com/problems/guess-number-higher-or-lower/description/) | used binary search. if guess < 0 then highest = mid - 1 otherwise lowest = mid + 1 |  O(logN) time, O(1) space |
| 744. Find Smallest Letter Greater Than Target | [Link](https://leetcode.com/problems/find-smallest-letter-greater-than-target/description/) | used binary search. if(letters[mid] > target && letters[mid-1] <= target) then return letters[mid], otherwise continue run loop |  O(logN) time, O(1) space |
| 278. First Bad Version | [Link](https://leetcode.com/problems/first-bad-version/description/) | used binary search. if(isBadVersion(mid) == true) { if(isBadVersion(mid-1)) high = mid - 1 else return mid } else low = mid + 1 | O(logN) time, O(1) space |
| 35. Search Insert Position | [Link](https://leetcode.com/problems/search-insert-position/description/) | used binary search. `if(nums[mid] === target or (nums[mid-1] < target && nums[mid] > target))` is the crack point | O(logN) time, O(1) space |
| 852. Peak Index in a Mountain Array | [Link](https://leetcode.com/problems/peak-index-in-a-mountain-array/description/) | used binary search. | O(logN) time, O(1) space |
| 162. Find Peak Element | [Link](https://leetcode.com/problems/find-peak-element/description/) | used binary search. | O(logN) time, O(1) space |
| 540. Single Element in a Sorted Array | [Link](https://leetcode.com/problems/single-element-in-a-sorted-array/description/) | binary search.check mid and mid+1 is different or not. if not then mid+1 otherwise mid. now check mid+1 % 2 === 0, if it is then go to right otherwise left | O(logN) time, O(1) space |