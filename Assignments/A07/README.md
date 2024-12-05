## **Leetcode 703: Kth Largest Element in a Stream**

**Problem**

![image](https://github.com/user-attachments/assets/02691719-1a7a-4c4f-ba57-415afde9d534)



**Test Case(s):**


![image](https://github.com/user-attachments/assets/7ba219e6-c242-47a2-965e-3e59213f0d1f)


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


