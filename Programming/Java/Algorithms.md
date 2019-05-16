# Algorithms

## Data Structures

### Arrays

- Collection of elements identified by index
- *Two dimensional arrays*

Operations
- Calculate item index `O(1)`
- Insert or delete item at beginning `O(n)`
- Insert or delete item in middle `O(n)`
- Insert or delete item at end 1O(1)`

### Linked Lists

- Linear collection of 'nodes'
- Contain reference to next node in list
- *Last item points to nothing*
- Elements can be easily inserted and removed
- *Can't do constant-time random item access*

Operations
- Alter where each node points

**Examples**

*Python*
```py
class Node :
	def __init__( self, data ) :
		self.data = data
		self.next = None
		self.prev = None

class LinkedList :
	def __init__( self ) :
		self.head = None		

	def add( self, data ) :
		node = Node( data )
		if self.head == None :	
			self.head = node
		else :
			node.next = self.head
			node.next.prev = node						
			self.head = node			

	def search( self, k ) :
		p = self.head
		if p != None :
			while p.next != None :
				if ( p.data == k ) :
					return p				
				p = p.next
			if ( p.data == k ) :
				return p
		return None

	def remove( self, p ) :
		tmp = p.prev
		p.prev.next = p.next
		p.prev = tmp		

	def __str__( self ) :
		s = ""
		p = self.head
		if p != None :		
			while p.next != None :
				s += p.data
				p = p.next
			s += p.data
		return s
```

*Java*

```Java
class LinkedList
{
	//Class variables for the Linked List
	private static Node head;
	private static int numNodes;
	
	public LinkedList(Object dat)
	{
		head = new Node(dat);
	}
	
	public void addAtHead(Object dat)
	{
		Node temp = head;
		head = new Node(dat);
		head.next = temp;
		numNodes++;
	}
	
	public void addAtTail(Object dat)
	{
		Node temp = head;
		while(temp.next != null)
		{
			temp = temp.next;
		}
		
		temp.next = new Node(dat);
		numNodes++;
	}
	
	public void addAtIndex(int index, Object dat)
	{
		Node temp = head;
		Node holder;
		for(int i=0; i < index-1 && temp.next != null; i++)
		{
			temp = temp.next;
		}
		holder = temp.next;
		temp.next = new Node(dat);
		temp.next.next = holder;
		numNodes++;
	}
	
	public void deleteAtIndex(int index)
	{
		Node temp = head;
		for(int i=0; i< index - 1 && temp.next != null; i++)
		{
			temp = temp.next;
		}
		temp.next = temp.next.next;
		numNodes--;
	}
	
	public static int find(Node n)
	{
		Node t = head;
		int index = 0;
		while(t != n)
		{
			index++;
			t = t.next;
		}
		return index;
	}
	
	public static Node find(int index)
	{
		Node temp=head;
		for(int i=0; i<index; i++)
		{
			temp = temp.next;
		}
		return temp;
	}
		
	public static void printList()
	{
		Node temp = head;
		while(temp != null)
		{
			System.out.println(temp.data);
			temp = temp.next;
		}
	}
	
	public static int getSize()
	{
		return numNodes;
	}
	
	class Node
	{
		//Declare class variables
		private Node next;
		private Object data;
		
		public Node(Object dat)
		{
			data = dat;
		}
		
		public Object getData()
		{
			return data;
		}
	}
}
```

### Stacks and Queues

Stack
- Collection that supports push and pop operations
- Last item pushed is the first one popped
- *Backtracking*

Queue
- Collection that supports adding and removing
- First item added is first item out
- *Order processing, messaging*

### Hash Tables

---