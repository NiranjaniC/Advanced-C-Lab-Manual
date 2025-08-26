EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:
```
struct Node{
    int data; 
    struct Node *next;
} *head;

void search(int data)
{
    struct Node *temp = head; 
    int position = 1; 

    while (temp != NULL){
        if (temp->data == data){
            printf("item %d found at location %d\n", data, position);
            return;
        }
        temp = temp->next;
        position++; 
    }
    printf("Item not found\n"); 
}
```
Output:

<img width="1094" height="426" alt="image" src="https://github.com/user-attachments/assets/a22dc19a-8481-4eb5-87d0-aac10c202f6f" />

Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:
```
struct Node{
    int data; 
    struct Node *next;
}*head;


void insert(int data){
    struct Node *newnode = (struct Node*)malloc(sizeof(struct Node));
    newnode->data=data;
    newnode->next=NULL;
    if (head==NULL){
        head=newnode;
    }
    else{
        struct Node *temp=head;
        while(temp->next !=NULL){
            temp=temp->next;
        }
        temp->next=newnode;
        return;
    }
}
```
Output:
<img width="1095" height="419" alt="image" src="https://github.com/user-attachments/assets/95a2465e-1f72-453b-8ab6-1c3f5b8d6bf2" />

Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:
```
struct Node
{
    struct Node *prev;
    struct Node *next;
    int data;
}*head;

void display()
{
     struct Node *temp = head;

    while (temp != NULL) {
        printf("%d\n", temp->data);
        temp = temp->next;
    }
    
    
    
    
}
```
Output:

<img width="1098" height="406" alt="image" src="https://github.com/user-attachments/assets/26738031-fd6b-4b26-ad50-e9e509f88e24" />

Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:
```
struct Node
{
    struct Node *prev;
    struct Node *next;
    float data;
}*head;

void insert(float data)
{
    struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;

    if (!head) {
        head = newNode;
        return;
    }

    struct Node *temp = head;
    while (temp->next) temp = temp->next;

    temp->next = newNode;
    newNode->prev = temp;
    
    
    
}
```
Output:

<img width="1093" height="410" alt="image" src="https://github.com/user-attachments/assets/0fd9bd28-4415-480a-8cad-8c4652e48ef2" />

Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


Program:
```
struct Node{
    float data; 
    struct Node *next;
}*head;
void delete()
{
    struct Node*temp;
    if(head==NULL)
    {
        printf("List is empty\n");
    }
    else
    {
        temp=head;
        head=temp->next;
        free(temp);
        printf("Node deleted from the begining ...\n");
    }
    
    
}
```
Output:

<img width="1360" height="542" alt="image" src="https://github.com/user-attachments/assets/82407171-a3fa-4d6d-9367-f1d1d53ffbd7" />

Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





