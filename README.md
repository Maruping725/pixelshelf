<!DOCTYPE html>
<html><img src="https://via.placeholder.com/300">
<head>
<title>PixelShelf Marketplace</title>

<style>

body{
font-family: Arial;
margin:0;
background:#0f0f1a;
color:white;
}

header{
text-align:center;
padding:40px;
background:linear-gradient(90deg,#7b2cff,#00e5ff);
}

.search{
padding:12px;
width:250px;
border-radius:6px;
border:none;
margin-top:10px;
}

.container{
width:90%;
margin:auto;
}

.grid{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
gap:20px;
margin-top:40px;
}

.card{
background:#1a1a2e;
padding:15px;
border-radius:10px;
text-align:center;
}

.card img{
width:100%;
border-radius:8px;
}

.price{
color:#ff9c7a;
font-weight:bold;
}

button{
margin-top:10px;
padding:10px;
width:100%;
border:none;
border-radius:6px;
background:#00e5ff;
cursor:pointer;
}

footer{
margin-top:60px;
padding:30px;
text-align:center;
background:#111;
}

</style>
</head>

<body>

<header>
<h1>PixelShelf</h1>
<p>Buy Creative Digital Assets</p>

<input class="search" placeholder="Search stickers, wallpapers, bitmojis">

</header>

<div class="container">

<h2>Trending Products</h2>

<div class="grid">

<div class="card">
<img src="https://via.placeholder.com/300">
<h3>Meme Sticker Pack</h3>
<p class="price">$5</p>
<button>Buy & Download</button>
</div>

<div class="card">
<img src="https://via.placeholder.com/300">
<h3>Brain Rot Wallpaper</h3>
<p class="price">$3</p>
<button>Buy & Download</button>
</div>

<div class="card">
<img src="https://via.placeholder.com/300">
<h3>Custom Bitmoji Set</h3>
<p class="price">$7</p>
<button>Buy & Download</button>
</div>

</div>

</div>

<footer>
<p>PixelShelf Marketplace</p>
<p>Support • Terms • Account</p>
</footer>

</body>
</html>
