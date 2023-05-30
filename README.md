# LinkedList
class Node:
    def __init__(self,data):
        self.data=data
        self.next=None
class SLL:
    def __init__(self):
        self.head=None
    
   def insertAtstart(self,data):
        nb=Node(data)
        nb.next=self.head
        self.head=nb
        
   def insertAtend(self,data):
        ne=Node(data)
        temp=self.head
        while temp.next:
            temp=temp.next
        temp.next=ne
        
   def insertAtpos(self,pos,data):
        np=Node(data)
        temp=self.head
        for i in range(0,pos-1):
            temp=temp.next
        np.data=data
        np.next=temp.next
        temp.next=np
    
   def Display(self):
        if self.head is None:
            print("Linkedlist is empty")
        else:
            temp=self.head
            while temp:
                print(temp.data,"--->",end=" ")
                temp=temp.next
    
   def delatstart(self):
        temp=self.head
        self.next=temp.next
        temp.next=None
        
   def delatend(self):
        prev=self.head
        temp=self.head.next
        while(temp.next is not None):
            temp=temp.next
            prev=prev.next
        prev.next=None
        
   def delatpos(self,pos):
        prev=self.head
        temp=self.head.next
        for i in range(0,pos-1):
            prev=prev.next
            temp=temp.next
        prev.next=temp.next
        
l=SLL()
n1=Node(20)
l.head=n1
n2=Node(30)
n1.next=n2
n3=Node(40)
n2.next=n3
#l.insertAtstart(10)
#l.insertAtend(50)
#l.insertAtpos(3,35)
#l.delatend()
l.delatpos(2)
l.Display()
