## ১. React.js কী এবং এটি কেন ব্যবহার করা হয়?

উত্তর:
React.js হল একটি জাভাস্ক্রিপ্ট লাইব্রেরি যা ইউজার ইন্টারফেস (UI) তৈরি করতে ব্যবহৃত হয়। এটি ফেসবুক দ্বারা ডেভেলপ করা হয়েছে এবং কম্পোনেন্ট ভিত্তিক আর্কিটেকচার ব্যবহার করে। React-এর প্রধান বৈশিষ্ট্য হল এর Virtual DOM যা ওয়েব অ্যাপ্লিকেশনের পারফরম্যান্স উন্নত করে এবং ডেটা পরিবর্তনের সময় দ্রুত আপডেট প্রদান করে।

উদাহরণ:

```
import React from 'react';

function HelloWorld() {
  return <h1>Hello, World!</h1>;
}

export default HelloWorld;
```

## ২. কম্পোনেন্ট (Component) কী এবং React-এ এর প্রকারভেদ কি?

উত্তর:
কম্পোনেন্ট হল UI এর পুনঃব্যবহারযোগ্য অংশ যা অ্যাপ্লিকেশনের বিভিন্ন অংশে ব্যবহৃত হতে পারে। React-এ কম্পোনেন্ট দুটি প্রধান প্রকারের:

- Class Components: ES6 ক্লাস ব্যবহার করে তৈরি হয় এবং স্টেট ও লাইফসাইকেল মেথডস ব্যবহার করতে পারে।
- Function Components: ফাংশন হিসেবে তৈরি হয় এবং হুকস (Hooks) ব্যবহার করে স্টেট এবং অন্যান্য React ফিচার ব্যবহার করতে পারে।

উদাহরণ:

Class Component:

```
import React, { Component } from 'react';

class Welcome extends Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}

export default Welcome;
```

Function Component:

```
import React from 'react';

function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

export default Welcome;
```

## ৩. JSX কী এবং এটি কেন ব্যবহৃত হয়?

উত্তর:
JSX (JavaScript XML) হল একটি সিনট্যাক্স এক্সটেনশন যা React-এ ব্যবহৃত হয়। এটি জাভাস্ক্রিপ্টের ভিতরে HTML-এর মত টেমপ্লেট লেখার সুবিধা দেয়, যা কোডের পড়তে সহজ এবং কম্পোনেন্টের স্ট্রাকচার বোঝার ক্ষেত্রে সহায়ক।

উদাহরণ:

```
const element = <h1>Hello, JSX!</h1>;
```

## ৪. Virtual DOM কী এবং এটি কীভাবে কাজ করে?

উত্তর:
Virtual DOM হল React-এর একটি ভার্চুয়াল রিপ্রেজেন্টেশন DOM-এর। যখন কোন পরিবর্তন ঘটে, React প্রথমে Virtual DOM-এ পরিবর্তন করে এবং তারপর ডিফারেন্স এলগরিদম ব্যবহার করে প্রকৃত DOM-এ শুধুমাত্র প্রয়োজনীয় পরিবর্তনগুলো প্রয়োগ করে। এটি অ্যাপ্লিকেশনের পারফরম্যান্স বাড়ায় কারণ সরাসরি DOM ম্যানিপুলেশনের চেয়ে Virtual DOM দ্রুত কাজ করে।

উদাহরণ:

```
// যখন স্টেট পরিবর্তিত হয়, Virtual DOM আপডেট হয়
this.setState({ name: 'Alice' });
// তারপর Virtual DOM এবং বাস্তব DOM তুলনা করা হয় এবং প্রয়োজনীয় আপডেট করা হয়
```

## ৫. Props এবং State এর মধ্যে পার্থক্য কী?

উত্তর:

- Props (Properties): এগুলো হল কম্পোনেন্টে বাইরের থেকে প্রেরিত ডেটা। Props পরিবর্তনযোগ্য নয় এবং কম্পোনেন্টের ভিতরে এগুলো পরিবর্তন করা যায় না।
- State: এটি হল কম্পোনেন্টের অভ্যন্তরীণ ডেটা যা পরিবর্তনশীল। State পরিবর্তন করলে কম্পোনেন্ট পুনঃরেন্ডার হয়।
  উদাহরণ:

