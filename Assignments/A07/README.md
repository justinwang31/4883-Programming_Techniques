## **Leetcode 703: Kth Largest Element in a Stream**

**Problem**

![image](https://github.com/user-attachments/assets/02691719-1a7a-4c4f-ba57-415afde9d534)



**Test Case(s):**

![image](https://github.com/user-attachments/assets/ac65b188-5241-4fd1-81d9-4def2c738143)

![image](https://github.com/user-attachments/assets/d0676046-9a0b-4dc8-b209-ce7c3227e50b)



**Code Solution**

```
class KthLargest {
private:
    int k;
    priority_queue<int, vector<int>, greater<int>> minHeap;

public:
    KthLargest(int k, vector<int>& nums) {
        this->k = k;
        for (int num : nums) {
            add(num);
        }
    }

    int add(int val) {
        minHeap.push(val);
        if (minHeap.size() > k) {
            minHeap.pop();
        }
        return minHeap.top();
    }
};
```


