# My Dsa Rev

# Linked List

******

**[Creating a Linked List From an array]()**

The logic behind is to

         1. CREATE OR ASSIGN HEAD SEPARATELY
   
         2. FOR LOOP FROM INDEX
            
            {
            
            ASSIGN HEAD TO CURRENTNODE
            
            MAKE A NEW NODE
            
            ASSIGN NEXT NODE TO CURRENT NODE
            
            AND NOW MAKE THE NEXT NODE TO CURRENT NODE
            
            }
   
4. LOOP ENDS THEN RETURN HEAD
   
**[Deleting a head]()**

      1. FIRST CHECK FOR THE LL FOR NULL FOR NO NEXT AND RETURN NEXT OR NULL RESP.
         
      2. ASSIGN TEMP REFERENCE FOR HEAD (so that we still have the head to original ll)
         
      3. HEAD = HEAD.NEXT
         
      4. NOTE-: In C++ we might have to delete the head but the garbage collection does that for us in Java
   
**[Deleting a tail]()**

      1. EDGE CASES -: one node or no node
         
      2. temp = head
         
      3. WHILE (temp.next ka next != null) {
         
         temp = temp.next
         
         }
   
   temp.next = null
   
**[Deleting any general position]()**

**Note** This covers all the cases

THE MAIN THING IS TO COVER THE EDGE CASES AND THEN THINK OF THE ALGORITHM

      1. if K==0
   
THEN -> HEAD {HEAD = HEAD.NEXT}

      2. else K != 0
         
         count = 0; temp = head; prevToTemp = null;
         
         WHILE (temp != null) {
         
         if (count == k) {
         
            prevToTemp.next = (prevToTemp.next).next
         
            break;
         
         }
         
         count++;
         
         prevTotemp = temp;
         
         temp = temp.next;
         
         }


**[Deleting using value]()**

**Note**-: if (temp.data == val)
******
**[Inserting at head]()**

Just return new node and its next as head

         return Node newHead = new Node(val, head);

**[Inmserting at Tail]()**

transverse tail 

         temp.next == nil;

then add node at that pos

         temp.next = new Node(val, nil);

**[Inserting at any General Pos]()**

         If k == 1
         
                  return Node newHead = new Node(val, head);
         
         count = 0; temp =head; 
         
         while (temp != nul) {

         if count = k-1 {

                  new Node(val, temp.next)
                  
                  temp.next = new node

                  break
         
         }

         return head;
         
         }

**NOTE** - in insertion and deletion general just pos cover the edge for the head and the left algorithm handles the tail;

**[Lenght and find element]()**

To find the length or add an element 

         count = 0; temp = head;
         
         while (temp != null) {
         
         count ++ || or return 1 if temp == desired
         
         }

# Double Linked List

**[constructing dll from an arr]()**

making head then starting the loop from arr[1]. the main idea here is assign prev to head

in a loop

create the nood by assing prev but next ass null

then assign prev.next to current node

then make the current node prev.

         class Solution {
         
    Node constructDLL(int arr[]) {
    
        // Code here
        
        //the mian way is first make head
        
        Node head = new Node(arr[0]);
        
        //make it prev
        
        Node prev = head;
        
        // nil<-prev->nil
        
        for (int i =1; i <= arr.length-1; i++) {
        
        // make temp or current node
        
        // prev<-temp->nil
        
        Node current = new Node(arr[i]);
        
        current.next = null;
        
        current.prev = prev;
        
        // prev->curreny
        
        prev.next = current;
        
        //make the temp prev
        
        prev = current;
        
        }
        
       return head; 
       
    }
    
         }

****

**[deleting a node in dll]()**

EDGE CASES ---> NULL DLL | AT ANY GENERAL POS ---->1.FOR HEAD
                                                   2.FOR TAIL
                                                   3.FOR GENERAL POS

The thing is for null dll we just return null but for not null dll we try to iterate over temp != null  and breaking the loop at desired pos or value

if the pos is 1 then handling edge case for head

         head.next.prev == null;

same for tail beacuse the null node next to tail should point to tailprev in general algo which cannot be handled by the general algo so need to be configure differently

         tail.prev.next = null;

         tail..prev = null;

GENERAL POSE

         temp.prev.next = temp.next;
         
         temp.next.prev = temp.prev;

**[inserting a node at a pos]()**

general ides is same the null should be handled and head and tail needs to be handled separately

try to have prev in iteration.

then assign prev to new node connections and same for tem's prev connection.

****

**[reversal DLL and return new head.]()**

for loop

consider temp to iterate and at every iteration reverse the pointers

to think to notice is

assign temp as new head every time

temp should be incremente as = temp.prev;

         class Solution {
    public DLLNode reverseDLL(DLLNode head) {
    //The main idea is to reverse the pointers only rather than creating a new Node;
        
        
    // DLL ==  NIL
    if (head == null) {
        return null;
    } 
    // DLL REVERSING FOR GENERAL
    // 1<->2<->3
    DLLNode temp = head;
    DLLNode newHead = null;

    // Traverse the list and reverse the pointers
        while (temp != null) {
            // Swap prev and next pointers
            DLLNode prev = temp.prev;
            temp.prev = temp.next;
            temp.next = prev;

            // Update the new head (it will be the last non-null node)
            newHead = temp;

            // Move to the next node in the original sequence (now using prev)
            temp = temp.prev;
        }

        return newHead;
    }
    }
****

# questions

1. **MIDDLE NODE**

         class Solution {
   
       public ListNode middleNode(ListNode head) {
   
        // EDGE CASES--> NULL DLL | NOT NULL-->

        // NULL DLL
   
        if (head == null) {
   
            return null;
   
        }

        //TWO CASES HERE--->
   
        //ODD NO OF ELEMENTS

       //   |---|---|
   
       //   |-------|-------|
    
         // 1<->2<->3<->4<->5

        //EVEN NO OF ELEMENTS

        // NOT NULL
   
        ListNode temp2 = head;
   
        ListNode temp1 = head;
   
        while (temp2 != null) {
   
            if (temp2.next == null) {
   
                break;
   
            }
   
            temp2 = temp2.next.next;
   
            temp1 = temp1.next;
   
        }
   
        return temp1;
   
       }
   
       }

There is a particular lag in play here the frognode is traversed by 2 nodes and it makes sure that the trortoisenode gets in the middle when the frog is at end or at tails next null

the thing to notice is to stop temp to traverse 2points when its at tail by implying the condition temp2.next == null and hence breaking the loop if it does it will acess a null pointer exception as there is

nothing next to tail's next