Props:

```
function Greeting(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

State:

```
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

## ৬. React Hooks কী এবং এর কিছু প্রধান হুকস কী কী?

উত্তর:
React Hooks হল ফাংশন যেগুলি ফাংশন কম্পোনেন্টে স্টেট এবং অন্যান্য React ফিচার ব্যবহার করতে দেয়। কিছু প্রধান হুকস হলো:

- useState: স্টেট ম্যানেজমেন্টের জন্য।
- useEffect: সাইড এফেক্ট ম্যানেজমেন্টের জন্য।
- useContext: কনটেক্সট ব্যবহারের জন্য।
- useReducer: কমপ্লেক্স স্টেট লজিকের জন্য।

উদাহরণ:

```
import React, { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `Count: ${count}`;
  }, [count]);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

## ৭. Lifecycle Methods কী এবং তাদের উদ্দেশ্য কী?

উত্তর:
Lifecycle Methods হল ক্লাস কম্পোনেন্টের বিশেষ মেথড যা কম্পোনেন্টের বিভিন্ন ধাপে এক্সিকিউট হয়, যেমন মাউন্টিং, আপডেটিং এবং আনমাউন্টিং। এগুলি কম্পোনেন্টের জীবনচক্রে নির্দিষ্ট কাজ করতে ব্যবহৃত হয়।

ক্লাস কম্পোনেন্টে কিছু প্রধান লাইফসাইকেল মেথড:

- componentDidMount: কম্পোনেন্ট DOM-এ যুক্ত হওয়ার পরে কল হয়।
- shouldComponentUpdate: কম্পোনেন্ট আপডেট হওয়ার আগে কল হয় এবং আপডেট হওয়া উচিত কিনা নির্ধারণ করে।
- componentWillUnmount: কম্পোনেন্ট DOM থেকে আনমাউন্ট হওয়ার আগে কল হয়।

Function কম্পোনেন্টে useEffect হুকের মাধ্যমে লাইফসাইকেল ম্যানেজ করা হয়।

উদাহরণ:

```
import React, { useEffect } from 'react';

function Example() {
  useEffect(() => {
    console.log('Component mounted');
    return () => {
      console.log('Component will unmount');
    };
  }, []);

  return <div>Check the console</div>;
}
```

## ৮. Higher-Order Components (HOC) কী?

উত্তর:
Higher-Order Components হল এমন একটি প্যাটার্ন যা কম্পোনেন্টকে ইনপুট হিসেবে নিয়ে একটি নতুন কম্পোনেন্ট রিটার্ন করে। এটি কোডের পুনঃব্যবহারযোগ্যতা এবং কম্পোনেন্টের লজিক শেয়ার করার জন্য ব্যবহৃত হয়।

উদাহরণ:

```
import React from 'react';

// HOC যা কম্পোনেন্টকে প্রোপ্স যোগ করে
function withGreeting(WrappedComponent) {
  return function(props) {
    return (
      <div>
        <h1>Hello!</h1>
        <WrappedComponent {...props} />
      </div>
    );
  };
}

function User(props) {
  return <p>User: {props.name}</p>;
}

const EnhancedUser = withGreeting(User);

export default EnhancedUser;
```

## ৯. React Router কী এবং এটি কীভাবে কাজ করে?

উত্তর:
React Router হল একটি লাইব্রেরি যা React অ্যাপ্লিকেশনে রাউটিং এবং নেভিগেশন হ্যান্ডল করে। এটি URL অনুযায়ী বিভিন্ন কম্পোনেন্ট রেন্ডার করতে সহায়তা করে, যা সিঙ্গল-পেজ অ্যাপ্লিকেশনের জন্য অপরিহার্য।

উদাহরণ:

```
import React from 'react';
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';
import Home from './Home';
import About from './About';

function App() {
  return (
    <Router>
      <Switch>
        <Route exact path="/" component={Home} />
        <Route path="/about" component={About} />
      </Switch>
    </Router>
  );
}

