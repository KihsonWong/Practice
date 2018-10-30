#include "stdio.h"
#include "malloc.h"
#include "assert.h"

typedef struct node{
	int data;
	struct node *last;
	struct node *next;
} Node;

Node* CreatDoubleList()
{
	int i, node_num;
	Node *head, *lst;
	Node *index;
	head = (Node*)malloc(sizeof(Node));
	assert(head!=NULL);
	head->data = 0;
	head->last = NULL;
	head->next = NULL;

	printf("Please input the double list node number: ");
	scanf("%d", &node_num);
	printf("Please input no.1: ");
	scanf("%d",  &head->data);
	
	lst = head;

	for(i=2;i<node_num+1;i++){
		index = (Node*)malloc(sizeof(Node));
		printf("Please input no.%d: ", i);
		scanf("%d",  &index->data);
		lst->next = index;
		index->last = lst;
		lst = lst->next;
		index->next = NULL;
	}
	
	return head;
}

Node *insert_node(Node *head)
{
	Node *new_node;
	Node *node = head;
	int i = 0, n;
	while(node!=NULL){
		i++;
		node = node->next;
	}
	printf("please input the location where the value is inserted: ");
	scanf("%d", &n);
	while(i<n){
		printf("over node number, please retype: ");
		scanf("%d", &n);
	}
	new_node = (Node*)malloc(sizeof(Node));
	printf("please input insert number: ");
	scanf("%d", &new_node->data);
	if(n==0){
		new_node->next = head;
		head->last = new_node;
		new_node->last = NULL;
		head = new_node;
	} else {
		i = 1;
		node = head;
		while(node!=NULL && (i<n)){
			i++;
			node = node->next;
		}
		new_node->last = node;
		new_node->next = node->next;
		node->next = new_node;
		if(new_node->next!=NULL)
			new_node->next->last = new_node;
	}
	return head;
}

Node *delete_node(Node* head)
{
	Node *node = head;
	int n, i = 1,node_num = 1;
	printf("please input the node witch you want to detele: ");
	scanf("%d", &n);

	while(node->next!=NULL){
		node = node->next;
		node_num++;
	}
	if(n>node_num){
		printf("Error...no exist!\n");
	} else {
		node = head;
		while(node!=NULL && (i<n)){
			i++;
			node = node->next;
		}
		if(n==1){
			head = head->next;
			node->next->last = NULL;
		} else if(node_num==n){
			node->last->next = NULL;
		} else {
			node->last->next = node->next;
			node->next->last = node->last;
		}
		free(node);
	}
	return head;
}

void print_all_node(Node *head)
{
	Node *node;
	int i;
	for(i=1,node = head;node!=NULL;node=node->next,i++){
		printf("the no.%d node value is: %d\n", i, node->data);
	}
}

int main(int argc, char **argv)
{
	Node *head;
	head = CreatDoubleList();
	head = insert_node(head);
	head = delete_node(head);
	print_all_node(head);
	return 0;
}
