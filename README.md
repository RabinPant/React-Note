Note: 



 
 
 
 
This is without BABEL and webpack.
 
With babel
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 

As we know we can’t modify props but if we want to do that then there is one way to do it and it’s through the help of state:
 
 
 
 
 
TO BIND THE THIS KEYWORD
1)	USE ARROW FUCNTION
2)	Use constructor to bind this . example 2 below
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 












 

 
 
 
 

 



 
API CALL and the use of componentDidMount in it:
 

To search the element from the input box:
 
This way we can only filtered one way data i.e if we delete the text in the input box then at that time we’re not able to see the whole list.
To have this ability we can maintain the separate state and send the input data in that state and filtered according to that state and map in that filtered list.
 

 


 
When we try to write the if condition inside the JSX then that will create problem because at last this jsx will be converted to react element and that won’t be valid code.

 
 
User Component 
Guest Component 

 

 

 

IMR = import react
IMRD = import react DOM
RCC = import class component
 
As we know we can’t use if else statement inside the JSX because babel will convert that into react.creatElement and this will create the invalid JS. 
To overcome this we can make use of IIFE.
IIFE is the concept where we can make use of if ..else any other code but we’re not writing the code inside the JSX. We’re writing the code inside the arrow function of the JSX.
 
IIFE method calls itself.
 

 

 
 
 

Through Props:
 
 

 

Getting all values from the state with the help of the MAP function:
 

 

 

If you want to apply two style at a same element then just use spread operator:
 

 


 
The need for the CSS module: when we can’t create the pseudo class in inline CSS we made use of the external CSS and in the external CSS we’ve a problem of name conflict. When we use same name in two or more place then our styling go bad. So to overcome this there is CSS module.
 
 

 
 

 

 

 

 
 
The img pic.jpg is in the public folder and this the way to import the image
 

 

 

 
  
 
 
Here the problem is for each and every input field and attribute we’re writing the handle function, what if we have 100 of input field then at that time we’ve to write 100’s of these function which is not a good practice. So how can we overcome this:

We’ve to make change in three place:
First add name attribute in both the input filed:
Name=”name” name=”password”
Then after you can create only one function and set the state according to the name:
 

 

 

 

 
 
  
 
 

 





 

 
 

Context API:
 
  
 
 
   

 

 
 

If multiple data then :
 

  

 

If you want to create a separate file for the context and manage everything from there then:
 

 
 
 
 

 

 

 

 

 

React Router:
 
 
 

RAFCE =  to create functional component


 
 

The above code has to be modified from react 6 and only the following code will get executed:
 
 
Whenever we use the anchor tag and try to navigate then at that time what happens is the whole page gets reloaded again and again. So this is not what we are trying to achieve.

To overcome this make use of LINK:
 
In Link we can’t make use of styling, so to overcome this we can make use of <NavLink>
 

 

What if user enter the URL which is wrong and doesn’t exist then at that time we have to show him a 404 page not found. How we can do that?
We can simply create a page error.js and navigate to that page if none of the Route will work.
 
Here we have added two things one is SWITCH and other is the route for the error page.

For the dynamic second url we can use the path as :
 
Here the :category is the dynamic and we can make use of anything 
 
 
 
 

REACT ROUTER V6:
 
 

If user enter the path that is not define then: Route path with (*) gets fired and run. 

 

For the Dynamic rendering:
 
 

How to get the value that was entered in the :category and get that value to display in the page:
 
 
 
Whatever value we provide in the URL it helps to get that value and display in the page.
How to get value form query param:
To get value we need to make use of useSearchParams
 
 
 

Conditional routing:
 

Data Passing as the attribute using useLocation:
 

 


UseNavigate hook:

GoodBye ReactDom.render()
Before react 18 we were using ReactDom.render() but after the release of react 18 we’re no longer using this feature at all.
React 17 index.js
Import ReactDom from ‘react-dom’;
ReactDom.render(
	<React.StrictMode><App/></React.StrictMode>
	Document.getElementById(‘root’)
);

React 18 index.js
Import ReactDom from ‘react-dom/client’;
Const root = ReactDom.createRoot(document.getElementById(‘root’))
Root.render(…..same as above)

Use NPM to install the latest version of React and react-dom API.
Npm install react react-dom
Yarn add react react-dom
Yarn upgrade react react-dom

Props destructing:
Const {name,age} = props
Props are the values you pass as attributes with the component.
Props are immutable and you cannot change the props. To change the value we will need the state.


Concept of state and useState() hook:
React hook was introduce from 16.8 version.
State is like a variable which is being watched by React Application.
If there are any changes made to the state React will make sure that they are re-rendered. The changes are updating the DOM as well.

useState() : 1)  state value => value which we have given of the state.
2)Setter Function
3)	Const [i,setCount] = useState(0);
 
Lazy initialization:
Whenever you have bigger process which is going to give you the initial state value and that you put in a function. Then instead of writing the function only do make sure that you follow the lazy initialization.
Function initialState(){
	Console.log(“Expensive process:”+ Date.now());
}
Expensive way: const[cnt, setCount] = useState(initialState)
Const [cnt, setCount] = useState(()=>initialState()); 
//lazy initialization because we’re making a function and calling. This way it is called only once and rerendring doesn’t happen again and again.
Basic Event handling & parameter passing:
If you need to pass parameters in the function then always use the arrow function that is the easiest way to approach.
<button onClick={test}> //no parameter
<button onClick={()=>test(5)}>//whenever passing parameter use arrow function otherwise it will not work

Applying external and Inline styling:
2 basic way:
External and internal styling
Const style= {
	Width:100px,
	Height:100px,
	Color:blue
};

<button style={style} >Click Me!</button>
JSX in depth:
HTML written inside the javascript. Any code which appears like HTML and is written inside the javascript is the JSX code.
JSX is powered with all the javascript features.
Let msg = <h1 style={{color:’red’}}> Hi! {new Date().toDateString()}</h1>
In HTML : <h1 class=””>
In JSX : <h1 className=””>

JSX is an easier way or the syntactic sugar
The actual function running behind is React.createElement()
This is actually the older way of doing things.
Lets take an example of the above :
Let msg = React.createElement(
	‘h1’,
	{style:{color:’blue’}},
	‘hello’).
