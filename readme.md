# My Dsa Rev

# Linked List

****
**Creating a Linked List From an array**
The logic behing is to
1. CREATE OR ASSIGN HEAD SEPERATELY
2. FOR LOOP FROM INDEX
   {
   ASSIGN HEAD TO CURRENTNODE
   MAKE A NEW NODE
   ASSIGN NEXT NODE TO CURRENT NODE
   AND NOW MAKE THE NEXT NODE TO CURRENT NODE
   }
3. LOOP ENDS THEN RETURN HEAD
****
**Deleting a head**
1. FIRST CHECK FOR THE LL FOR NULL FOR NO NEXT AND RETURN NEXT OR NULL RESP.
2. ASSIGN TEMP REFERENCE FOR HEAD (so that we still have the head to riginal ll)
3. HEAD = HEAD.NEXT
4. NOTE-: In C++ we might had to delete the head but the garabage collection does that for us in java
****
**Deleting a tail**
1. EDGE CASES -: one node or no node
2. temp = head
3. WHILE (temp.next ka next != null) {
   temp = temp.next
   }
   tail = temp
****
