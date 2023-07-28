---
title: "Props in React"
datePublished: Mon Jul 24 2023 04:46:10 GMT+0000 (Coordinated Universal Time)
cuid: clkgdxy4i000109mwhual4us0
slug: props-in-react
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1690173832874/7c9e7073-a20c-4974-8845-d69f95daf810.webp
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1690173959511/2f5c21f3-260c-4987-8fba-84a7872aee20.webp
tags: reactjs, props, props-in-reactjs

---

React relies on props, which stands for "properties," as a fundamental concept. Props allow data and values to be passed from one component to another, enabling dynamic and unique outputs.

Websites developed using React, such as Facebook, Twitter, and Netflix, apply consistent design patterns across various sections that differ mainly in their data. This reusability is accomplished by utilizing props.

This article aims to provide a comprehensive understanding of React props, including their syntax for passing and receiving data. To reinforce this knowledge, a practical example of building a section for an e-commerce site, displaying information about different products to users, will be covered.

React Props are inputs passed into components, allowing them to access customized data, values, and information. The data flow in React is unidirectional, meaning data can only be transferred from the parent component to child components, and child components cannot modify the data passed to them.

To send props into a component, the syntax resembles that of HTML attributes, where you assign values to properties of the component:

```javascript
<ComponentName property1="value" property2="value" property3="value" />
```

```javascript
function Product(props) {
    return (
        <div>
            <img src={props.img} alt="products" />
            <h4>{props.name}</h4>
            <p>{props.desc}</p>
            <h4>{props.price}</h4>
        </div>
    );
}
```

Using props allows us to dynamically render data without hard-coding it into the component. By reusing the component with different prop values, we achieve the desired flexibility.

For better code readability and conciseness, we can use destructuring to access props directly within the function's parameter:

```javascript
function Product({ img, name, desc, price }) {
    return (
        <div>
            <img src={img} alt="products" />
            <h4>{name}</h4>
            <p>{desc}</p>
            <h4>{price}</h4>
        </div>
    );
}
```

In conclusion, understanding React props is crucial for creating dynamic web pages with reusable components.