Advantage of JSX:
JSX prevents injection attacks as the values are embedded in jsx before rendering so you can never inject anything that’s not explicitly written in your application.
JSON.stringify(sobj) => This helps to display the JSON value.
The new JSX transform helps to run the application without importing react.
Import React from ‘react’  =>not needed now for jsx may needed for hooks like useState and other thing but not needed for JSX.
This is coming from v17

Primitive type and object literal with useState().
To display the Boolean value in screen at that time you need to convert to string by using .toString().


What is Stateful and stateless component?
In versions before React 16.8, Class was the only component which could use “State” in it. After react 16.8 function can also have the state so these saying of stateful and stateless component got lost.

What is the render() method in the class component?
Render() is a very essential component life cycle method. Whenever the state is updated or a new state is define then at that time this render() method is called and render() method contains the JSX which is the user interface.

How do you change the state of class in react?
We use the setState() method for the update of the state in react.
setState(updater,[,callback])
setState(changeObject[,callback])


Component lifecycle Methods:
The whole lify cycle can be divided into 4 category:
1)Mounting
	Constructor()
	Render()
	componentDidMount()
2)Updating
	Render()
	componentDidUpdate()
3)Unmounting
	componentWillUnmount()
4)Error handling:
	componentDidCatch()

Concept of useEffect Hook()
useEffect() hook is called everytime when the component is rendered or re-rendered(). If you know the lifecycle methods, you can think of useEffect() hook as componentDidMount(), componentDidUpdate() and componentWillUnmount() combined.
How can you prevent useEffect() to be called for all states() or how do u skip the useEffect() for specific states?
useEffect(()=>{ 
console.log(“Effect called..”+gCnt++)
},[cnt])
So after comma whatever component we provide in the array, useEffect will be executed for only those component. Here, we have given cnt component.

Conditional Rendering()-Cleaning of an effect:
	useEffect(()=>{
		//Code
	Return()=>{
			//clean-up code
		}
	})
In case of class component componentWillUnmount() is used to get this objective. 
So after the initial code is displayed in the screen then this part of the code is executed to remove the code.
List and Keys:
1)	Map() method:
	Find length of each element in an array?
	Let arr = [“apple”,”banana”,”oranges”];
	Let length = arr.map((element)=>element.length);
Console.log(length);
	With map always use the key attribute.
	
Fixed stable keys: Do not take the index of an array as an key because its not stable and may cause the problem. We should always try to have the stable  unique string as a key.

Example: Product: {id:1,pNmae:’apple’,price:’10’} 
<li key={product.id.toString()}>{product.pName}</li>
 

Event handling:
Const getData = (e)=>{
	Console.log(e.target.value);
}
Return (
	<div className=”app”>
		<h1>Test</h1>
		<input onChange={getData} type=”text” />
	</div>


Update the state with the use of the hooks.

Import React, {useState} from ‘react’;
Function App(){
	Const[h, setH] = useState(‘Default’);
	Cosnt getData = (e)=>{
			setH(e.target.value);
		}
Return (
		<div className=”App”>
			<h1>{h}</h1>
			<input onChange={getData} type=”text”/>
		</div>
	)
}


Preventing the Default Behavior:
	The default behavior of form submit is that whenever we submit a new form then at that time whole page get refreshed and whatever data we have entered is lost also the console.log() printed data will be refreshed.
How can we prevent this behavior?
In javascript how we do this:
<form onsubmit=”console.log(‘you clicked submit’); return false”>
	<button type=”submit”>Submit</button>
</form>
But this doesn’t work in react:
But we can make use of preventDefault();
Const getData = (e)=>{e.preventDefault();}

Form with multiple States:
	  

Task is to display the form data in the down with the help of useState for each input box.
 
 

FORM – State as Object:
In the earlier part we have different state for each field of the form, in this part we’ll combine all the state into one state.
Const[persInfo,setPersInfo] = useState({
	firstName: ‘’,
	lastName:’’,
	mobile:’’
})
const firstNameChangeHandler = ()=>{
	setPersInfo({…persInfo, firstName:e.target.value);
} //this part is very important because here whenever we update a object literal we have to first save the earlier and show the new one. The spread … is doing exactly the same thing.
Const showData = (e)=>{
	e.preventDefault();
}

Can you directly render an object?
No, you can’t render an object directly for that you’ll have to make use of JSON.stringify(persInfo)

Single Event Handler using dynamic key:
1)	How to make the keyName Dynamic:
	ES6 syntax: 
	let test = “ename”;
	const obj = {
		[test]:’Name’
	}
 Const inputChangeHandler = (e)=>{
	setPersInfo({…persinfo,[e.target.name]:e.target.value})
}

<input type=”text” name=”firstName” onChange={inputChangeHandler}>


THE CORRECT WAY TO DO EVERYTHING :
import React,{useState} from 'react';
import "./styles.css";
export default function App() {
 const [persInfo,setPersInfo]=useState({
   firstName:'',
   lastName:'',
   mobile:''
 })

const inputChangeHandler=(e)=>{
 setPersInfo((prevState)=>{
    return { ...prevState,[e.target.name]:e.target.value}
 });
}
const showData=(e)=>{
   e.preventDefault();
}
return (
  <div className="App">
    <div>
      <form onSubmit={showData}>
      <input  type="text"
      placeholder="First Name"
      name="firstName"
      onChange={inputChangeHandler}
      />
      <br/>
      <input type="text"
      placeholder="Last Name"
      name="lastName"
      onChange={inputChangeHandler}
      />
      <br/>
      <input type="text"
       placeholder="Mobile"
       name="mobile"
       onChange={inputChangeHandler}
       />
      <br/>
      <input type="submit" value="Submit"/>
      </form>
      {JSON.stringify(persInfo)}
    </div>
  </div>
);
}
Why is updating state with “Functional update” syntax better?


For the check Box and Radio button:

Const inputcheckHandler = (e)=>{
	setPersInfo((preState)=>{
		return {…prevState,      [e.target.name]:e.target.checked}
	})
}

Concept of Single Page Application:

Only certain component gets loaded when we click on the certain hyperlink in the page.

To make a single page application we have to implement client-side routing
There are 2 libraries often used:

1.	React Router
2.	Reach Router


React Router 6:
Npm install react-router-dom

<BrowserRouter> is the main component and all the routes and components will be wrapped inside it. 
 

The three most needed component after this is Routes,Route and Link.

Import {Routes,Route,Link} from react-router-dom;

Inside the Routes the Route is placed and the hyperlink which we earlier used to do with anchor tag is now replace with Link.

Why Link is use instead of anchor tag?
Because when we use anchor tag the whole page gets refreshed and that’s not what we are trying to achieve. To achieve the feature of SPA we have to make use of Link.
  
  
Is URL and Routes same?
No, URL and Routes aren’t the same because URL is the path which we see in the browser and route is the code that check the URL in the LINK attribute and then map that with Route and display the component.


Dynamic Routes – UseParams():

Whenever we pass anything in URL which is dynamic. How can we route to that URL by making use of one route instead of making four route.

For example.
 
Here inside product route we have four fruits and they all route to same page but with different ID.   
So here same page is getting rendered again and again but with dynamic value passed in URL.

To make the dynamic Route:
 
 
To ge the dynamic value we are making the use of useParams().

Nested Routes:

<Outlet/> =  whenever you want to showcase the child component then you just put this tag.

ProductDetail page is child of Product so, we can put this inside the parent component.
 
/product can be remove from the child product detail.
Now to showcase the child component we just use <Outlet/> tag.
 


Page Not Found:
What if the URL is invalid then you need to showcase the PAGE NOT FOUND:

How do you configure NOT FOUND PAGE:
 


Index Attribute – Referring The Parent Route:

If you make a child component and you want to refer to the parent component then at that time you can make use of INDEX. For example,

 
Here main parent is / and then instead of putting path=”/” at second line we are saying index that mean that route path will refer to the parent component and render the Home component.


















Dynamic Products Data useState() & route Configuration

 

Context & useOutletContext() Passing Data to Child Component.

When it comes to Sharing the data to child component, there is an attribute called “CONTEXT” which you can use with the <Outlet/> component.

<Outlet context={object} />

The object is passed to the child component and to refer the passed data inside child component you have the useOutletContext() hook.

 

 

State & useLocation() hook The correct way of Data Sharing.




Context-API

1)	Prop drilling:
	What is Prop Drilling?