export default App;
```

## ১০. State Management Libraries কী এবং কেন এগুলি ব্যবহার করা হয়?

উত্তর:
State Management Libraries হল এমন লাইব্রেরি যা অ্যাপ্লিকেশনের স্টেটকে কেন্দ্রভিত্তিকভাবে ম্যানেজ করতে সাহায্য করে। এগুলি বড় অ্যাপ্লিকেশনে স্টেট শেয়ার এবং ম্যানেজ করা সহজ করে। কিছু জনপ্রিয় স্টেট ম্যানেজমেন্ট লাইব্রেরি হলো:

- Redux
- MobX
- Recoil

উদাহরণ (Redux):

```
// actions.js
export const increment = () => ({ type: 'INCREMENT' });

// reducer.js
const initialState = { count: 0 };

function counterReducer(state = initialState, action) {
  switch(action.type) {
    case 'INCREMENT':
      return { count: state.count + 1 };
    default:
      return state;
  }
}

export default counterReducer;

// store.js
import { createStore } from 'redux';
import counterReducer from './reducer';

const store = createStore(counterReducer);

export default store;
```

## ১১. Redux কী এবং এর প্রধান উপাদানগুলি কী কী?

উত্তর:
Redux হল একটি পূর্বাভাসযোগ্য স্টেট কন্টেইনার যা জাভাস্ক্রিপ্ট অ্যাপ্লিকেশনের জন্য ব্যবহৃত হয়। এর প্রধান উপাদানগুলো হলো:

- Store: যেখানে অ্যাপ্লিকেশনের সমস্ত স্টেট রাখা হয়।
- Actions: স্টেট পরিবর্তনের জন্য পাঠানো ইভেন্ট।
- Reducers: স্টেট পরিবর্তনের লজিক নির্ধারণ করে।

উদাহরণ:

```
// actions.js
export const increment = () => ({ type: 'INCREMENT' });

// reducer.js
const initialState = { count: 0 };

function counterReducer(state = initialState, action) {
  switch(action.type) {
    case 'INCREMENT':
      return { count: state.count + 1 };
    default:
      return state;
  }
}

export default counterReducer;

// store.js
import { createStore } from 'redux';
import counterReducer from './reducer';

const store = createStore(counterReducer);

export default store;

// App.js
import React from 'react';
import { Provider, useSelector, useDispatch } from 'react-redux';
import store from './store';
import { increment } from './actions';

function Counter() {
  const count = useSelector(state => state.count);
  const dispatch = useDispatch();

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => dispatch(increment())}>Increment</button>
    </div>
  );
}

function App() {
  return (
    <Provider store={store}>
      <Counter />
    </Provider>
  );
}

export default App;
```

## ১২. Context API কী এবং এটি কখন ব্যবহার করা হয়?

উত্তর:
Context API হল React-এর একটি ফিচার যা কম্পোনেন্ট ট্রি জুড়ে ডেটা শেয়ার করতে ব্যবহৃত হয়, বিশেষ করে প্রপ্স ড্রিলিং এড়ানোর জন্য। এটি বিভিন্ন লেভেলের কম্পোনেন্টগুলিতে প্রোপ্স পাঠানো সহজ করে তোলে।

উদাহরণ:

```
import React, { createContext, useContext } from 'react';

const ThemeContext = createContext('light');

function ThemedButton() {
  const theme = useContext(ThemeContext);
  return <button className={theme}>Button</button>;
}

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <ThemedButton />
    </ThemeContext.Provider>
  );
}

export default App;
```

## ১৩. React.memo কী এবং এটি কেন ব্যবহার করা হয়?

উত্তর:
React.memo হল একটি হাইয়ার-অর্ডার কম্পোনেন্ট (HOC) যা ফাংশন কম্পোনেন্টগুলিকে রেন্ডার অপ্টিমাইজ করতে সহায়তা করে। এটি কম্পোনেন্টের প্রপ্স অপরিবর্তিত থাকলে রেন্ডার হওয়া বন্ধ করে দেয়, ফলে পারফরম্যান্স বৃদ্ধি পায়।

উদাহরণ:

```
import React from 'react';

const ExpensiveComponent = React.memo(function({ data }) {
  // ভারী কাজের লজিক
  return <div>{data}</div>;
});

