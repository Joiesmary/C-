					1.Write a C++ program to implement singly linked list
					 #include<iostream> 
					 #include<cstdlib> 
					 using namespace std; 
					 struct node 
					 { 
					 int info; 
					 struct node *next; 
					 }*start; 
					 class single_llist 
					 {  
					 public: 
					 node* create_node(int); 
					 void insert_begin(); 
					void insert_last(); 
					    void insert_pos(); 
					void delete_begin(); 
					void delete_last(); 
					void delete_pos(); 
					void update_begin(); 
					void update_last(); 
					void update_pos(); 
					void sort(); 
					void reverse(); 
					void search(); 
					 void display(); 
					 single_llist() 
					 { 
					 start = NULL; 
					 } 
					}; 
					int main() 
					{ 
					 int choice; 
					 single_llist sl,s2; 
					  start = NULL; 
					 do 
					 { 
					cout<<"---------------------------------"<<endl; 
					cout<<"Operations on singly linked list"<<endl; 
					cout<<"---------------------------------"<<endl; 
					 cout<<"1.Insert at first"<<endl; 
					cout<<"2.Insert at last"<<endl; 
					cout<<"3.Insert at position"<<endl; 
					cout<<"4.Delete at first"<<endl; 
					cout<<"5.Delete at Last"<<endl; 
					cout<<"6.Delete at position"<<endl; 
					cout<<"7.Update at first"<<endl; 
					cout<<"8.Update at last"<<endl; 
					cout<<"9.Update at position"<<endl; 
					cout<<"10.Ascending order"<<endl; 
					cout<<"11.Descending order"<<endl; 
					cout<<"12.Search"<<endl; 
					cout<<"13.Display"<<endl; 
					cout<<"14.Exit "<<endl; 
					cout<<"Enter your choice :"; 
					cin>>choice; 
					    switch(choice) 
					 { 
					case 1: sl.insert_begin(); 
					sl.display(); 
					break; 
					case 2: sl.insert_last(); 
					 sl.display(); 
					 break; 
					case 3: sl.insert_pos(); 
					 sl.display(); 
					 break; 
					case 4: s2.delete_begin(); 
					 sl.display(); 
					  break; 
					 case 5: s2.delete_last(); 
					  sl.display(); 
					break; 
					case 6: sl.delete_pos(); 
					sl.display(); 
					break; 
					case 7: sl.update_begin(); 
					sl.display(); 
					break; 
					case 8: sl.update_last(); 
					sl.display(); 
					break; 
					case 9: sl.update_pos(); 
					sl.display(); 
					break; 
					case 10:sl.sort(); 
					sl.display(); 
					break; 
					case 11:sl.reverse(); 
					sl.display(); 
					break; 
					case 12:sl.search(); 
					sl.display(); 
					break; 
					case 13:sl.display(); 
					break; 
					case 14:exit(0); 
					break; 
					default:cout<<"Wrong choice...???"<<endl; 
					break; 
					} 
					} 
					while(choice != 14); 
					} 
					node *single_llist::create_node(int value) 
					{ 
					struct node *temp, *s; 
					temp = new(struct node); 
					if (temp == NULL) 
					{ 
					cout<<"Memory not allocated"<<endl; 
					return 0; 
					} 
					else 
					 { 
					temp->info = value; 
					temp->next = NULL; 
					return temp; 
					} 
					} 
					void single_llist::insert_begin() 
					{ 
					int value; 
					 cout<<"Enter the value to be inserted : "; 
					 cin>>value; 
					 struct node *temp, *s; 
					temp = create_node(value); 
					if (start == NULL) 
					{ 
					start = temp; 
					start->next = NULL; 
					cout<<temp->info<<" is inserted at first in the empty list"<<endl; 
					} 
					else 
					{ 
					 s = start; 
					start = temp; 
					start->next = s; 
					cout<<temp->info<<" is inserted at first"<<endl; 
					} 
					} 
					 void single_llist::insert_last() 
					{ 
					int value; 
					cout<<"Enter the value to be inserted : "; 
					cin>>value; 
					 struct node *temp, *s; 
					 temp = create_node(value); 
					if (start == NULL) 
					 { 
					 start = temp; 
					start->next = NULL; 
					 cout<<temp->info<<" is inserted at last in the empty list"<<endl; 
					} 
					 else 
					{ 
					s = start; 
					while (s->next != NULL) 
					{ 
					s = s->next; 
					 } 
					temp->next = NULL; 
					 s->next = temp; 
					 cout<<temp->info<<" is inserted at last"<<endl; 
					 } 
					 } 
					 void single_llist::insert_pos() 
					 { 
					      int value, pos, counter = 0, loc = 1; 
					     struct node *temp, *s, *ptr; 
					   s = start; 
					 while (s != NULL) 
					  { 
					s = s->next; 
					  counter++; 
					     } 
					 if (counter == 0){} 
					  else 
					{ 
					cout<<"Enter the postion from "<<loc<<" to "<<counter+1<<" : "; 
					 cin>>pos; 
					 s = start; 
					 if(pos == 1) 
					  { 
					   cout<<"Enter the value to be inserted : "; 
					 cin>>value; 
					     temp = create_node(value); 
					   start = temp; 
					     start->next = s; 
					   cout<<temp->info<<" is inserted at first"<<endl; 
					   } 
					     else if (pos > 1 && pos <= counter) 
					   { 
					      cout<<"Enter the value to be inserted : "; 
					  cin>>value; 
					  temp = create_node(value); 
					 for (int i = 1; i < pos; i++) 
					 { 
					 ptr = s; 
					 s = s->next; 
					 } 
					   ptr->next = temp; 
					   temp->next = s; 
					 cout<<temp->info<<" is inserted at position "<<pos<<endl; 
					      } 
					   else if (pos == counter+1) 
					  { 
					 cout<<"Enter the value to be inserted : "; 
					  cin>>value; 
					  temp = create_node(value); 
					     while (s->next != NULL) 
					       { 
					     s = s->next; 
					      } 
					    temp->next = NULL; 
					 s->next = temp; 
					 cout<<temp->info<<" is inserted at last"<<endl; 
					 } 
					else 
					 { 
					 cout<<"Positon out of range...!!!"<<endl; 
					  } 
					 }  else 
					
					 { 
					
					  s = start; 
					
					 while (s->next != NULL) 
					
					 { 
					
					 s = s->next; 
					
					} 
					
					temp->next = NULL; 
					
					 s->next = temp; 
					
					   cout<<temp->info<<" is inserted at last"<<endl; 
					
					  } 
					
					 } 
					
					  void single_llist::insert_pos() 
					
					 { 
					
					  int value, pos, counter = 0, loc = 1; 
					
					  struct node *temp, *s, *ptr; 
					
					   s = start; 
					
					    while (s != NULL) 
					
					    { 
					
					 s = s->next; 
					
					 counter++; 
					
					 } 
					
					 if (counter == 0){} 
					
					 else 
					
					 { 
					
					    cout<<"Enter the postion from "<<loc<<" to "<<counter+1<<" : "; 
					
					cin>>pos; 
					
					 s = start; 
					
					 if(pos == 1) 
					
					 { 
					
					  cout<<"Enter the value to be inserted : "; 
					
					cin>>value; 
					
					 temp = create_node(value); 
					
					 start = temp; 
					
					  start->next = s; 
					
					 cout<<temp->info<<" is inserted at first"<<endl; 
					
					  } 
					
					     else if (pos > 1 && pos <= counter) 
					
					 { 
					
					 cout<<"Enter the value to be inserted : "; 
					
					 cin>>value; 
					
					 temp = create_node(value); 
					
					for (int i = 1; i < pos; i++) 
					
					 { 
					
					  ptr = s; 
					
					  s = s->next; 
					
					   } 
					
					  ptr->next = temp; 
					
					  temp->next 
					  } 
					   void single_llist::delete_begin() 
					 { 
					  if (start == NULL){} 
					  else 
					 { 
					struct node *s, *ptr; 
					s = start; 
					start = s->next; 
					cout<<s->info<<" deleted from first"<<endl; 
					free(s); 
					 } 
					} 
					void single_llist::delete_last() 
					{ 
					int i, counter = 0; 
					struct node *s, *ptr; 
					if (start == NULL){} 
					else 
					{ 
					s = start; 
					while (s != NULL) 
					{ 
					s = s->next; 
					counter++; 
					} 
					s = start; 
					if (counter == 1) 
					{ 
					start = s->next; 
					cout<<s->info<<" deleted from last"<<endl; 
					free(s); 
					} 
					else 
					{ 
					for (i = 1;i < counter;i++) 
					{ 
					ptr = s; 
					s = s->next; 
					} 
					ptr->next = s->next; 
					cout<<s->info<<" deleted from last"<<endl; 
					free(s); 
					} 
					  } 
					} 
					void single_llist::delete_pos() 
					{ 
					 int pos, i, counter = 0, loc = 1; 
					struct node *s, *ptr; 
					s = start; 
					while (s != NULL) 
					{ 
					  s = s->next; 
					 counter++; 
					} 
					if (counter == 0){} 
					else 
					{ 
					 if (counter == 1) 
					{ 
					 cout<<"Enter the postion [ SAY "<<loc<<" ] : "; 
					 cin>>pos; 
					s = start; 
					 if (pos == 1) 
					 { 
					 start = s->next; 
					 cout<<s->info<<" deleted from first"<<endl; 
					 free(s); 
					  } 
					 else 
					 cout<<"Position out of range...!!!"<<endl; 
					 } 
					 else 
					{ 
					 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; 
					 cin>>pos; 
					 s = start; 
					 if (pos == 1) 
					{ 
					 start = s->next; 
					cout<<s->info<<" deleted from first"<<endl; 
					free(s); 
					} 
					else if (pos > 1 && pos <= counter) 
					{ 
					  for (i = 1;i < pos;i++) 
					  { 
					 ptr = s; 
					s = s->next; 
					 } 
					  ptr->next = s->next; 
					if(pos == counter) 
					{cout<<s->info<<" deleted from last"<<endl; 
					free(s);} 
					else 
					{cout<<s->info<<" deleted from postion "<<pos<<endl; 
					free(s);} 
					 } 
					else 
					 cout<<"Position out of range...!!!"<<endl; 
					} 
					} 
					 } 
					 void single_llist::update_begin() 
					{ 
					int value, pos=1, i,counter = 0; 
					struct node *s, *ptr; 
					s = start; 
					while (s != NULL) 
					{ 
					s = s->next; 
					counter++; 
					} 
					if (counter == 0){} 
					 else if (pos == 1) 
					{ 
					 cout<<"Enter the new node : "; 
					cin>>value; 
					start->info = value; 
					cout<<"Node updated at first position : "<<pos<<" = "<<start->info<<endl; 
					 } 
					} 
					void single_llist::update_last() 
					{ 
					 int value, pos, i,counter = 0; 
					 struct node *s, *ptr; 
					s = start; 
					       while (s != NULL) 
					   { 
					   s = s->next; 
					 counter++; 
					} 
					 s=start; 
					 if (counter == 0){} 
					 else 
					 { 
					 cout<<"Enter the new node : "; 
					 cin>>value; 
					 for (i = 1; i < counter ; i++) 
					 { 
					 s = s->next; 
					 } 
					 s->info = value; 
					 cout<<"Node updated at last position : "<<counter<<" = "<<s->info<<endl; 
					} 
					} 
					void single_llist::update_pos() 
					{ 
					int value, pos, i,counter = 0, loc = 1; 
					struct node *s, *ptr; 
					s = start; 
					while (s != NULL) 
					{ 
					s = s->next; 
					counter++; 
					} 
					if (counter == 0){} 
					else 
					{ 
					if (counter == 1) 
					{ 
					cout<<"Enter the postion [ SAY "<<loc<<" ] : "; 
					cin>>pos; 
					s = start; 
					if (pos == 1) 
					{ 
					cout<<"Enter the new node : "; 
					cin>>value; 
					start->info = value; 
					cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; 
					} 
					else 
					cout<<"Position out of range...!!!"<<endl; 
					} 
					else 
					{ 
					cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; 
					cin>>pos; 
					s = start; 
					if (pos == 1) 
					{ 
					cout<<"Enter the new node : "; 
					cin>>value; 
					start->info = value; 
					cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; 
					} 
					else if (pos > 1 && pos <= counter) 
					{ 
					cout<<"Enter the new node : "; 
					cin>>value; 
					for (i = 1; i < pos ; i++) 
					{ 
					s = s->next; 
					} 
					s->info = value; 
					cout<<"Node updated at position : "<<pos<<" = "<<s->info<<endl; 
					 } 
					else 
					cout<<"Position out of range...!!!"<<endl; 
					} 
					} 
					} 
					 void single_llist::sort() 
					{ 
					struct node *ptr, *s; 
					int value; 
					if (start == NULL){} 
					else 
					{ 
					 ptr = start; 
					while (ptr != NULL) 
					{ 
					 for (s = ptr->next;s !=NULL;s = s->next) 
					 { 
					if (ptr->info > s->info) 
					{ 
					 value = ptr->info; 
					ptr->info = s->info; 
					s->info = value; 
					} 
					} 
					ptr = ptr->next; 
					} 
					 } 
					} 
					void single_llist::reverse() 
					{ 
					 struct node *ptr, *s; 
					int value; 
					if (start == NULL){} 
					 else 
					{ 
					 ptr = start; 
					 while (ptr != NULL) 
					{ 
					for (s = ptr->next;s !=NULL;s = s->next) 
					{ 
					if (ptr->info < s->info) 
					{ 
					 value = ptr->info; 
					ptr->info = s->info; 
					s->info = value; 
					} 
					} 
					ptr = ptr->next; 
					} 
					} 
					} 
					void single_llist::search() 
					{ 
					 int value, loc = 0, pos = 0, counter = 0; 
					struct node *s; 
					 s = start; 
					while (s != NULL) 
					 { 
					s = s->next; 
					counter++; 
					 } 
					if (start == NULL){} 
					else 
					{ 
					cout<<"Enter the value to be searched : "; 
					cin>>value; 
					struct node *s; 
					s = start; 
					while (s != NULL) 
					{ 
					pos++; 
					 if (s->info == value) 
					{ 
					 loc++; 
					 if(loc == 1) 
					 cout<<"Element "<<value<<" is found at position "<<pos; 
					 else if(loc <= counter) 
					cout<<" , "<<pos; 
					} 
					s = s->next; 
					} 
					cout<<endl; 
					if (loc == 0) 
					cout<<"Element "<<value<<" not found in the list"<<endl; 
					} 
					} 
					void single_llist::display() 
					{ 
					struct node *temp; 
					 if (start == NULL) 
					cout<<"Linked list is empty...!!!"<<endl; 
					else 
					{ 
					cout<<"Linked list contains : "; 
					temp = start; 
					while (temp != NULL) 
					{ 
					cout<<temp->info<<" "; 
					temp = temp->next; 
					} 
					cout<<endl; 
					 } 
					 }
           
   ![image](https://user-images.githubusercontent.com/19484531/163928616-14be44fc-2402-43f4-9d77-84cee0e34bbc.png)
![image](https://user-images.githubusercontent.com/19484531/163928692-5978ea84-620c-43b1-851f-68c3fde44a92.png)
![image](https://user-images.githubusercontent.com/19484531/163928744-5261e7af-a0fe-4039-bcb3-6c76b9c572b8.png)
![image](https://user-images.githubusercontent.com/19484531/163929150-35904d3a-6921-4667-9de3-6db8381a9541.png)
![image](https://user-images.githubusercontent.com/19484531/163929586-07d97416-d6b2-4170-99f4-3cac506fd3af.png)
![image](https://user-images.githubusercontent.com/19484531/163930009-913bb0b1-b1e6-4822-9031-2b376a06c4a6.png)
![image](https://user-images.githubusercontent.com/19484531/163930335-c38362d2-4637-4916-90ad-5c9e5ca64f40.png)
![image](https://user-images.githubusercontent.com/19484531/163930637-9e6c531d-3ae2-4e7d-ab44-bb185eada0d2.png)
![image](https://user-images.githubusercontent.com/19484531/163931064-975ce07e-b7c7-4cd8-a5cd-e8a99c15b87b.png)

   

					
    program 2: Write a C++ program to split the linked list into two halves such that the element ‘e’ should be the first element of second list.
 
		#include<iostream>
		using namespace std;
		struct Node{
		int value;
		struct Node *next;
		};
		struct Node* head = NULL;
		struct Node* sHead = NULL;
		struct Node* temp = NULL;
		void insert(int new_data){
		struct Node* new_node = new Node(); //(struct Node*)malloc(sizeof(struct Node));
		new_node->value = new_data;
		new_node->next = head;
		head = new_node;
		}
		int n;
		int ele;
		int splitIndex;
		int main(){
		int i;
		cout<<"Enter number of elements you want in the list\t";
		cin>>n;
		cout<<"Enter elements :" <<endl;
		for(i=0;i<n;i++){
		cin>>ele;
		insert(ele);
		}
		cout<<"\nList of elements : "<<endl;
		Node *t;
		t = head;
		while(t != NULL){
		cout<<t->value<<"\t";
		t = t->next;
		}
		cout<<"\n\nEnter the position you want the list to split ";
		cin>>splitIndex;
		while(splitIndex < 0 || splitIndex > n-1){
		cout<<"Invalid position. Try again."<<endl;
		cin>>splitIndex;
		}
		temp = head;
		for(i=0;i<=splitIndex;i++){
		if(i==splitIndex-1){
		Node *tN;
		tN = temp->next;
		sHead = tN;
		temp->next = NULL;
		break;
		}
		temp = temp->next;
		}
		temp = head;
		if(temp == NULL){
		cout<<"\nFirst list is empty"<<endl;
		}else{
		cout<<"\n\nFirst list element "<<endl;
		while(temp != NULL){
		cout<<temp->value<<"\t";
		temp = temp->next;
		}
		}
		temp = sHead;
		if(temp == NULL){
		cout<<"\nSecond list is empty"<<endl;
		}else{
		cout<<"\n\nSecond list elements "<<endl;
		while(temp != NULL){
		cout<<temp->value<<"\t";
		temp = temp->next;
		}
		}
		return 0;
		}
    
  output:
  ![image](https://user-images.githubusercontent.com/19484531/163933485-221159ea-4ffc-4c24-8e4a-4f3472e57baf.png)


    program 3:Write a C++ program to check if a binary tree is BST or not
    
    
				#include <bits/stdc++.h>
				using namespace std;
				struct Node
				{
				int data;
				struct Node* left, *right;
				Node(int data)
				{
				this->data = data;
				left = right = NULL;
				}
				};
				bool isBSTUtil(struct Node* root, Node *&prev)
				{
				if (root)
				{
				if (!isBSTUtil(root->left, prev))
				return false;
				if (prev != NULL && root->data <= prev->data)
				return false;
				prev = root;
				return isBSTUtil(root->right, prev);
				}
				return true;
				}
				bool isBST(Node *root)
				{
				Node *prev = NULL;
				return isBSTUtil(root, prev);
				}
				int main()
				{
				struct Node *root = new Node(7);
				root->left = new Node(5);
				root->right = new Node(8);
				root->left->left = new Node(3);
				root->left->right = new Node(6);
				if (isBST(root))
				cout << "Is BST";
				else
				cout << "Not a BST";
				return 0;
				}
        
 output: 
 ![image](https://user-images.githubusercontent.com/19484531/163934439-709ffdcd-a78b-4b54-be69-3a0c6d9d7648.png)


				
	program 4:	 Write a C++ program to implement BST to support the following operations
     Assume no duplicate elements while constructing the BST
     1.Given a key perform a search in the BST, if the key is found then display “key found”
     2.Insert an element into a BST
     3.Delete an element from a BST
     Display the tree using Inorder,Preorder and Postorder traversal methods

     # include <iostream> 
		# include <cstdlib> 
		using namespace std; 
		struct node 
		{ 
		 int info; 
		 struct node *left; 
		 struct node *right; 
		}*root; 
		class BST 
		{ 
		 public: 
		 void find(int, node **, node **); 
		 void insert(node *, node *); 
		 void del(int); 
		 void case_a(node *,node *); 
		 void case_b(node *,node *); 
		 void case_c(node *,node *); 
		 void preorder(node *); 
		 void inorder(node *); 
		 void postorder(node *); 
		 void display(node *, int); 
		 BST() 
		 { 
		 root = NULL; 
		 } 
		}; 
		int main() 
		{ 
		 int choice, num; 
		 BST bst; 
		 node *temp; 
		 while (1) 
		 { 
		 cout<<"-----------------"<<endl; 
		 cout<<"Operations on BST"<<endl; 
		 cout<<"-----------------"<<endl; 
		 cout<<"1.Insert Element "<<endl; 
		 cout<<"2.Delete Element "<<endl; 
		 cout<<"3.Inorder Traversal"<<endl; 
		 cout<<"4.Preorder Traversal"<<endl; 
		 cout<<"5.Postorder Traversal"<<endl; 
		 cout<<"6.Display"<<endl; 
		 cout<<"7.Quit"<<endl; 
		 cout<<"Enter your choice : "; 
		 cin>>choice; 
		 switch(choice) 
		 { 
		 case 1: 
		 temp = new node; 
		 cout<<"Enter the number to be inserted : "; 
		 cin>>temp->info; 
		 bst.insert(root, temp); 
		 break; 
		 case 2: 
		 if (root == NULL) 
		 { 
		 cout<<"Tree is empty, nothing to delete"<<endl; 
		 continue; 
		 } 
		 cout<<"Enter the number to be deleted : "; 
		 cin>>num; 
		 bst.del(num); 
		 break; 
		 case 3: 
		 cout<<"Inorder Traversal of BST:"<<endl; 
		 bst.inorder(root); 
		 cout<<endl; 
		 break; 
		 case 4: 
		 cout<<"Preorder Traversal of BST:"<<endl; 
		 bst.preorder(root); 
		 cout<<endl; 
		 break; 
		 case 5: 
		 cout<<"Postorder Traversal of BST:"<<endl; 
		 bst.postorder(root); 
		 cout<<endl; 
		 break; 
		 case 6: 
		 cout<<"Display BST:"<<endl; 
		 bst.display(root,1); 
		 cout<<endl; 
		 break; 
		 case 7: 
		 exit(1); 
		 default: 
		 cout<<"Wrong choice"<<endl; 
		 } 
		 } 
		} 
		void BST::find(int item, node **par, node **loc) 
		{ 
		 node *ptr, *ptrsave; 
		 if (root == NULL) 
		 { 
		 *loc = NULL; 
		 *par = NULL; 
		 return; 
		 } 
		 if (item == root->info) 
		 { 
		 *loc = root; 
		 *par = NULL; 
		 return; 
		 } 
		 if (item < root->info) 
		 ptr = root->left; 
		 else 
		 ptr = root->right; 
		 ptrsave = root; 
		 while (ptr != NULL) 
		 { 
		 if (item == ptr->info) 
		 { 
		 *loc = ptr; 
		 *par = ptrsave; 
		 return; 
		 } 
		 ptrsave = ptr; 
		 if (item < ptr->info) 
		 ptr = ptr->left; 
		 else 
		 ptr = ptr->right; 
		 } 
		 *loc = NULL; 
		 *par = ptrsave; 
		} 
		
		void BST::insert(node *tree, node *newnode) 
		{ 
		 if (root == NULL) 
		 { 
		 root = new node; 
		 root->info = newnode->info; 
		 root->left = NULL; 
		 root->right = NULL; 
		 cout<<"Root Node is Added"<<endl; 
		 return; 
		 } 
		 if (tree->info == newnode->info) 
		 { 
		 cout<<"Element already in the tree"<<endl; 
		 return; 
		 } 
		 if (tree->info > newnode->info) 
		 { 
		 if (tree->left != NULL) 
		 { 
		 insert(tree->left, newnode); 
		 } 
		 else 
		 { 
		 tree->left = newnode; 
		 (tree->left)->left = NULL; 
		 (tree->left)->right = NULL; 
		 cout<<"Node Added To Left"<<endl; 
		 return; 
		 } 
		 } 
		 else 
		 { 
		 if (tree->right != NULL) 
		 { 
		 insert(tree->right, newnode); 
		 } 
		 else 
		 { 
		 tree->right = newnode; 
		 (tree->right)->left = NULL; 
		 (tree->right)->right = NULL; 
		 cout<<"Node Added To Right"<<endl; 
		 return; 
		 } 
		 } 
		} 
		
		void BST::del(int item) 
		{ 
		 node *parent, *location; 
		 if (root == NULL) 
		 { 
		 cout<<"Tree empty"<<endl; 
		 return; 
		 } 
		 find(item, &parent, &location); 
		 if (location == NULL) 
		 { 
		 cout<<"Item not present in tree"<<endl; 
		 return; 
		 } 
		 if (location->left == NULL && location->right == NULL) 
		 case_a(parent, location); 
		 if (location->left != NULL && location->right == NULL) 
		 case_b(parent, location); 
		 if (location->left == NULL && location->right != NULL) 
		 case_b(parent, location); 
		 if (location->left != NULL && location->right != NULL) 
		 case_c(parent, location); 
		 free(location); 
		} 
		 
		
		void BST::case_a(node *par, node *loc ) 
		{ 
		 if (par == NULL) 
		 { 
		 root = NULL; 
		 } 
		 else 
		 { 
		 if (loc == par->left) 
		 par->left = NULL; 
		 else 
		 par->right = NULL; 
		 } 
		} 
		 
		
		void BST::case_b(node *par, node *loc) 
		{ 
		 node *child; 
		 if (loc->left != NULL) 
		 child = loc->left; 
		 else 
		 child = loc->right; 
		 if (par == NULL) 
		 { 
		 root = child; 
		 } 
		 else 
		 { 
		 if (loc == par->left) 
		 par->left = child; 
		 else 
		 par->right = child; 
		 } 
		} 
		 
		
		void BST::case_c(node *par, node *loc) 
		{ 
		 node *ptr, *ptrsave, *suc, *parsuc; 
		 ptrsave = loc; 
		 ptr = loc->right; 
		 while (ptr->left != NULL) 
		 { 
		 ptrsave = ptr; 
		 ptr = ptr->left; 
		 } 
		 suc = ptr; 
		 parsuc = ptrsave; 
		 if (suc->left == NULL && suc->right == NULL) 
		 case_a(parsuc, suc); 
		 else 
		 case_b(parsuc, suc); 
		 if (par == NULL) 
		 { 
		 root = suc; 
		 } 
		 else 
		 { 
		 if (loc == par->left) 
		 par->left = suc; 
		 else 
		 par->right = suc; 
		 } 
		 suc->left = loc->left; 
		 suc->right = loc->right; 
		} 
		 
		 
		void BST::preorder(node *ptr) 
		{ 
		 if (root == NULL) 
		 { 
		 cout<<"Tree is empty"<<endl; 
		 return; 
		 } 
		 if (ptr != NULL) 
		 { 
		 cout<<ptr->info<<" "; 
		 preorder(ptr->left); 
		 preorder(ptr->right); 
		 } 
		} 
		
		void BST::inorder(node *ptr) 
		{ 
		 if (root == NULL) 
		 { 
		 cout<<"Tree is empty"<<endl; 
		 return; 
		 } 
		 if (ptr != NULL) 
		 { 
		 inorder(ptr->left); 
		 cout<<ptr->info<<" "; 
		 inorder(ptr->right); 
		 } 
		} 
		 
		void BST::postorder(node *ptr) 
		{ 
		 if (root == NULL) 
		 { 
		 cout<<"Tree is empty"<<endl; 
		 return; 
		 } 
		 if (ptr != NULL) 
		 { 
		 postorder(ptr->left); 
		 postorder(ptr->right); 
		 cout<<ptr->info<<" "; 
		 } 
		} 
		 
		void BST::display(node *ptr, int level) 
		{ 
		 int i; 
		 if (ptr != NULL) 
		 { 
		 display(ptr->right, level+1); 
		 cout<<endl; 
		 if (ptr == root) 
		 cout<<"Root->: "; 
		 else 
		 { 
		 for (i = 0;i < level;i++) 
		 cout<<" "; 
		 } 
		 cout<<ptr->info; 
		 display(ptr->left, level+1); 
		 } 
		}
    

![image](https://user-images.githubusercontent.com/19484531/163935901-c143749a-e36d-454c-894a-bc3fc1684a79.png)
![image](https://user-images.githubusercontent.com/19484531/163935970-577124a3-3d52-4fd9-a324-89f5eae93309.png)
![image](https://user-images.githubusercontent.com/19484531/163936022-1b70508c-23c3-4638-8372-25fe15449728.png)


    
    program 5:Write a C++ program for implementing Heap sort technique.
  
  		#include <iostream>
		using namespace std;
		void MaxHeapify (int a[], int i, int n)
		{
			int j, temp;
			temp = a[i];
			j = 2*i;
			while (j <= n)
			{
				if (j < n && a[j+1] > a[j])
				j = j+1;
				if (temp > a[j])
					break;
				else if (temp <= a[j])
				{
					a[j/2] = a[j];
					j = 2*j;
				}
			}
			a[j/2] = temp;
			return;
		}
		void HeapSort(int a[], int n)
		{
			int i, temp;
			for (i = n; i >= 2; i--)
			{
				temp = a[i];
				a[i] = a[1];
				a[1] = temp;
				MaxHeapify(a, 1, i - 1);
			}
		}
		void Build_MaxHeap(int a[], int n)
		{
			int i;
			for(i = n/2; i >= 1; i--)
				MaxHeapify(a, i, n);
		}
		int main()
		{
		int n, i,arr[100];
			cout<<"\nEnter the number of data element to be sorted: ";
			cin>>n;
			n++;
			for(i=1;i<n;i++)
			 {
			 cout<<"Enter element"<<i<<":";
			 cin>>arr[i];
			 }
			Build_MaxHeap(arr, n-1);
			HeapSort(arr, n-1);
			cout<<"\nSorted Data ";
			for (i = 1; i < n; i++)
				cout<<" "<<arr[i];
			return 0;
		}
Output:
![image](https://user-images.githubusercontent.com/19484531/163936181-94f17dfa-1271-4ed2-9f67-51afbf60f0de.png)



				program 6: Write C++ program for implementing the max Heap and min heap  Sort technique.
			 #include <iostream>
			 using namespace std;
			void MaxHeapify (int *a, int m, int n) {
			int j, t;
			t = a[m];
			j = 2 * m;
			while (j <= n) {
			   if (j < n && a[j+1] > a[j])
			     j = j + 1;
			  if (t > a[j])
			     break;
			  else if (t <= a[j]) {
			     a[j / 2] = a[j];
			     j = 2 * j;
			  }
			}
			a[j/2] = t;
			return;
			}
			void MinHeapify (int *a,int i, int n)
			{
			 int j, temp;
			temp = a[i];
			j = 2*i;
			while (j <= n)
			{
			  if (j < n && a[j+1] < a[j])
			  j = j+1;
			  if (temp < a[j])
					break;
			else if (temp >= a[j])
			{
			    a[j/2] = a[j];
			    j = 2*j;
			} 
			}
			a[j/2] = temp;
			return;
			}
			
			/*void HeapSort(int a[], int n)
			 {
			int i, temp;
			for (i = n; i >= 2; i--)
			{
				temp = a[i];
				a[i] = a[1];
				a[1] = temp;
				MaxHeapify(a, 1, i - 1);
			}
			} */
			
			void build_maxheap(int *a,int n) {
			 int k;
			 for(k = n/2; k >= 1; k--) {
			  MaxHeapify(a,k,n);
			  }
			}
			void Build_MinHeap(int *a, int n)
			{
			int i;
			for(i = n/2; i >= 1; i--)
			{
			
				MinHeapify(a, i, n);
			}
			
			}
			
			int main()
			{
			    int n, i,arr[100];
			cout<<"\nEnter the number of data element to be sorted: ";
			cin>>n;
			//n++;
			for(i=1;i<=n;i++)
			 {
			 cout<<"Enter element"<<i<<":";
			 cin>>arr[i];
			 }
			 
			 
			Build_MinHeap(arr, n);
			cout<<"\nMin heap Sorted Data \n";//correct
			for (i = 1; i <= n; i++)
			{
			
				cout<<" "<<arr[i];
			}
			
			  build_maxheap(arr,n-1);
			  cout<<"\nMax Heap\n";
			 for (i = 1; i <= n; i++) {
			  cout<<arr[i]<<endl;
			 }
			
			}
output: 
![image](https://user-images.githubusercontent.com/19484531/163936250-c31e5dd6-b310-41b8-bf22-564335f88048.png)


     program 7: Write a C++ program to find subset of a given sets.
    #include <iostream>

    #include<stack>
    using namespace std;
    int set[]={4,6,3,7,5,8,1};
    int numberOfElements=7,sum=11;
    class Subset
    {
	public:
		stack<int> solutionSet;
		bool hasSolution;
		void solve(int s,int idx)
		{
			if(s>sum)
			return;
			if(s==sum)
			{
				hasSolution=true;
				displaySolutionSet();
				return;
				
			}
			for(int i=idx;i<numberOfElements;i++)
			{
				solutionSet.push(set[i]);
				solve(s+set[i],i+1);
				solutionSet.pop();
			}
		}
		void displaySolutionSet()
		{
			stack<int> temp;
			while(!solutionSet.empty())
			{
				cout<<solutionSet.top()<<" ";
				temp.push(solutionSet.top());
				solutionSet.pop();
			}
			cout<< '\n';
			while(!temp.empty())
			{
				solutionSet.push(temp.top());
				temp.pop();
				
			}
		}
    };
    int main()
    {
	Subset ss;
	ss.solve(0,0);
	if(ss.hasSolution==false)
	cout<<"no solution";
	return 0;
	
    }
   
     out put:
   ![image](https://user-images.githubusercontent.com/19484531/163926238-77f5ccd3-c237-4cb5-a714-6f34d18490af.png)


     program 8: Write a C++ program for implementing doubly Linked list
     
     #include<iostream>
			#include<cstdio>
			#include<cstdlib>
			/*
			 * Node Declaration
			 */
			using namespace std;
			struct node
			{
			    int info;
			    struct node *next;
			    struct node *prev;
			}*start;
			 
			/*
			 Class Declaration 
			 */
			class double_llist
			{
			    public:
			        void create_list(int value);
			        void add_begin(int value);
			        void add_after(int value, int position);
			        void delete_element(int value);
			        void display_dlist();
			        double_llist()
			        {
			            start = NULL;  
			        }
			};
			 
			/*
			 * Main: Conatins Menu
			 */
			int main()
			{
			    int choice, element, position;
			    double_llist dl;
			    while (1)
			    {
			        cout<<endl<<"----------------------------"<<endl;
			        cout<<endl<<"Operations on Doubly linked list"<<endl;
			        cout<<endl<<"----------------------------"<<endl;         
			        cout<<"1.Create Node"<<endl;
			        cout<<"2.Add at begining"<<endl;
			        cout<<"3.Add after position"<<endl;
			        cout<<"4.Delete"<<endl;
			        cout<<"5.Display"<<endl;
			        cout<<"6.Quit"<<endl;
			        cout<<"Enter your choice : ";
			        cin>>choice;
			        switch ( choice )
			        {
			        case 1:
			            cout<<"Enter the element: ";
			            cin>>element;
			            dl.create_list(element);
			            cout<<endl;
			            break;
			        case 2:
			            cout<<"Enter the element: ";
			            cin>>element;
			            dl.add_begin(element);
			            cout<<endl;
			            break;
			        case 3:
			            cout<<"Enter the element: ";
			            cin>>element;
			            cout<<"Insert Element after postion: ";
			            cin>>position;
			            dl.add_after(element, position);
			            cout<<endl;
			            break;
			        case 4:
			            if (start == NULL)
			            {                      
			                cout<<"List empty,nothing to delete"<<endl;   
			                break;
			            }
			            cout<<"Enter the element for deletion: ";
			            cin>>element;
			            dl.delete_element(element);
			            cout<<endl;
			            break;
			        case 5:
			            dl.display_dlist();
			            cout<<endl;
			            break;
			        case 6:
			            exit(1);
			        default:
			            cout<<"Wrong choice"<<endl;
			        }
			    }
			    return 0;
			}
			 
			/*
			 * Create Double Link List
			 */
			void double_llist::create_list(int value)
			{
			    struct node *s, *temp;
			    temp = new(struct node); 
			    temp->info = value;
			    temp->next = NULL;
			    if (start == NULL)
			    {
			        temp->prev = NULL;
			        start = temp;
			    }
			    else
			    {
			        s = start;
			        while (s->next != NULL)
			            s = s->next;
			        s->next = temp;
			        temp->prev = s;
			    }
			}
			 
			/*
			 * Insertion at the beginning
			 */
			void double_llist::add_begin(int value)
			{
			    if (start == NULL)
			    {
			        cout<<"First Create the list."<<endl;
			        return;
			    }
			    struct node *temp;
			    temp = new(struct node);
			    temp->prev = NULL;
			    temp->info = value;
			    temp->next = start;
			    start->prev = temp;
			    start = temp;
			    cout<<"Element Inserted"<<endl;
			}
			 
			/*
			 * Insertion of element at a particular position
			 */
			void double_llist::add_after(int value, int pos)
			{
			    if (start == NULL)
			    {
			        cout<<"First Create the list."<<endl;
			        return;
			    }
			    struct node *tmp, *q;
			    int i;
			    q = start;
			    for (i = 0;i < pos - 1;i++)
			    {
			        q = q->next;
			        if (q == NULL)
			        {
			            cout<<"There are less than ";
			            cout<<pos<<" elements."<<endl;
			            return;
			        }
			    }
			    tmp = new(struct node);
			    tmp->info = value;
			    if (q->next == NULL)
			    {
			        q->next = tmp;
			        tmp->next = NULL;
			        tmp->prev = q;      
			    }
			    else
			    {
			        tmp->next = q->next;
			        tmp->next->prev = tmp;
			        q->next = tmp;
			        tmp->prev = q;
			    }
			    cout<<"Element Inserted"<<endl;
			}
			 
			/*
			 * Deletion of element from the list
			 */
			void double_llist::delete_element(int value)
			{
			    struct node *tmp, *q;
			     /*first element deletion*/
			    if (start->info == value)
			    {
			        tmp = start;
			        start = start->next;  
			        start->prev = NULL;
			        cout<<"Element Deleted"<<endl;
			        free(tmp);
			        return;
			    }
			    q = start;
			    while (q->next->next != NULL)
			    {   
			        /*Element deleted in between*/
			        if (q->next->info == value)  
			        {
			            tmp = q->next;
			            q->next = tmp->next;
			            tmp->next->prev = q;
			            cout<<"Element Deleted"<<endl;
			            free(tmp);
			            return;
			        }
			        q = q->next;
			    }
			     /*last element deleted*/
			    if (q->next->info == value)    
			    { 	
			        tmp = q->next;
			        free(tmp);
			        q->next = NULL;
			        cout<<"Element Deleted"<<endl;
			        return;
			    }
			    cout<<"Element "<<value<<" not found"<<endl;
			}
			 
			/*
			 * Display elements of Doubly Link List
			 */
			void double_llist::display_dlist()
			{
			    struct node *q;
			    if (start == NULL)
			    {
			        cout<<"List empty,nothing to display"<<endl;
			        return;
			    }
			    q = start;
			    cout<<"The Doubly Link List is :"<<endl;
			    while (q != NULL)
			    {
			        cout<<q->info<<" <-> ";
			        q = q->next;
			    }
			    cout<<"NULL"<<endl;
			}
		
   output: 
   ![image](https://user-images.githubusercontent.com/19484531/163936805-4285c278-8122-4586-9b6b-3c7b9e2670bf.png)
![image](https://user-images.githubusercontent.com/19484531/163936840-67149601-b00a-4da0-8e54-65c874173225.png)
![image](https://user-images.githubusercontent.com/19484531/163936875-7486568a-b05c-450c-a6d9-f1283df9721d.png)
![image](https://user-images.githubusercontent.com/19484531/163936900-07913881-c668-49ce-b1d1-746d5672f0bb.png)

    
    

     program 9: Write C++ program to implement merge sort technique using divide and conquer method
			
			#include <iostream>
			#include<conio.h>
			using namespace std;
			void Merge(int *a, int low, int high, int mid)
			{
			int i, j, k, temp[high-low+1];
			i = low;
			k = 0;
			j = mid + 1;
			while (i <= mid && j <= high)
			{
				if (a[i] < a[j])
				{
					temp[k] = a[i];
					k++;
					i++;
				}
				else
				{
					temp[k] = a[j];
					k++;
					j++;
				}
			}
			while (i <= mid)
			{
				temp[k] = a[i];
				k++;
				i++;
			}
			while (j <= high)
			{
				temp[k] = a[j];
				k++;
				j++;
			}
			for (i = low; i <= high; i++)
			{
				a[i] = temp[i-low];
			}
			 }
			 void MergeSort(int *a, int low, int high)
			 {
			int mid;
			if (low < high)
			{
				mid=(low+high)/2;
					MergeSort(a, low, mid);
				              MergeSort(a, mid+1, high);
					Merge(a, low, high, mid);
			}
			}
			int main()
			 {
			int n, i;
			cout<<"\nEnter the number of data element to be sorted: ";
			cin>>n;
			
			int arr[n];
			for(i = 0; i < n; i++)
			{
				cout<<"Enter element "<<i+1<<": ";
				cin>>arr[i];
			}
			MergeSort(arr, 0, n-1);
			cout<<"\nSorted Data ";
			for (i = 0; i < n; i++)
			    cout<<"->"<<arr[i];
			getch();
			 }		

output:
![image](https://user-images.githubusercontent.com/19484531/163937019-21b94626-a7f5-437b-9222-6ba4d692f3cc.png)

 
 
    program 10: WAP to store k keys into an array of size n at the location computed using a hash function, loc = key % n, where k<=n and Key takes values from [1 to m], m>n. Handle the collision using Linear probing technique.
    
    #include<iostream>
    #include<limits.h>
    using namespace std;
    void Insert(int ary[],int hFn, int Size)
     {
     int element,pos,n=0;
     cout<<"Enter key element to insert\n";
     cin>>element;
    pos = element%hFn; 
    while(ary[pos]!= INT_MIN)
    {  
        if(ary[pos]== INT_MAX)
        break;
        pos = (pos+1)%hFn;
        n++;
        if(n==Size)
        break;     
    }
    if(n==Size)
    cout<<"Hash table was full of elements\nNo Place to insert this element\n\n";
    else
    ary[pos] = element;    
    }
    void display(int ary[],int Size) 
    {
    int i;

    cout<<"Index\tValue\n";
    for(i=0;i<Size;i++)
    cout<<i<<"\t"<<ary[i]<<"\n";
     }
    int main() 
    {
    int Size,hFn,i,choice;
    cout<<"Enter size of hash table\n";
    cin>>Size;
    hFn=Size;
    int ary[Size];
    for(i=0;i<Size;i++)
    ary[i]=INT_MIN; 
    do
     {
    cout<<"Enter your choice\n";
    cout<<" 1-> Insert\n 2-> Display\n 0-> Exit\n";
    cin>>choice;
    switch(choice) 
     {
       case 1:
       Insert(ary,hFn,Size);
       break;
       case 2:
       display(ary,Size);
       break;
       default:
       cout<<"Enter correct choice\n";
       break;
    }
    }while(choice);
    return 0;
    }
  ![image](https://user-images.githubusercontent.com/19484531/163937438-7d648d24-7aab-4d87-aaf3-577935fc3930.png)


    program 11: Write a C++ program for solving the N-Queen’s Problem using backtracking
    
    #include<iostream>
		using namespace std;
		int grid[100][100];
		//print the solution
		void print(int n) {
		    for (int i = 0;i <= n-1; i++) {
		        for (int j = 0;j <= n-1; j++) {
		           
		                cout <<grid[i][j]<< " ";
		           
		        }
		        cout<<endl;
		    }
		    cout<<endl;
		    cout<<endl;
		}
		//function for check the position is safe or not
		//row is indicates the queen no. and col represents the possible positions
		bool isSafe(int col, int row, int n) {
		  //check for same column
		    for (int i = 0; i < row; i++) {
		        if (grid[i][col]) {
		            return false;
		        }
		    }
		    //check for upper left diagonal
		    for (int i = row,j = col;i >= 0 && j >= 0; i--,j--) {
		        if (grid[i][j]) {
		            return false;
		        }
		    }
		    //check for upper right diagonal
		    for (int i = row, j = col; i >= 0 && j < n; j++, i--) {
		        if (grid[i][j]) {
		            return false;
		        }
		    }
		    return true;
		}
		//function to find the position for each queen
		//row is indicates the queen no. and col represents the possible positions
		bool solve (int n, int row) {
		    if (n == row) {
		        print(n);
		        return true;
		    }
		    //variable res is use for possible backtracking
		    bool res = false;
		    for (int i = 0;i <=n-1;i++) {
		        if (isSafe(i, row, n)) {
		            grid[row][i] = 1;
		            //recursive call solve(n, row+1) for next queen (row+1)
		            res = solve(n, row+1) || res;//if res ==false then backtracking will occur
		            //by assigning the grid[row][i] = 0
		           
		            grid[row][i] = 0;
		        }
		    }
		    return res;
		}
		int main()
		{
		  ios_base::sync_with_stdio(false);
		    cin.tie(NULL);
		        int n;
		        cout<<"Enter the number of queen"<<endl;
		        cin >> n;
		        for (int i = 0;i < n;i++
		            for (int j = 0;j < n;j++) {
		                grid[i][j] = 0;
		            }
		        }
		        bool res = solve(n, 0);
		        if(res == false) {
		            cout << -1 << endl; //if there is no possible solution
		        } else {
		            cout << endl;
		        }
		  return 0;
		}
		
     output:
  ![image](https://user-images.githubusercontent.com/19484531/163938093-19c8678c-b9c4-4023-9e0c-8c8d3b96ee0d.png)
  
  
  
     BFS:
  
    #include<iostream>
    #include<conio.h>
    #include<stdlib.h>
    using namespace std;
    int cost[10][10],qu[10],front,rare,visit[10],visited[10];
    int main()
    {

    int m,n,j,i,v,k;
    cout <<"Enter no of vertices:";
    cin >> n;
    cout <<"Enter no of edges:";
    cin >> m;
    cout <<"\nEDGES \n";
    for(k=1; k<=m; k++)
    {
        cin >>i>>j;                                                            
        cost[i][j]=1;
    }
    cout <<"Enter initial vertex to traverse from:";
    cin >>v;
    cout <<"BFS of Visitied vertices:";
    cout <<v<<" ";
    visited[v]=1;
    k=1;
    while(k<n)
    {
         for(j=1; j<=n; j++)
            if(cost[v][j]!=0 && visited[j]!=1 && visit[j]!=1)
            {
                visit[j]=1;
                qu[rare++]=j;
            }
        v=qu[front++];
        cout<<v <<" ";
        k++;
        visit[v]=0;
        visited[v]=1;
    }
    return 0;
    
   }
   
   
     DFS:
   
     #include<iostream>
    #include<conio.h>
    #include<stdlib.h>
    using namespace std;
    int cost[10][10],i,j,k,n,stk[10],top,v,visit[10],visited[10];
    int main()
      {
    int m;
    cout <<"Enter no of vertices:";
    cin >> n;
    cout <<"Enter no of edges:";
    cin >> m;
    cout <<"\nEDGES \n";
    for(k=1; k<=m; k++)
    {
        cin >>i>>j;
        cost[i][j]=1;
    }
    cout <<"Enter initial vertex to traverse from:";
    cin >>v;
    cout <<"DFS ORDER OF VISITED VERTICES:";
    cout << v <<" ";
    visited[v]=1;
    k=1;
    while(k<n)
    {
        for(j=n; j>=1; j--)
            if(cost[v][j]!=0 && visited[j]!=1 && visit[j]!=1)
            {
                visit[j]=1;
                stk[top]=j;
                top++;
            }
        v=stk[--top];
        cout<<v << " ";
        k++;
        visit[v]=0;
        visited[v]=1;
    }
    return 0;
    }


Tower of hanoi

      #include <iostream>
       using namespace std;
        void towers(int, char, char, char);
           int main()
      {
         int num;
         cout<<"Enter the number of disks : ";
         cin>>num;
           cout<<"The sequence of moves involved in the Tower of Hanoi are :\n";
           towers(num, 'A', 'C', 'B');
            return 0;
          }
         void towers(int num, char frompeg, char topeg, char auxpeg)
            {
         if (num == 1)
            {
        cout<<"Move disk 1 from peg "<<frompeg<<" to peg "<<topeg<<"\n";
        return;
             }
           towers(num - 1, frompeg, auxpeg, topeg);
             cout<<"Move disk "<<num<<" from peg "<<frompeg<<" to peg "<<topeg<<"\n";
              towers(num - 1, auxpeg, topeg, frompeg);
           }
	

	out put 
![image](https://user-images.githubusercontent.com/19484531/167391344-cb9ba14e-5fca-4c09-be64-e5ab105599cc.png)


                 Write a C++ program to count the number of connected components in an undirected graph
			#include <iostream>
			#include <list>
			using namespace std;
			class Graph {
			int V; 
			list<int>* adj;
			void DFSUtil(int v, bool visited[]);
			public:
			Graph(int V); 
			~Graph();
			void addEdge(int v, int w);
			void connectedComponents();
			};
			void Graph::connectedComponents()
			{
			bool* visited = new bool[V];
			for (int v = 0; v < V; v++)
			visited[v] = false;
			for (int v = 0; v < V; v++) {
			if (visited[v] == false) {
			DFSUtil(v, visited);
			cout << "\n";
			}
			}
			delete[] visited;
			}
			void Graph::DFSUtil(int v, bool visited[])
			{
			visited[v] = true;
			cout << v << " ";
			list<int>::iterator i;
			for (i = adj[v].begin(); i != adj[v].end(); ++i)
			if (!visited[*i])
			
			DFSUtil(*i, visited);
			}
			Graph::Graph(int V)
			{
			this->V = V;
			adj = new list<int>[V];
			}
			Graph::~Graph() { delete[] adj; }
			void Graph::addEdge(int v, int w)
			{
			adj[v].push_back(w);
			adj[w].push_back(v);
			}
			int main()
			{
			Graph g(5); 
			g.addEdge(1, 0);
			g.addEdge(2, 3);
			g.addEdge(3, 4);
			cout << "Following are connected components \n";
			g.connectedComponents();
			return 0;
			}


![image](https://user-images.githubusercontent.com/19484531/167393205-bf359fa7-11af-4304-9a73-d51db1caa9c3.png)