Login
DashBoard			UserDetails
Component 1
Component2 

Login is one component and when user login the user will enter some data like username, password and isValid. After that other components like DashBoard, userDetails those are coming. But what if we want to send the login data to the other different component. That time we have to make use of props. From login to the component2 the data will flow with the help of props.

There are 3 main steps to setup Context API:
1)	Create Context
2)	Provider
3)	Consumer
To create a contxt we will use : React.createContext() method.
Const TotalContext = React.createContext(0);
Const ProdContext = React.createContext({pName:’Apple’,price:45}…);

The value you pass within createContext is the initial or default value & you can later on add & manipulate.
2)	Provider
Once the context is created, we have to provide it.

Const TotalContext = React.createContext(0);

<MyContext.Provider value={value}>
	<App/>
</MyContext.Provider>

<TotalContext.Provider value={total}>
	<Total/>
</TotalContext.Provider>

Here, <Provider> is a react component available with the context object & we need to wrap around all the components who want to refer to the context.

3)	Consume the Global context now:
	<TotalContext.Consumer>
		{(total)=>{
			Return(
					<div className=”c”>
					)		
			}
		}
	</TotalContext.Consumer>

Explain the concept of Context API and how do you implement it in your project?

Whenever there is a need to have some data pieces available to various/multiple components, (maybe) for the entire application, then you use the Context API.

You can implement in three steps:
1)	Create Context:
Const MyContext = React.createContext(defaultValue);
		2)Provider
			<TotalContext.Provider value={total}>
				<Total/>
			</TotalContext.Provider>
	3)Consumer
		Const Component = ()=>{
					Return(
							<MyContext.Consumer>

							</MyContext.Consumer>
						)		
				}

useContext()- New & Better Consumer!

Syntax : Const value = useContext(MyContext);
The whole line of the consumer above can be replace by this single useContext(). The useContext() takes the context as parameter and it returns the context value.

Redux:
Npm install –save redux react-redux

To create a global store use createStore() method of redux.
Const store = createStore(reducer);
It returns the store object i.e the global state
Remember !!!!! A reducer function becomes an actual reducer when you pass it as an argument inside createStore() method.

Const store = createStore(reducer);
This means we’ll have to create the reducer function first, and then we will pass it to the createStore() method as an argument.

How to create a global store? Or Explain the usage of redux-createStore() method
To create a global store we use this const store= createStore(reducer); wehre reducer is an argument. That is a function.

 


Providing store with <Provider>
The next step is to provide the store to the entire application
<provider store={store}> <App/></provider>
The <Provider> component makes the Redux store available to any nested components that need to access the redux store.
  

useSelector() hook accessing store data:

If you’re using the class component, then you have to use the connect() method.

Syntax:
Const products = useSelector((state)=>state.products);
For cart data:
Cosnt cart = useSelector((state)=>state.cart);
For total data
Const total = useSelector((state)=>state.total);

Explain the difference between useStore() & useSelector() hooks?
useStore() hook returns a refrence to the same Redux store that was passed into the <Provider> component
useStore() hook should probably not be used frequently, prefer useSelector() as your primary choice.


useDispatch() Event Handling.
 
 

Explain the Flow of event handling with redux?
How do you use the dispatch hook?
How can you dispatch event from component to reducer?
Const dispatch = useDispatch();
Dispatch ({type:’ACT’,payload:obj})

HTTP Request:

Fetch() => This is the core javascript method that is use to make an API call.
XMLHTTP request-before ES6
Fetch API – ES6 onwards

Const responsePromise = fetch(url,[optional object]);
If the “optional object” is not mentioned it becomes a GET request.

Cosnt response = fetch(‘http://URL’,{
	Method:’POST’,
Headers:{
   ‘Content-Type’: ’application/json;charset=utf-8’
},
Body: JSON.stringify(data)
})

