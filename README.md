# merge-two-linkedlist
//https://github.com/ayush460/linked-list-add-number/edit/main/README.md
/******************************************************************************

Welcome to GDB Online.
GDB online is an online compiler and debugger tool for C, C++, Python, Java, PHP, Ruby, Perl,
C#, OCaml, VB, Swift, Pascal, Fortran, Haskell, Objective-C, Assembly, HTML, CSS, JS, SQLite, Prolog.
Code, Compile, Run and Debug online from anywhere in world.

*******************************************************************************/
import java.util.*;
public class Main
{
    public static Node merge(Node ll1,Node ll2){
        if(ll1==null){
            return ll2;
        }
        if(ll2==null){
            return ll1;
        }
        Node head=null;
        if(ll1.data<ll2.data){
            head=ll1;
            ll1=ll1.next;
        }
        else{
            head=ll2;
            ll2=ll2.next;
        }
        Node temp=head;
        while(ll1!=null && ll2!=null){
            if(ll1.data<ll2.data){
                temp.next=ll1;
                ll1=ll1.next;
                temp=temp.next;
            }
            else{
            temp.next=ll2;
            ll2=ll2.next;
            temp=temp.next;
        }
        }
        if(ll1!=null){
           temp.next=ll1;
        }
        if(ll2!=null){
            temp.next=ll2;
        }
        return head;
    }
    public static void print(Node head){
     Node temp=head;
     while(temp!=null){
         System.out.print(temp.data+" ");
         temp=temp.next;
     }
    
 }   
	public static void main(String[] args) {
		Scanner sc=new Scanner(System.in);
		int n=sc.nextInt();
		int m=sc.nextInt();
		check a=new check();
		    check b=new check();
		for(int i=0;i<n;i++){
		    a.add(sc.nextInt());
		    
		}
		for(int i=0;i<m;i++){
		    b.add(sc.nextInt());
		}
		Node mergehead=merge(a.head,b.head);
		print(mergehead);
	}
}

class check{
    Node head;
    Node tail;
    void add(int data){
       Node newnode=new Node(data);
       if(head==null){
           head=newnode;
           tail=newnode;
       }
       tail.next=newnode;
       tail=newnode;
    }
 
}
class Node{
    int data;
    Node next;
    Node(int data){
        this.data=data;
        this.next=null;
    }
}
