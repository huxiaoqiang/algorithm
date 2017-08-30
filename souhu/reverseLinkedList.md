部门：搜狐产品技术部

面试手写

问题：给定一个单链表，实现单链表反转

思路：一个很简单的链表问题，思路是先记录当前节点的下一个节点，防止断链。具体的实现代码也比较简单，如下：

```Java
public class Main{
		public static LinkedList reverseLinkedList(LinkedList head){
	    LinkedList curNode = head;
	    LinkedList preNode = null;
	    LinkedList nextNode = null;
	    while(curNode != null){
	        //先存下当前节点的后续节点，防止当前节点指向前一个节点，产生断链。
	        nextNode = curNode.next; 
	        curNode.next = preNode;
	        preNode = curNode;
	        if(nextNode == null){
	            break;
	        }
	        else
	            curNode = nextNode;
	    }
	    return curNode;
	}
	
	static class LinkedList{
	    int val;
	    LinkedList next;
	    LinkedList(int val){
	        this.val = val;
	        next = null;
	    }
	}
}
```