Async function fetchData(){
	Let data;
Const response = await fetch(‘https://jsonplaceholder.tyicode.com/users’)
If(response.ok){
	Data = await response.json();
	Console.log(data);
}
}

fetchData();
in place of json you can get text and image. By using response.text() and response.blob()


Shortcut of above function is:
Fetch(‘https://jsonplaceholder.typicode.com/users’)
.then(response=>response.json())
.then(data=>console.log(data));

 
 


Error Handling.
 







Typescript:
The main purpose of TypeScript is for static type checking. i.e It allows you to implement strict type checking and also helps you to write code with more validations so at the development time itself you get to know possible compile time errors.

Npm install –g typescript. 
Tsc –v

Variable & Datatypes:

Let a:number=9;
Console.log(a)

Let<variablename>:<datatype>;
Let<variablename>:<datatype>=value;

Const <variablename>:<datatype>=value;

Type Annotation & Inference:
When there is no explicit type annotation, TypeScript complier infers(assumes) the type according to assigned value.
Function sum(a=3,b=3):number{
}
Let a = sum(5,6);
1)	Typescript infers the datatype when you have value assigned to it.
2)	When you apply the default value for function parameters TypeScript automatically infers the datatype.
3)	When a function is returning a specific type of value, TypeScript automatically infers the same datatype.


Creating React & TypeScript Project

Npx create-react-app ts-app –template typescript

  
React.FC – TypeScript FunctionalComponent

Const Product:React.FC<{pCode:number,pName:string}> = ()=>{
	Return(
			<div>{props.pCode}-{props.pName}</div>
			)
}

How do you configure props with TypeScript in React?
What is React.FC?
While using the functional expression to create a component, you use React.FC where FC stands for Function Component & it is an interface.

Interface & Optional Attributes:
In above code we’re passing all the parameters in the <> angle bracket and this is not the good way of doing.
What we do is first create an interface and then define variable there and pass that to the React.FC<>

Interface Props{
	pCode:number;
	pName:string;
	qty:number;
}

Const Product:React.FC<Props>=(props)=>{

	Return(
			<div>
				{props.pCode}-{props.Pname}-{props.qty}
			</div>
		)
}

To make some of the props as optional we’ve to make it optional and how we can make that?

Interface Props{
	pCode:number;
	pName?:string;
	qty?:number;
}



useState in TypeScript:
Create a state named counter which can have number, null or Boolean values.
Function App(){
	Const[counter,setCounter]=useState<number|null|boolean>(1);

Return(
)
}

onClick – Event Handling with TypeScript:
function App(){
	const[counter,setCounter]=useState<number>(1);
	const btnHandler = (e:React.mouseEvent<HTMLButtonElement>):void=>{
	setCounter(counter+1);
}
	return(
			<div>
				<button onClick={btnHandler}>onClick</button>
		)
}


onChange EventHandling with Typescript:
<input type=”text” onChange={inputChangeHandler} />
Const[txt,setTxt]=useState<string>(‘ ’);
Const inputChangeHandler = (e.React.ChangeEvent<HTMLInputElement>):void=>{
	setTxt(e.target)
}

Testing:
Types of Testing:
1: unit testing
2:Integration Tests
3:End to End(e2e) Tests

Jest Library with React for unit testing:
Other tools or library are Jasmine and Mocha
Npm install --save-dev jest
Jest and Enzyme are used together for the testing of react application. Jest can test both node and react app whereas Enzyme is used only for react app.

Explain the difference between Jest and Enzyme:
Jest is a powerful library with all the tools available in it i.e assertion, mocking, test runner etc.

Enzyme gives more functionality while dealing with components or basically the UI. It gives additional testing utilities which can interact with elements & built for react only.

Npm test.

SYNTAX:
Test(“Initial value of counter should be 0”,()=>{
Render(<Counter/>);
Const counterEL = Screen.getByText(0);
Expect(counterEL).toBeInTheDocument();
})

Assertion is the possibility that can happen in the code.
You can derive assertions using the expect() method.

getByTestId() and data-testid

<h3 data-testid=”cnt”>{counter}</h3>
Const counterEl = screen.getByTestId(“cnt”);


Button Click Test – fireEvent
Test for a button click to check, that before clicking on a button it is 0 and after click it should be 1

Option for generating click event from the test:
1)	userEvent – Companion library of testing library
2)	fireEvent – Part of react testing library.

When you write fireEvent.click() it will directly run the click procedure, that means you’re missing the events getting fired along the way.
“Code written on other related events will not execute”.
If you use the userEvent library it will executes all these events in order.
Like : mouseOver(), mouseMove(), mouseDown(), focus()


FireEvent means directly the event, means it will neglect the other related events along the way.

userEvent is almost like what actually, happes in the browser, all those events will be executed.


Matchers – toBe() or not.toBe()
expect().toBeNull()
expect().not.toBeNull()
expect().toBeGreaterThanOrEqual()
expect().toBeLessThanOrEqual()
expect().toBeGreaterThan()
expect().toBeLessThan()

Test with the input element:
Dynamic value in the input box way:
 
 


Asynchronous Testing:
 

 

Mock Test – Mocking Fetch() API:

 

BeforeEach and afterEach:

 
Memory/container cleaning process – we put inside the afterEach() method and component rendering and other initial stage coding – we put inside the beforeEach() method.


Snapshot testing:
It is basically the output’s snapshot has been taken and that is getting compared for subsequent changes.

Press U to overwrite the snapshot



