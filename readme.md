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


