# DSA_Link
//反转链表（head是不带哨兵的链表）
struct ListNode {
      int val;
      ListNode *next;
};
//迭代法
ListNode* reverseList(ListNode* head) {
    ListNode *pre=NULL,*p=head;
    while(p!=NULL){
    	ListNode *ntemp=p->next;
		  p->next=pre;
		  pre=p;
		  p=ntemp;  
	}
    return pre;
};
//递归法
class Solution {
public:
    ListNode* reverse(ListNode *pre,ListNode *cur){
        if(cur==NULL)return pre;
        ListNode *temp=cur->next;
        cur->next=pre;
        pre=cur;
        cur=temp;
        return reverse(pre,cur);
    }
    ListNode* reverseList(ListNode* head) {
        return reverse(NULL,head);
    }
};