Npm create vite@latest
Npm i
Npm run dev
Summary of today's class:
1.	Intro about the namaste react course
2.	Environment needed : Editor - vs code, Browser - google chrome
3.	Extensions for VS code : better comments bracket pair colorization toggler es7+ react/redux gitlens prettier prettifyjson vs-code icons
4.	Created html boiler template in vs code using emmet and wrote html for printing some text.
5.	Wrote a simple js program to print Namaste Everyone in h1 tag inside div container with id root. -> used js engine's browser API called document to create h1 element and appendChild to append it to root div const heading = document.createElement("h1"); heading.innerHTML = "Namaste Everyone"; const root = document.getElementById("root); root.appendChild(heading);
6.	Wrote the same program using React
-> Add script for react cdn link in body of index.hmtl -> create app.js and move our js script there -> Now, write the same script in react
A react element is object with properties which is created by React library const heading = React.createElement("h1", {}, "Namaste Everyone");
const root = ReactDOM.createRoot(document.getElementById("root")); root.render(heading);
render() function will override the content of the root if there is any content already present in root container
so until the root is rendered, if we want to display some error message, it can be written in html.
what if we need to put more elements inside the root container - pass array of react elements to the container creation
const heading1 = React.createElement("h1", {id : "title"}, "Namaste Everyone"); const heading2 = React.createElement("h2", {id : "sub_title"}, "Welcome");
const container = React.createElement("div", {}, [heading1, heading2]); const root = ReactDOM.createRoot(document.getElementById("root")); root.render(container);
7.	Created a style.css file and linked to index.html
8.	Learn about arrow function for tomorrow's class
9.	Igniting React App
10.	. In last class - Created Basic React App
11.	
12.	. Today, production ready React App - From scratch without using create react-app
13.	
14.	. to Ignite our app - Bundler eg : vite,parcel,webpack
15.	
16.	. In create react-app, they use webpack bundler
17.	
18.	. Bundler is package/module of javascript code
19.	
20.	. to have a package in code -> we need Package Manager (eg : npm, yarn)
21.	
22.	npm init -> create package.json -> initialise our repo with npm 
23.	npm init -y -> to skip configuration
24.	. why npm ? helper packages -> React app is powered by a lot of packages for bundling, optimizing, minifying maven : java :: rnpm : react
25.	
26.	Parcel :
27.	
28.	npm install package-name -> to install a package named package-name  & node modules (helper functions )is created 
29.	
30.	npm install -d package-name -> -D means dev dependency or --save-dev
31.	
32.	package-lock.json is created and parcel code is updated in node modules
33.	
34.	parcel is in dev dependencies of package-lock - parcel is needed in dev environment
35.	
36.	if update happens, package.json is updated but package-lock.json is not updated
37.	
38.	package-lock.json - dont ignore in git but put node modules in .gitignore
39.	
40.	if we have package-lock.json -> we can regenerate node modules
41.	
42.	react cdn - is not a good way Good way -> in server thrugh node modules
43.	
44.	npm install react -> in global dependencies not dev dependencies
45.	
46.	npx parcel index.html -> Execute using npm with index.html as entry point -> Creates local server
47.	
48.	Parcel gives us this server
49.	
50.	Error : React is defined because we removed cdn link. Instead of that, we have to use import since this time we are using node modules - npm
51.	
52.	Error : Browser doesnot understand import -> we have to inform its modules, use type="module" in script tag
53.	
54.	Warning : React DOM -> createRoot is not found -> use react-dom/client
55.	
56.	Live Server -> Auto refresh -> Hot Module Replacement (HMR) -> Parcel does it for us using File Watcher Algorithm (written in c++) Parcel.cache -> uses this space for doing all the HMR, minify and other stuffs dist folder -> minified code in dist npx parcel build index.html -> production ready build is created by parcel inside dist folder and has only 3 files : css, html and js file containing all the code including react code
57.	
58.	Parcel Functionalities :
59.	
60.	minification (removing indentation),
61.	image optimizations,
62.	compression(renaming variables),
63.	cleaning our code,
64.	super fast build,
65.	dev and prod builds,
66.	caching while development
67.	works with older version of browsers
68.	Https on dev as well npx parcel index.html --https 10.Consistent Hashing Algorithm 11.zero config
69.	Tree shaking - Removing unwanted code
70.	we should put .parcel-cache in gitignore -> anything which can be autogenerated in server can be put in gitignore
71.	
72.	Initial dev build -> longer time (500ms) -> for next build -> takes less time 5ms using caching
73.	
74.	When using parcel, we give entry point in command so we can remove main: app.js from package.json
75.	
76.	Transitive dependencies -> dependencies of dependencies Eg: Our App is dependent on Parcel which is again dependent on other dependencies (dependency Tree)
77.	
78.	browsersList -> cross browser compatibility for older versions of browsers
79.	
80.	Summary Steps :
81.	
82.	npm init
83.	npm install -D parcel
84.	npm install react
85.	npm install react-dom
86.	npx parcel index.html or npx parcel build index.html
87.	import React from 'react'; in App.js
88.	import ReactDOM from 'react-dom/client'; in App.js
89.	use type="module" for index.html
90.	Remove main : app.js from package.json
91.	Write browserslist in package.json
92.	"browsersList" : [ "last 2 versions"]
93.	
94.	Homework :
95.	
96.	Read Parcel Documentation
97.	Types of script in script tage in html
98.	Issues:
99.	One issue I faced while setting up parcel is, though the server was succesfully started,I was getting 404 Page not found when run the application in browser. We were not able to find the root cause for long time. Finally, my npm was outdated and it did not throw any error during build. After updating the npm, it worked.
100.	




Theory Assignment: Chapter - 01 Inception (24/12/2022)
1. What is Emmet ?
Emmet is a plug-in for many popular text editors which greatly improves HTML & CSS. Emmet short hand expression can be used to generate HTML markup and css. Most useful emmet abbreviations are :
HTML
1.	html:5 - generates html5 boilerplate
2.	ui>li - nested elements
3.	h1.#heading.container.con - create h1 element with id heading and classes container and con
4.	div[data-name=harshi] - Custom attribute
5.	header+div+footer - generate siblings
CSS
1.	m10-10-10-10 - Margin on all sides margin: 10px 10px 10px 10px;
2. Difference between library and framework ?
Library - collection of pre-defined helper functions, objects, classes, modules that can be used in code to boost the development. By using a library, you can control the flow of the application and call the library. Eg: React, JQuery, Lodash
Framework - Foundation upon which applications are built. In contrast, when you use a framework, the control is inverted, i.e., the framework controls the flow and calls your code. Eg: Node JS, Angular, Spring
3. What is CDN ? Why do we use it ?
A CDN also called a content distribution network, is a group of geographically distributed and interconnected servers. They provide cached internet content from a network location closest to a user to speed up its delivery.
4. Why is React known as React ?
React was developed for applications (Facebook) that have constantly changing data. Since React is a front-end framework or the View in MVC, this means that as the user clicks around and changes the app's data, the view should react or change with those user events.
5. What is cross-origin in script tag ?
The crossorigin attribute provides support for CORS , defining how the element handles cross-origin requests. CORS stands for Cross-Origin Resource Sharing. If cross-origin is set to "user-credential", then user authentication is required to access the file.
6. What is difference between React and ReactDOM?
React library contains functionality utilised in web and mobile apps (react native). ReactDOM library contains functionality utilised in web browser. It contains DOM manipulation utilities.
7.What is the difference between react.production.js and react.development.js ?
react.production.js - production code of react library that is minified and production ready. react.development.js - More readable and developer friendly react library code that can be used to debug.
8.What is async and defer - check Akshay Saini's Youtube channel ?
Without async/defer : Browser stops the html parsing once script tag is encountered. It resumes parsing only after script is fetched and executed.
Async : Html parsing is done in parallel while scripts are being fetched from the network and executed. Once the script is done with execution, html parsing is resumed. This can be used for external scripts like google analytics. It is better to avoid async for scripts that are dependent on other scripts since we dont know in which order script will be executed.
Defer : Similar to async, Html parsing is done in parallel while scripts are being fetched from the network. But scripts are executed only after the html parsing is done.


