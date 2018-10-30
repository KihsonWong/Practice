#include "stdio.h"
#include "ctype.h"
#include "malloc.h"

typedef struct node {
	int data;
	struct node *next;
} Node;

Node *New_Node()
{
	Node *p = (Node*)malloc(sizeof(Node));
	if(p==NULL){
		printf("creat new node fail!");
		return NULL;
	}
	p->next = NULL;
	return p;
}

Node *New_Node1(int val)
{
	Node *p = (Node*)malloc(sizeof(Node));
	if(p==NULL){
		printf("creat new node fail!");
		return NULL;
	}
	p->data = val;
	p->next = NULL;
	return p;
}

Node *New_Node2()
{
	Node *p = (Node*)malloc(sizeof(Node));
	if(p==NULL){
		printf("creat new node fail!");
		return NULL;
	}
	printf("please input new node data: ");
	scanf("%d", &p->data);
	p->next = NULL;
	return p;
}

Node *BuildList()
{
	Node *p, *head = NULL, *tail = NULL;
	char c;
	printf("Add new node?y/n:");
	while((c=getchar())=='\n');
	while(tolower(c)!='n'){
		p = New_Node2();
		if(head==NULL) head = p;
		else tail->next = p;
		tail = p;
		printf("Add new node?y/n:");
		while((c=getchar())=='\n');
	}
	return head;
}

printf_List(Node *head_node)
{
	printf("\nThe List contains:\n");
	for(;head_node!=NULL;head_node=head_node->next)
		printf("%4d",head_node->data);
	printf("\tFinish\n");
}

void ClearlList(Node **head_ptr)
{
	Node *node = *head_ptr;
	while(*head_ptr){
		node = (*head_ptr)->next;
		free(*head_ptr);
		*head_ptr = node;
	}
}

int main(int argc, char **argv)
{
	Node *head;
	head = BuildList();
	printf_List(head);
	ClearlList(&head);
	printf_List(head);
	return 0;
}