export default ExpensiveComponent;
```

## ১৪. React.lazy এবং Suspense কী এবং তারা কীভাবে কোড স্প্লিটিংয়ে সাহায্য করে?

উত্তর:

React.lazy: এটি কম্পোনেন্ট লেজি লোড করার জন্য ব্যবহৃত হয়, অর্থাৎ যখন কম্পোনেন্ট প্রয়োজন তখনই এটি লোড হয়।
Suspense: এটি লেজি লোডিং কম্পোনেন্টের সময় লোডিং স্টেট দেখানোর জন্য ব্যবহৃত হয়।
এগুলি কোড স্প্লিটিং সহজ করে, ফলে অ্যাপ্লিকেশনের প্রাথমিক লোড সময় কমে যায়।

উদাহরণ:

```
import React, { Suspense } from 'react';

const LazyComponent = React.lazy(() => import('./LazyComponent'));

function App() {
  return (
    <div>
      <Suspense fallback={<div>Loading...</div>}>
        <LazyComponent />
      </Suspense>
    </div>
  );
}

export default App;
```

## ১৫. PropTypes কী এবং এটি কেন ব্যবহৃত হয়?

উত্তর:
PropTypes হল একটি টাইপচেকিং টুল যা React কম্পোনেন্টগুলিতে প্রোপ্সের টাইপ যাচাই করতে ব্যবহৃত হয়। এটি ডেভেলপমেন্টে বাগ খুঁজে পেতে এবং কোডের গুণগত মান বজায় রাখতে সহায়তা করে।

উদাহরণ:

```
import React from 'react';
import PropTypes from 'prop-types';

function Greeting({ name, age }) {
  return <h1>Hello, {name}. You are {age} years old.</h1>;
}

Greeting.propTypes = {
  name: PropTypes.string.isRequired,
  age: PropTypes.number
};

export default Greeting;
```

## ১৬. Error Boundaries কী এবং কিভাবে কাজ করে?

উত্তর:
Error Boundaries হল React কম্পোনেন্ট যা জাভাস্ক্রিপ্ট এরর ক্যাচ করতে এবং উপযুক্ত ইউজার ফিডব্যাক প্রদানের জন্য ব্যবহৃত হয়। এগুলি শুধুমাত্র ক্লাস কম্পোনেন্টে ব্যবহার করা যায় এবং ডেরাইভড লাইফসাইকেল মেথড `componentDidCatch` এবং `getDerivedStateFromError` ব্যবহার করে।

উদাহরণ:

```
import React, { Component } from 'react';

class ErrorBoundary extends Component {
  constructor(props) {
    super(props);
    this.state = { hasError: false };
  }

  static getDerivedStateFromError(error) {
    return { hasError: true };
  }

  componentDidCatch(error, info) {
    // লগিং সার্ভিসে পাঠান
    console.log(error, info);
  }

  render() {
    if (this.state.hasError) {
      return <h1>Something went wrong.</h1>;
    }
    return this.props.children;
  }
}

export default ErrorBoundary;

// ব্যবহার:
import React from 'react';
import ErrorBoundary from './ErrorBoundary';
import SomeComponent from './SomeComponent';

function App() {
  return (
    <ErrorBoundary>
      <SomeComponent />
    </ErrorBoundary>
  );
}

export default App;
```

## ১৭. Keys কী এবং কেন এগুলো গুরুত্বপূর্ণ?

উত্তর:
Keys হল বিশেষ প্রপ্স যা React-এ তালিকার প্রতিটি উপাদানের জন্য একটি ইউনিক আইডেন্টিফায়ার হিসেবে ব্যবহৃত হয়। এগুলি লিস্ট রেন্ডার করার সময় রিয়্যাক্টকে সাহায্য করে কোন উপাদানগুলো পরিবর্তিত, যোগ বা মুছে ফেলা হয়েছে তা সনাক্ত করতে।

উদাহরণ:

```
import React from 'react';

function ItemList({ items }) {
  return (
    <ul>
      {items.map(item => (
        <li key={item.id}>{item.name}</li>
      ))}
    </ul>
  );
}

