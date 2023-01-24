class LL
{    
    Node head;
    public int size ;
    LL()
    {
        this.size=0;
    }
     class Node
     {
          String  data ;
          Node next;
          Node(String data )
          {
              this.data =data;
              this.next=null;
              size++;
          }
     }
     public void addFirst(String data)
     {    
         Node newNode = new Node(data);
         if(head==null )
         {
              head =newNode;
              return;
         }
         newNode.next=head;
         head=newNode;
         
     }
     public void addLast(String data)
     {
        Node newNode = new Node(data);
            
           if(head==null)
             {
                 head = newNode;
                 return;
             }
           Node currNode = head;
            while(currNode.next!=null)
            {
              currNode=currNode.next;
            }
         currNode.next=newNode;
         
     }
    public void printList()
    {   
       if(head==null){ System.out.println("list is empty ");return;}  
       Node currNode = head;
       while(currNode!=null)
       {
           System.out.print(currNode.data +"->");
           currNode=currNode.next;
       }
        System.out.println("Null");
     }
     public void deleteFirst()
     {   
          
        if(head==null){ System.out.println("list is empty ");return;} 
        head=head.next;
        size--;
     }
     public void deleteLast()
     {    
          
        if(head==null){ System.out.println("list is empty ");return;} 
        size--;
        if(head.next==null)
        {
            head=null;
            return;
        }
        Node secondLast=head;
        Node lastNode=head.next;
        while(lastNode.next!=null)
        {
            lastNode=lastNode.next;
            secondLast=secondLast.next;
        }
        secondLast.next=null;
     }
     public int getsize()
     {
        return size;
     }
     public static void main(String args[])
     {
         LL List = new LL();
         List.addFirst("r");
         List.addFirst("is");
         List.addFirst("are");
         List.addFirst("is");
         List.printList();
         List.addLast("list  ");
         List.printList(); 
         List.addFirst("love");
         List.printList();
         List.deleteLast();
         List.printList();
         List.deleteLast();
         List.printList();
         List.deleteFirst();
         List.printList();
         System.out.println(List.getsize());
         List.addFirst("winner");
        List.printList();
        System.out.println(List.getsize());

        }}
     
