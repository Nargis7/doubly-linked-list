# doubly-linked-list
#include<stdio.h>
#include<stdlib.h>
struct node 
{
    int data;
    struct node *next;
    struct node *prev;
};
struct node *head;
struct node *createnode(int data){
struct node *newnode=(struct node *)malloc(sizeof(struct node));
newnode->data=data;
newnode->next=NULL;
newnode->prev=NULL;
return newnode;
}
int main()
{
    struct node *head=createnode(10);
    struct node *second=createnode(20);
    struct node *third=createnode(30);

    head->next=second;
    second->prev=head;
    second->next=third;
    third->prev=second;

    printf("doubly linked list:\n");
    struct node *temp=head;
    while(temp)
    {
        printf("%d\n",temp->data);
        temp=temp->next;
    }
    return 0;
}
