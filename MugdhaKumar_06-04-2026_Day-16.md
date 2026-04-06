class MyQueue {
private:
    stack<int> incoming, outgoing;
    
public:
    MyQueue() {}
    
    void push(int x) {
        incoming.push(x);
    }
    
    int pop() {
        peek();
        int res = outgoing.top();
        outgoing.pop();
        return res;
    }
    
    int peek() {
        if (outgoing.empty()) {
            while (!incoming.empty()) {
                outgoing.push(incoming.top());
                incoming.pop();
            }
        }
        return outgoing.top();
    }
    
    bool empty() {
        return incoming.empty() && outgoing.empty();
    }
};

/**
 * Your MyQueue object will be instantiated and called as such:
 * MyQueue* obj = new MyQueue();
 * obj->push(x);
 * int param_2 = obj->pop();
 * int param_3 = obj->peek();
 * bool param_4 = obj->empty();
 */