Theory Assignment: Chapter - 03 Laying the foundation (01/01/2023)
1. What is JSX?
JSX is neither a string nor a html tag but a syntactic sugar for the React object. It is a html-like syntax inside js code for creating react elements. By using JSX, instead of writting markup (html) and logic(js) separately, the separation of concerns (SoC) is emphasized based on loosely coupled units called 'Components' which contains both.
Broswer does not understand JSX and a transpiler/compiler is required to convert this to browser understandable js code. Eg: Babel
JSX ------> React.createElement() -----> React element ----> Object to be rendered in the DOM
2. Superpowers of JSX
•	JSX as variables : markup (html-like) syntax can be set in a variable. This creates a react element (object).
•	javascript expressions in JSX : JSX supports all js expressions by wrapping them in {}
•	Attributes in JSX : We can pass all the html attributes inside jsx tag (attributes must be CamelCased). Even, custom attributes can be created, but it must not use CamelCase.
•	Props in JSX : The values of each attribute can be passed as properties (props) to a react element. This is my favourite superpower of jsx, since it can handle dynamic data to create react elements.
3. Role of type attribute in script tag ? What options can I use there ?
type attribute of the <script> tag indicates the type of script. Until HTML 4, type is a required attribute. The value of type can be any of the following :
<script type="" src="app.js"></script>
In HTML5, type attribute is not mandatory. If type attribute is not present(default), or an empty string (type="") or javascript MIME type (text/javascript or application/ecmascript), it is treated as classic "javascript" file.
<script type="module" src="app.js"></script>
If the type attribute is set module, then the code in that js file is treated as module.
<script type="importmap" src="app.js"></script>
If the type attribute is set importmap, the body of the element contains importmap ie an JSON object using which the browser can resolve the module specifiers while importing modules.
<script type="{$anyothervalue}" src="app.js"></script>
If the type attribute contains anyother value, then the code is treated as data block and will not be processed by the browser. A valid MIME type other than Javascript MIME type (Eg: image/png or text/css) must be mentioned. All the other attributes for this type will be ignored even the src attribute.
4. { TitleComponent } vs { <TitleComponent /> } vs { <TitleComponent> </TitleComponent> } in JSX
{ TitleComponent } - This value in jsx is considered as jsx expression or variable. If no such variable is present, no output will be shown in the browser. Console throws the following warning
index.js:1 Warning: Functions are not valid as a React child. This may happen if you return a Component instead of <Component /> from render. Or maybe you meant to call this function rather than return it.

{ <TitleComponent /> } - This value in jsx is meant for rendering a component (i.e) function that return jsx. This is self closing tag.
{ <TitleComponent> </TitleComponent> } - This is same as { <TitleComponent /> } if there are no child inside TitleComponent. If there are children, then those values come inside { <TitleComponent>}  and </TitleComponent> }.


JSX  =  HTML like element but it’s not html with javascript.
Jsx is different and html/javascript is differenet.

Basically what happens is parcel which is the bundler and contains all the package that is required to bundle and build the react app consist of one more beast called babble and this babble helps us to transpile the jsx into react element and then to javascript element then after that javascript element is read by the JS engine.



Component position : component inside the component.









React Router to navigate different pages:

When we are using router first we need to download react router and put into our package.json.

The way we can do it is npm install react-router-dom.

Now we can go to our app.js and import the createBrowserRouter from react-router-dom;

Then we can start creating our path and render the component.
 
At last while rendering earlier we were putting Applayout but now since we have lots of routing we are putting following code in the render.


Custom error page with error logged in :
 

Children Routes:
Why this is use?
For example if you want to have a header intact and want to change the body of the page according to the route then you’ll need the children route.
In above code you see there is Header and Body component but in place of body component you want to have different pages and same header so how will you do it.
In this case I am going to make use of Outlet from the react-router-dom and then this will help us to load the children route in place of Outlet.

See the code:
 
 
Above we have children route setup for the Applayout. Now in Applayout there is two components rendering one is the header which we need all the time but the other one is the Outlet which is coming from the react-router-dom and this will help me to route to the children route according to the path. If we have / path then body will be rendered and showcase if something else then our children route setup will kick in and load the page
Create Custom Hooks (Utility function)
Single Responsibility Principle
Bundling
•	Chunking
•	Code Spliting
•	Dynamic Import
•	Lazy Loading
lazy and Suepense
import { lazy, Suspense } from "react";

const MarkdownPreview = lazy(() => import("./MarkdownPreview.js"));

<Suspense
  falback={<h1>Loading... - "It will render untill the component rendered"</h1>}
>
  <MarkdownPreview />
