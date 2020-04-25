# Segment Trees
## pseudocode
```cpp
struct Node {
    int l, r;
    Node *lc, *rc;
    int max;
    
    Node(int l, int r) : l(l), r(r), lc(nullptr), rc(nullptr), max(0) {
    }
    
    void clean() {
        if (l != r && !lc) {
            int m = (l + r) / 2;
            lc = new Node(l, m);
            rc = new Node(m + 1, r);
        }
    }
    
    void set(int p, int v) {
        clean();
        
        if (p < l || p > r) {
            return;
        }
        
        if (l == r) {
            max = v;
            return;
        }
        
        lc->set(p, v);
        rc->set(p, v);
        max = std::max(lc->max, rc->max);
    }
    
    int query(int ql, int qr) {
        clean();
        
        if (qr < l || ql > r) {
            return 0;
        }
        
        if (ql <= l && qr >= r) {
            return max;
        }
        
        return std::max(lc->query(ql, qr), rc->query(ql, qr));
    }
};
```
