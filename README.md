<!DOCTYPE html>
<html>
<head>
<title>Dave Dropshipping Store</title>

<meta name="viewport" content="width=device-width, initial-scale=1">

<style>

body{
font-family:Arial;
margin:0;
background:#f4f6f8;
}

header{
background:#111;
color:white;
padding:20px;
text-align:center;
}

.search{
text-align:center;
margin:20px;
}

.search input{
padding:10px;
width:260px;
}

.products{
display:flex;
flex-wrap:wrap;
justify-content:center;
}

.product{
background:white;
border:1px solid #ddd;
margin:10px;
padding:15px;
width:200px;
text-align:center;
}

.product img{
width:150px;
height:150px;
object-fit:contain;
}

button{
background:#28a745;
color:white;
border:none;
padding:8px;
cursor:pointer;
}

.cart{
background:white;
width:350px;
margin:40px auto;
padding:20px;
border:1px solid #ddd;
}

.remove{
background:red;
margin-left:10px;
}

</style>

</head>

<body>

<header>

<h1>Dave Dropshipping Store</h1>
<p>Global Marketplace</p>

</header>

<div class="search">

<input type="text" id="search" placeholder="Search products..." onkeyup="searchProducts()">

</div>

<div id="products" class="products"></div>

<div class="cart">

<h2>Cart (<span id="count">0</span>)</h2>

<ul id="cart-items"></ul>

<p>Total: $<span id="total">0</span></p>

<div id="paypal-button-container"></div>

</div>

<script src="https://www.paypal.com/sdk/js?client-id=YOUR_CLIENT_ID&currency=USD"></script>

<script>

let products=[]
let cart=[]
let total=0

function displayProducts(list){

let container=document.getElementById("products")

container.innerHTML=""

list.forEach(p=>{

let div=document.createElement("div")

div.className="product"

div.innerHTML=`

<img src="${p.image}">

<h3>${p.title}</h3>

<p>$${p.price}</p>

<button onclick="addToCart('${p.title}',${p.price})">Add to Cart</button>

`

container.appendChild(div)

})

}

function addToCart(name,price){

cart.push({name,price})

updateCart()

}

function removeItem(index){

cart.splice(index,1)

updateCart()

}

function updateCart(){

let list=document.getElementById("cart-items")

list.innerHTML=""

total=0

cart.forEach((item,i)=>{

total+=item.price

let li=document.createElement("li")

li.innerHTML=`${item.name} - $${item.price}
<button class="remove" onclick="removeItem(${i})">X</button>`

list.appendChild(li)

})

document.getElementById("total").innerText=total.toFixed(2)
document.getElementById("count").innerText=cart.length

}

function searchProducts(){

let text=document.getElementById("search").value.toLowerCase()

let filtered=products.filter(p=>p.title.toLowerCase().includes(text))

displayProducts(filtered)

}

fetch("https://fakestoreapi.com/products")

.then(res=>res.json())

.then(data=>{

products=data

displayProducts(products)

})

paypal.Buttons({

createOrder: function(data, actions) {

return actions.order.create({
purchase_units: [{
amount: {
value: total.toFixed(2)
}
}]
});

},

onApprove: function(data, actions) {

return actions.order.capture().then(function(details) {

alert("Payment completed by " + details.payer.name.given_name)

});

}

}).render('#paypal-button-container')

</script>

</body>
</html>
