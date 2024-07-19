# W11D2-Assignment

# Solving the Remove Linked List Elements Problem

 

# Objective:

# Enhance your problem-solving skills by solving the Remove Linked List Elements problem on LeetCode and documenting your solution approach.

 

# Problem Statement:

# Solve the LeetCode problem: https://leetcode.com/problems/remove-linked-list-elements/description/Links to an external site.

 

# Steps to Complete the Exercise:

# Understand the Problem:
#    - Carefully read the problem statement.

Given the head of a linked list and an integer val, remove all the nodes of the linked list that has Node.val == val, and return the new head.


#    - Identify the inputs and expected outputs.

Input: head = [1,2,6,3,4,5,6], val = 6
Output: [1,2,3,4,5]

Input: head = [], val = 1
Output: []

Input: head = [7,7,7,7], val = 7
Output: []

#    - Note the constraints and possible edge cases.

The number of nodes in the list is in the range [0, 104].
1 <= Node.val <= 50
0 <= val <= 50

# Plan Your Approach:
#    - Consider different strategies to solve the problem.

traverse the linked list, start a new linked list, for each step check to see if the data matches the passed value, if it does, it is not added to new linked list. setup linked list with a fake head to initialize, then pass it values that do not equal the target.

return the head of the new linked list as requirement, with some logic to filter empty lists and handle empty list results.

#    - Choose the most efficient algorithm considering time and space complexity.

Only using one while loop so time complexity is O(n) and since it is a linked list, updating pointers and not values it has a space complexity of O(1) which is ideal in both cases as it is neccessary to traverse the entire list to search for target values.

#    - Outline your solution before coding.

Using boilerplate from class for initialization and traversal, modified logic to remove selected elements.  This challenge is similar to a problem I solved and I accidentaly created this code expecting it to select the values between targets, but my code didnt work. I saved it with notes, and it was reused for this assignment.  I worked offline in vsc.

# Write the Code:
#    - Use your preferred coding environment.

Python 3

#    - Implement your solution clearly and concisely.

#    - Use meaningful variable names and comments to explain your code.

# Test Your Solution:
#    - Test your code with various test cases, including edge cases.

see attached screenshots

#    - Ensure your solution passes all test cases on LeetCode.

# Document Your Solution:
#    - Create a documentation file in PDF or Markdown format.

document is readme file

#    - Explain your code design choices.

my choices were made to comply with dynamic programming best practices

#    - Describe any specific algorithms or data structures used.

only one while loop used to minimize time complexity

#    - Detail your approach and reasoning for solving the problem.

# Submit Your Solution:
#    - Ensure your solution passes the LeetCode submission.

#    - Submit your documentation and LeetCode solution via the designated platform.

 

class ListNode(object):
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

class Solution(object):
    def removeElements(self, head, val):
        fake_head = ListNode(0)
        fake_head.next = head
        current = fake_head

        while current.next is not None:
            if current.next.val == val:
                current.next = current.next.next
            else:
                current = current.next

        return fake_head.next

    def create_linked_list(self, lst):
        if not lst:
            return None
        head = ListNode(lst[0])
        current = head
        for value in lst[1:]:
            current.next = ListNode(value)
            current = current.next
        return head



space complexity O(1)
time comlexity O(n)


### Conclusion

I was able to quickly solve this as code I wrote in the past solved this case. I originnally was writing to solve the selection betweentarget values and it selected everything but the target element.  I saved the useful mistake documenting the problem and behavior.

it took minimal updating for this application which I did in VSC.

the git repo includes this readme with my submission details.

