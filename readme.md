**Implementation of Observables in Vanilla JS**

```javascript
class VanillaJavascriptObservable {
    constructor() {
        this.subscribers = [];
    }
    
    subscribe(cb) {
        this.subscribers.push(cb);
    }

    unsubscribe() {
        // TODO ¯_(ツ)_/¯
        this.subscribers = [];
    }

    emit(value) {
        if(this.subscribers)
            this.subscribers.forEach(cb => cb(value));
    }
};

// Create new Observables
const posts = new VanillaJavascriptObservable();
const comments = new VanillaJavascriptObservable();

// 2 time subscribe to observable to check
posts.subscribe(v => console.log(`1 - ${v} FROM posts`));
posts.subscribe(v => console.log(`2 - ${v} FROM posts`));

// Subscribe to comment
comments.subscribe(v => console.log(`${v} FROM comments`));

// Emit message to all subscribers
posts.emit('hello');
comments.emit('hi there');

```