export default ItemList;
```

## ১৮. Controlled এবং Uncontrolled Components এর মধ্যে পার্থক্য কী?

উত্তর:

Controlled Components: এগুলো হল কম্পোনেন্ট যেখানে ফর্মের উপাদানগুলির মান React-এর স্টেট দ্বারা নিয়ন্ত্রিত হয়। মান পরিবর্তনের জন্য স্টেট আপডেট করা হয়।
Uncontrolled Components: এগুলো হল কম্পোনেন্ট যেখানে ফর্মের উপাদানগুলির মান DOM দ্বারা নিয়ন্ত্রিত হয়। এগুলিতে রেফারেন্স ব্যবহার করে মান পড়া হয়।

উদাহরণ:

Controlled Component:

```
import React, { useState } from 'react';

function ControlledInput() {
  const [value, setValue] = useState('');

  return (
    <input
      type="text"
      value={value}
      onChange={e => setValue(e.target.value)}
    />
  );
}

export default ControlledInput;
```

Uncontrolled Component:

```
import React, { useRef } from 'react';

function UncontrolledInput() {
  const inputRef = useRef();

  const handleSubmit = () => {
    alert(`Input Value: ${inputRef.current.value}`);
  };

  return (
    <div>
      <input type="text" ref={inputRef} />
      <button onClick={handleSubmit}>Submit</button>
    </div>
  );
}

export default UncontrolledInput;

```

## ১৯. React Fragments কী এবং কেন এগুলি ব্যবহার করা হয়?

উত্তর:
React Fragments হল উপাদান যা একাধিক উপাদানকে গ্রুপ করতে ব্যবহৃত হয় যখন কোন অতিরিক্ত DOM নোড যোগ করা না হয়। এটি JSX-এ একাধিক উপাদান রিটার্ন করার সময় উপকারী।

উদাহরণ:

```
import React from 'react';

function FragmentExample() {
  return (
    <>
      <h1>Title</h1>
      <p>Description</p>
    </>
  );
}

export default FragmentExample;
```

## ২০. Prop Drilling কী এবং কিভাবে এটি এড়ানো যায়?

উত্তর:
Prop Drilling হল এমন একটি সমস্যা যেখানে ডেটা এক উপাদান থেকে অনেকগুলো স্তরের মধ্য দিয়ে প্রোপ্স হিসেবে পাঠাতে হয়। এটি কোডকে জটিল করে এবং রক্ষণাবেক্ষণ কঠিন করে তোলে।

কিভাবে এড়ানো যায়:

Context API ব্যবহার করে ডেটা সরাসরি প্রয়োজনীয় স্তরে পাঠানো।
State Management Libraries যেমন Redux ব্যবহার করে স্টেট ম্যানেজমেন্ট করা।

উদাহরণ (Context API):

```
import React, { createContext, useContext } from 'react';

const UserContext = createContext();

function Parent() {
  const user = { name: 'Alice' };

  return (
    <UserContext.Provider value={user}>
      <Child />
    </UserContext.Provider>
  );
}

function Child() {
  return <Grandchild />;
}

function Grandchild() {
  const user = useContext(UserContext);
  return <p>User: {user.name}</p>;
}

export default Parent;
```

## ২১. useCallback এবং useMemo হুকসের মধ্যে পার্থক্য কী?

উত্তর:

useCallback: এটি একটি ফাংশনকে ক্যাশে করে রাখে, যাতে প্রপ্স হিসেবে ফাংশন পাঠানো হলে নতুন ফাংশন তৈরি না হয়। এটি রেন্ডারিং অপ্টিমাইজেশনে ব্যবহৃত হয়।
useMemo: এটি একটি হিসাব করা মানকে ক্যাশে করে রাখে, যাতে পুনরায় হিসাব না করতে হয় যতক্ষণ না নির্দিষ্ট ডিপেনডেন্সি পরিবর্তিত হয়। এটি পারফরম্যান্স অপ্টিমাইজেশনে ব্যবহৃত হয়।

উদাহরণ:

```
import React, { useState, useCallback, useMemo } from 'react';

