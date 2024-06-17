# Insert-at-middle
Insert an element at middle of a singly linked list
//Insert element at middle position
#include<iostream>
using namespace std;

struct Node{
	int data;
	Node* next;
	Node(int d){
		data=d;
		next=NULL;
	}
};

Node* insertMid(Node* head,int x){
	Node* temp=new Node(x);
	int count=0;
	Node* curr=head;
	while(curr!=NULL){
		count++;
		curr=curr->next;
	}
	Node* p1=head;
	for(int i=1;i<=count/2;i++){
		p1=p1->next;
	}
	temp->next=p1->next;
	p1->next=temp;
	return head;
}

Node* insertAtEnd(Node* head,int y){
	Node* temp = new Node(y);
	if(head==NULL){
		return temp;
	}
	Node* curr=head;
	while(curr->next!=NULL){
		curr=curr->next;
	}
	curr->next=temp;
	return head;
}

void printList(Node* head){
	Node* curr=head;
	while(curr!=NULL){
		cout<<curr->data;
		curr=curr->next;
	}
}

int main(){
	Node* head=NULL;
	int n;
	cin>>n;
	for(int i=1;i<=n;i++){
		int x;
		cin>>x;
		head=insertAtEnd(head,x);
	}
	printList(head);
	insertMid(head,30);
	printList(head);
	return 0;
	
}