</Suspense>;
Suppose we need to show MarkdownPreview on markdown-page (http://localhost:1234/markdown) using react router, then we can use as below.
const router = createBrowserRouter([
  {
    path: "/",
    element: <App />,
    errorElement: <Error />,
  },
  {
    path: "/markdown-page",
    element: (
      <Suspense
        falback={
          <h1>Loading... - "It will render untill the component rendered"</h1>
        }
      >
        <MarkdownPreview />
      </Suspense>
    ),
    errorElement: <Error />,
  },
]);
1. When and why do we need lazy()?
React.lazy is used to dynamically import a component when it is first rendered, instead of importing at the beginning when the file loads. This is called Code Splitting/ On-demading loading.
In our example : In App.js, Instamart component and about component are lazy loaded, which means only when the user clicks on the navigation button, those components are imported and rendered. This improves the performance of the application. So, lazy is used when that component might not be used by all users, instead of loaded in the beginning, only when the user really needs it, its loaded.
2. What is suspense?
Suspense component allows us to show some fallback content (such as a loading indicator/ Shimmer component) while we’re waiting for the lazy component to load or the component is not yet rendered. It is similar to catch block. If a component suspends, the closest Suspense component above the suspending component catches it
import React, { Suspense } from 'react';

const About = React.lazy(() => import('./About'));

function MyComponent() {
return (
  <div>
    <Suspense fallback={<div>Loading...</div>}>
      <About />
    </Suspense>
  </div>
);
}
The fallback prop accepts any React elements that you want to render while waiting for the component to load. You can place the Suspense component anywhere above the lazy component. You can even wrap multiple lazy components with a single Suspense component.
3. Why we got this error : A component suspended while responding to synchronous input. This will cause the UI to be replaced with a loading indicator. To fix, updates that suspend should be wrapped with startTransition? How does suspense fix this error?
This error is thrown as Exception by React when the promise to dynamically import the lazy component is not yet resolved and the Component is expected to render in the meantime. If only the dynamic import is done and there is no <Suspense /> component then this error is shown. React expects a Suspense boundary to be in place for showing a fallback prop until the promise is getting resolved. If showing the shimmer (loading indicator) is not desirable in some situations, then startTransistion API can used to show the old UI while new UI is being prepared. React do this without having to delete or remove the Suspense component or its props from your code.
4. Advantages and disadvantages of using this code splitting pattern?
Advantages	Disadvantages
Reduces the page load time by bundling the large code into smaller bundles and laoding dynamically only when the component is loaded	Though the initial page load time is reduced, this increases the load time of each component thats loaded dynamically
Only the components that the user needs are loaded initially	There will be many http requests as the components are loaded dynamically
Cna imporve the user experience while loaded by showing suspense fallback/ loading dicator	But, this suspense boundary needs a new chunk of code to be written for showing the shimmer component
5. When do we and why do we need suspense?
Suspense are useful when the components are waiting (React.lazy components are getting dynamically loaded) before rendering. Today, React Suspense only supports one use case which is loading components dynamically with React lazy(). In the future, it will support other use cases like data fetching.
chapter-09-optimizing-our-app/theory-assignment.md at main • Learn-React-With-Harshi/chapter-09-







Higher order component:
Takes one component as an input and output another component from that input.

Lifting state up: controlling two component state by using the parent state. Basically, controlling children component with the help of parent component.

Data is the new oil
UI layer & Data layer
Data layer -> states & props
state -> local variable/ scope is only within a component
props -> values passed from one component to another component
Props Drilling :- Passing props from one component to another which inturn passes to another component
AppLayout -> state (user) pass as prop to Body Body -> pass as prop to Body RestaurantCard ->
React Developer tool -> important extension -> debugging data layer Component & Profiler in console dev
Data layer:
props State Hooks rendered by source
Data from child to parent ?
state lifting
Context -> for storing a data that we can used throughout application
why not global variable -> react will not be able to track and trigger reconciliation
Create Context in utils
useContext -> hook
Context Provider -> displayName for debugging in React Dev Tools
chapter


Props Drilling
Prop drilling is a technique where data is passed from one component through multiple components until it gets to the component where the data is needed.
I have already implemented props drilling in our app InstaFood without knowing its actually name. So, I wanted to pass user info like name, email and isAuthenticated values that I get in landing page (AppLayout) component to NavComponent in Header where based on isAuthenticated value, display Login or Logout button.
Check App.js & Header.js to see how the props is passed from AppLayout to NavComponent of previous chapter to see the props drilling implementation. Because, in this chapter we will be modifying that with React Context. More about that in React context section below.
Lifting up state
When we want to pass some props from child component to parent or its siblings, we can use lifting up state technique. It can be thought as if the control is handed over to the parent and let the child modify the data through the function that is passed to child as props.
Child -> Parent
Again, I have already implemented this in InstaFood without knowing its actually name. On click of Favourites button in Body Component, only the restaurants that are marked favourite (enabled/disabled by toggling heart button on restaurant card component). For this, I wanted my marked restaurant data in Body to update the Body to show the favourite restaurant ie child's props must be passed to parent. For this, I moved the adding/removing favourites logic to Body and passed that function to child, where the child can update through that function. This is one way of lifting up state.
Child -> Siblings
I am implementing sharing data between Siblings feature in this chapter. For eg: There are multiple FAQs sections in the Help Page and all the FAQ answers are initially hidden, once the user clicks on any question, its corresponding answer is visible. If user clicks on any another question, the previous visible answer must be hidden and new answer must be visible.
All the FAQ sections are Siblings Components and Help is the Parent component.
Static Version : The data to display FAQ sections of Help page is mocked in config.js. Each section (faq) has an unique id, title (question) and description (answer). Loop through the FAQ array and display title and description of each FAQ in Section Components
Normal Approach : Each section might have a state isVisible and setIsVisible funtion to update the state. If isVisible is true, then show description and if false show hide description. The problem with this approach is each section does not know the state of its sibling section (we need them to know each other because on opening one section others must hide). For them to know each other's state, lifting up state technique is used. By this technique, the state (visibleSection) is maintained by parent which contains the id of the visible section.
Show/Hide Description:
  const [visibleSection, setVisibleSection] = useState("");
   /* Initially description of all questions are hidden */
Giving the control of state visibleSection to the parent (Help Component) and child (Section) can modify the state only through the callback function setIsVisible passed by the Parent (Help), in turn parent updates the state through setVisibleSection. This way the sibling components can be shown/hidden based on this state maintained by the parent. Initially description of all Section component is hidden. For this, " " is set as visibleSection.
<Section key={question.id} id={question.id} title={question.title} description={question.description}
   isVisible={visibleSection === question.id }
   setIsVisible={(display) => {
   if(display) {
      setVisibleSection(question.id);
   } else {
      setVisibleSection(" ");
   }}
} />
Since visibleSection is empty, visibleSection === question.id will be false and all section components isVisible will be 'false` and in Section component down arrow will be displayed for all components(all descriptions are hidden).
{
   isVisible ? (
   <SlArrowUp onClick={() => setIsVisible(false)} className="cursor-pointer" />
   ) : (
   <SlArrowDown onClick={() => setIsVisible(true)} className="cursor-pointer" />
)}



{isVisible && <p className="text-bio text-base">{description}</p>}
User clicks for the first time Once the user clicks on any section's down arrow button, the state that parent maintained is updated by the child through the callback funtion setIsVisible by setting true. Now, this value is passed as params (display) to callback function at line no: 51. Since display is true, setVisibleSection(question.id); will be executed and visibleSection is set with question.id. Now, {visibleSection === question.id } becomes true and isVisible is set true, because of which the arrow changes to up arrow and description is displayed. Note that all other sections state is still false and no changes happens there.
Subsequent User clicks on same FAQ Now, if the user again clicks on up arrow, it's setIsVisible is updated with false. Now, this value is passed as params (display) to callback function at line no: 51. Since display is false, setVisibleSection(" "); will be executed and visibleSection is set with " ". Now, {visibleSection === question.id } becomes false and isVisible is set false, because of which the arrow changes to down arrow and description is hidden.
User clicks on different FAQ If the user clicks on another FAQ, that FAQ's setIsVisible is updated to true, because of which the arrow changes to up arrow and description is displayed in the similar way mentioned above at line 75. If any other FAQ section's description was visible, that will hidden because the visibleSection state of parent now hold the newly clicked FAQ id which is different from question.id (check the condition at line no :51) and isVisible is set to true for current section only and all other visible descriptions are hidden because other sections isVisible is false.
React Context
In the props drilling examples, we tried to pass userInfo through multiple components to reach NavComponent. Props drilling could be used when data need to be passed to a few (2-3 components) before reaching its destination component. But, what if there are lot of components in the hierarchy which needs to be crossed, it becomes tedious and inefficient. The solution to this is to store the data in Context which could be then accessed throughout the application.
Let's try to use Context Provider to share userInfo data between Login, NavComponent & Footer .
•	Create a context UserContext with keys that we need in our user object and dummy values in UserContext.js under utils folder.
•	Import the created UserContext into the App.js (where we want to use)
•	Create a state to maintain this user object
•	Enclose <UserContext.Provider> </UserContext.Provider> component around the components where the user object must be accessible.
•	Now, pass this state as value props to the UserContext provider and use this components that needs it.
In Header
•	Let's say we must to use the user object in NavComponent in Header.js. Import UserContext that we created into Header.js
•	Create a variable user and set the UserContext using useContext(UserContext)
•	Now use user.name in Header
In Footer
•	Import UserContext that we created into Footer.js
•	Create a variable user and set the UserContext using useContext(UserContext)
•	Now use user.name in Header
Updating the Context in Login
•	Import UserContext that we created into Footer.js
•	Create a variable and set the UserContext using useContext(UserContext)
const {user, setUser} = useContext(UserContext); 
•	After succesful login of user, set the user response object (which contains the UserContext to be set) using setUser
•	Check if user.isAuthenticated is true and navigate to the landing page (App.js)
Updating the Context in Header
•	Once the user clicks on the Login/Logout button, set the user object to isAuthenticated to false before navigating to the login page
Nested Contexts









REDUX-TOOLKIT:

When we click on the add to cart it will dispatch an action then it will call reducer function and this function will update the slice of the redux store.
If you want to read the data from the redux store slice to the UI then you’ve to use selector.
Install @redux.js/toolkit and react-redux
Build our store
Connect our store to our app
Slice(cartSlice)
Dispatch(action)
Selector
Npm install @reduxjs/toolkit
Npm –I react-redux

To create the store we will use the redux toolkit.
 
To connect this store with our application we’ll use provider which will come form the react-redux.
 
Cart Slice:
import { createSlice } from "@reduxjs/toolkit";

const cartSlice = createSlice({
  name: "cart",
  initialState: {
    items: ["burgers", "pizza"],
  },
  reducers: {
    addItem: (state, action) => {
      state.items.push(action.payload);
    },
    removeItem: (state) => {
      state.items.pop();
    },
    clearCart: (state, action) => {
      state.items.length = 0;
    },
  },
});
export const { addItem, removeItem, clearCart } = cartSlice.actions;

export default cartSlice.reducer;

To connect this cart slice with the store
Appstore.js
import { configureStore } from "@reduxjs/toolkit";
import cartReducer from "./cartSlice";

const appStore = configureStore({
  reducer: {
    cart: cartReducer,
  },
});

export default appStore;

now to provide this store to our app:
in main app.js
return (
    <Provider store={appStore}>
      <UserContext.Provider value={{ loggedInUser: userName, setUserName }}>
        <div className="app">
          <Header />
          <Outlet />
        </div>
      </UserContext.Provider>
    </Provider>
  );
};

now how can I suscribe the data to the store, we can suscribe this data as follows:
import { useSelector } from "react-redux";

we have to make use of useSelector hook:

//Suscribing to the store using a selector
  const cartItems = useSelector((store) => store.cart.items);
now cartItems has all the data that are store in the cart.
in the header.js file use this:
 <li className="px-4 font-bold text-xl">
            Cart({cartItems.length}items)
          </li>
 now earlier we have put items in the cart by hardcoding but we want to add item in the cart using the button how can I do that:
 fot that I need to dispatch an action adding item in the cart:

 to dispatch an action we need to make use of a hook as :
 const dispatch = useDispatch();
<button
                className="p-2 mx-16 rounded-lg bg-black shadow-lg text-white m-auto"
                onClick={handleAddItem}
              >
                Add +
              </button>

const handleAddItem = ()=>{
    //dispatch an action:
    dispatch(addItem("pizza"))
  }
here we are adding item in the cart through button but still hardcoding the data, its not coming from the api list of data.

 
 