function Example() {
  const [count, setCount] = useState(0);
  const [items, setItems] = useState([1, 2, 3]);

  const increment = useCallback(() => {
    setCount(count + 1);
  }, [count]);

  const doubledItems = useMemo(() => {
    return items.map(item => item * 2);
  }, [items]);

  return (
    <div>
      <button onClick={increment}>Count: {count}</button>
      <ul>
        {doubledItems.map(item => (
          <li key={item}>{item}</li>
        ))}
      </ul>
    </div>
  );
}

export default Example;
```

## ২২. Portals কী এবং এটি কেন ব্যবহার করা হয়?

উত্তর:
Portals হল React-এর একটি ফিচার যা একটি কম্পোনেন্টকে DOM হায়ারার্কির ভিন্ন স্থানে রেন্ডার করতে দেয়। এটি সাধারণত মডাল, টুলটিপ বা অন্যান্য ওভারলে উপাদান তৈরি করার জন্য ব্যবহৃত হয়।

উদাহরণ:

```
import React from 'react';
import ReactDOM from 'react-dom';

function Modal({ children }) {
  return ReactDOM.createPortal(
    <div className="modal">{children}</div>,
    document.getElementById('modal-root')
  );
}

export default Modal;

// ব্যবহার:
import React from 'react';
import Modal from './Modal';

function App() {
  return (
    <div>
      <h1>Main App</h1>
      <Modal>
        <p>This is a modal!</p>
      </Modal>
    </div>
  );
}

export default App;
```

## ২৩. React.lazy এবং Suspense কীভাবে কোড স্প্লিটিংয়ে সাহায্য করে?

উত্তর:
React.lazy এবং Suspense হল React-এর ফিচার যা কম্পোনেন্ট লেজি লোডিং সহজ করে তোলে। এটি কোড স্প্লিটিংয়ের মাধ্যমে অ্যাপ্লিকেশনের প্রাথমিক লোড সময় কমায় এবং পারফরম্যান্স বৃদ্ধি করে।

উদাহরণ:

```
import React, { Suspense } from 'react';

const LazyComponent = React.lazy(() => import('./LazyComponent'));

function App() {
  return (
    <div>
      <Suspense fallback={<div>Loading...</div>}>
        <LazyComponent />
      </Suspense>
    </div>
  );
}

export default App;
```

## ২৪. Reconciliation কী?

<b>উত্তর</b>:
Reconciliation হল React-এর প্রক্রিয়া যেখানে এটি Virtual DOM-কে বর্তমান DOM-এর সাথে তুলনা করে এবং ডিফারেন্স খুঁজে বের করে। তারপর শুধুমাত্র প্রয়োজনীয় পরিবর্তনগুলো বাস্তব DOM-এ প্রয়োগ করা হয়, যা অ্যাপ্লিকেশনের পারফরম্যান্স বৃদ্ধি করে।

<b>উদাহরণ:</b> যখন স্টেট পরিবর্তিত হয়, React নতুন Virtual DOM তৈরি করে এবং পুরানো Virtual DOM-এর সাথে তুলনা করে। পরিবর্তিত অংশগুলো শুধুমাত্র রেন্ডার করা হয়।

## ২৫. React.memo এবং PureComponent এর মধ্যে পার্থক্য কী?

উত্তর:

React.memo: এটি একটি হাইয়ার-অর্ডার কম্পোনেন্ট যা ফাংশন কম্পোনেন্টগুলিকে রেন্ডার অপ্টিমাইজ করতে ব্যবহৃত হয়। এটি প্রপ্সের উপর ভিত্তি করে কম্পোনেন্ট রেন্ডার হওয়া নির্ধারণ করে।
PureComponent: এটি ক্লাস কম্পোনেন্টগুলির জন্য একটি বেস ক্লাস যা shouldComponentUpdate মেথডকে অটো ইমপ্লিমেন্ট করে, প্রপ্স এবং স্টেটের শ্যালো তুলনা করে রেন্ডার হওয়া নির্ধারণ করে।
উদাহরণ:

React.memo:

```
import React from 'react';

const MyComponent = React.memo(function({ name }) {
  return <div>{name}</div>;
});

export default MyComponent;
```

PureComponent:

```
import React, { PureComponent } from 'react';

class MyComponent extends PureComponent {
  render() {
    return <div>{this.props.name}</div>;
  }
}

export default MyComponent;
```
