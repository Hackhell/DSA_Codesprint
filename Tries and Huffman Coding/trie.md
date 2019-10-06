<h1>Trie</h1>

### Trie Implementation
Insert in O(|S|) and Erase in O(|S|)

```cpp
struct node {
	node *p[26];
	int count;
	node() {
		count=0;
		memset(p, 0, sizeof(p));
	}
}

class trie {
    node *root;
    public:
	
    trie(){
        root = new node()
    }

    void insert(char *s){
        node *x = root;
        int length = strlen(s);
        for (int i = 0; i < length; i++) {
            if (x->p[s[i] - 'a'] == NULL) {
                x->p[s[i] - 'a'] = new node()
            }
            x = x->p[s[i] - 'a'];
        }
        x->count++;
    }
	
    void erase(char *s){
        node *x = root;
        int length = strlen(s);
        for (int i = 0; i < length; i++) {
            x = x->p[s[i] - 'a'];
        }
        x->count--;
    }
	
};
```
