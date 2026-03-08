<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>PixelShelf Store</title>
<link rel="stylesheet" href="styles.css">
</head>

<body>

<header>
<h1>PixelShelf</h1>
<p>Digital products for creators</p>fetch("products.json")
.then(res => res.json())
.then(data => {

const container = document.getElementById("products")

data.forEach(product => {

container.innerHTML += `
<div class="product">
<img src="${product.image}">
<h3>${product.name}</h3>
<p>${product.price}</p>
<a href="${product.link}" target="_blank">Buy</a>
</div>
`

})

})
</header>

<section id="products"></section>

<script src="script.js"></script>

</body>
</html>
