# linked-list-code-c-
linked list code using structure in c++
//---------------------------------------********************LINKED LIST IN C++************************************---------------------------------------------------
//created by AMAN KHAIRWAR

#include<iostream>
using namespace std;
struct node
{
    int data;
    node *next;
};
void printList(node *head)
{
    node *temp=head;
    while(temp!=NULL)
    {
        cout<<temp->data<<"-->";
        temp=temp->next;
    }
    cout<<"NULL"<<endl;
}
void findMiddle(node *head)
{
    node *slow=head;
    node *fast=head;
    if(head!=NULL)
    {
        while(fast!=NULL && fast->next!=NULL)
        {
            slow=slow->next;
            fast=fast->next->next;
        }
        cout<<"the middle one is "<<slow->data<<endl;
    }
}
void removeMiddle(node *head)
{
    node *prev;
    node *slow,*fast=head;
    if(head!=NULL)
    {
        while(fast!=NULL && fast->next!=NULL)
        {
            prev=slow;
            slow=slow->next;
            fast=fast->next->next;
        }
        prev->next=slow->next;
        delete slow;
    }
}
void deleteList(node *head)
{
    node *prev=head;
    head=head->next;
    while(head!=NULL)
    {
        delete prev;
        prev=head;
        head=head->next;
    }
    //head->next=NULL;
}
void print_reverse(node *head)
{
    node *temp=head;
    if(temp==NULL)
    {
        return;
    }
    print_reverse(temp->next);
    cout<<temp->data<<"-->";
    
}
/*
void reverse(node *head)
{
    node *curr=head;
    node *prev=NULL;
    node *next;
    while(curr!=NULL)
    {
        next=curr->next;
        curr->next=prev;
        prev=curr;
        curr=next;
    }
    head=prev;
}
*/

int main()
{
    node *head=new node();
    node *second=new node();https://www.onlinegdb.com/online_c_compiler#tab-stdin
    node *three=new node();
    node *four=new node();
    node *five=new node();
    head->data=2;
    head->next=second;
    second->data=3;
    second->next=three;
    three->data=4;
    three->next=four;
    four->data=5;
    four->next=five;
    five->data=6;
    five->next=NULL;
    printList(head);
    findMiddle(head);
    //deleteList(head);
    print_reverse(head);
    cout<<"NULL";
    //reverse(head);
    //printList(head);
    return 0;
}
