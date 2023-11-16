//header library
#include <iostream>
using namespace std;

//Node structure for the linked list
struct Node 
{
    int data;
    Node* next; // pointer to the next node
};
//linked list class
class LinkedList 
{
    private:
        Node* head; //pointer for the 1st node
    public:
        LinkedList() 
		{
            head = NULL; //Initializing head 
        }
        //Node at the beginning of the linked list
        void insertAtBeginning(int data)
		 {
            Node* newNode = new Node; // create a new node
            newNode->data = data; //setting data for new node 
            newNode->next = head;
            head = newNode; // setting head for new node
        }
        //inserting the node at any n position in the linked list
        void insertAtN(int data, int position) 
		{
            Node* newNode = new Node;  //creating new node
            newNode->data = data; //setting data for new node
            newNode->next = NULL; //setting next data to null

            if (position == 1) //condition
			{
                newNode->next = head;  //setting next of new node to head
                head = newNode; //initializing head with new node
                return; //exit the funtion
            }
            Node* temp = head;  //setting temp equal to head
            for (int i = 1; i < position - 1; i++) //loop for reaching the position
			{
                temp = temp->next; //moving to the next node
            }
            newNode->next = temp->next;
            temp->next = newNode; //setting next of temp node to new node.
        }
        // Delete the first node of the linked list
        void deleteFromBeginning()
		 {
            if (head == NULL) //condition
			{
                cout << "The linked list is empty." << endl; //checking if the link list is empty
                return;
            }

            Node* temp = head; //initializing temp with head
            head = head->next; //setting head to next node
            delete temp; //deleting
        }
        // Delete the last node of the linked list
        void deleteFromEnd() 
		{
            if (head == NULL)                            //condition
			{
                cout << "The linked list is empty." << endl; //printing the msg if list is empty
                return;
            }
            if (head->next == NULL)                 //condition
			{
                delete head;                  //deleting the head
                head = NULL;                    //setting head to null
                return;                         //exit the function
            }
            Node* temp = head; //setting temp equal to head
            while (temp->next->next != NULL) 
			{
                temp = temp->next; //setting temp with next node
            }
            delete temp->next;           //deleting node at position
            temp->next = NULL;                //setting next node to null
        }
        // Delete a node from any n position in the linked list
        void deleteFromN(int position)
		 {
            if (head == NULL) {
                cout << "The linked list is empty." << endl; //error msg
                return;
            }

            Node* temp = head;
            if (position == 1)                         //condition 
			 {
                head = temp->next;            // setting head to next
                delete temp;                  //deleting temp
                return;                       //exit the function
            }
            for (int i = 1; temp != NULL && i < position - 1; i++) //loop for reaching the position
			 {
                temp = temp->next; //setting temp node to next
            }
            if (temp == NULL || temp->next == NULL) //if position is greater than length of list
			{
                return;
            }

            Node* next = temp->next->next;// create a new node and set it to the next of the temp node
            delete temp->next;                    // delete the node at the position
            temp->next = next;        // set the next of the temp node to the new node
        }
        // Search for a node in the linked list
        Node* search(int data) 
		{
            Node* temp = head;           // create a temp node and set it to the head
            while (temp != NULL)       // loop through the list until the end is reached
			 {
                if (temp->data == data) // if the data of the node is equal to the search data
				 {
                    return temp; 
                }
                temp = temp->next;  //setting temp node to next node
            }
            return NULL;
        }
        // Update a node at any n position in the linked list
        void updateAtN(int data, int position)
		 {
            Node* temp = head;
            for (int i = 1; temp != NULL && i < position; i++) //loop for reaching the  position 
			 {
                temp = temp->next; //moving to the next node
            }
            temp->data = data;           //setting data for temp node
        }

        // Display the linked list
        void display() {
            Node* temp = head; 
            while (temp != NULL)   //using while loop for condition
			{
                cout << temp->data << " ";    //printing the data 
                temp = temp->next;               //setting temp to next
            }
            cout << endl;
        }
};
int main() 
{
    LinkedList list;

    // Insert nodes at the beginning
    list.insertAtBeginning(5);
    list.insertAtBeginning(4);
    list.insertAtBeginning(3);
    list.insertAtBeginning(2);
    list.insertAtBeginning(1);

    // Display the linked list
    cout << "Linked list: ";
    list.display(); //displaying the link list

    // Search for a node
    Node* node = list.search(4);
    if (node != NULL) {
        cout << "Node found: " << node->data << endl; //for searching node 
    } else {
        cout << "Node not found." << endl; //error msg if the given node is not found
    }

    // Update a node
    list.updateAtN(10, 3);
    cout << "Linked list after updating node at position 3: ";
    list.display(); // displaying after updating 

    // Insert a node at any n position
    list.insertAtN(6, 3);
    cout << "Linked list after inserting node at position 3: ";
    list.display(); //displaying after inserting node 
    
    // Delete the first node of the linked list
    list.deleteFromBeginning();
    cout<<"Link list after deleting from the start: ";
    list.display(); //displaying the node  
    
    // Delete a node from any n position in the linked list
    list.deleteFromN(2);
    cout<<"Link list after deleting node from position 2 : ";
    list.display(); //displaying node after deleting from 2nd position 
    
     // Delete the last node of the linked list
     list.deleteFromEnd();
     cout<<"Link list after deleting from the end : ";
     list.display();//displaying node after deleting from end 
    
}
