<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>VK Groups and Foods</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;700&display=swap" rel="stylesheet">
<style>
    /* --- RESET & BASIC --- */
    * { box-sizing: border-box; }
    body {
        font-family: 'Poppins', sans-serif;
        margin: 0;
        padding: 0;
        background: linear-gradient(135deg, #FF6B6B, #FFBE0B); 
        height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
        overflow: hidden;
    }

    /* --- MOBILE CONTAINER --- */
    #mobile-app {
        width: 100%;
        max-width: 400px;
        height: 100vh;
        max-height: 800px;
        background: #fff;
        position: relative;
        overflow-y: auto;
        box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        display: flex;
        flex-direction: column;
    }

    @media (min-width: 450px) {
        #mobile-app {
            height: 90vh;
            border-radius: 20px;
            overflow: hidden;
        }
    }

    /* --- PAGE SYSTEM --- */
    .page {
        display: none !important;
        width: 100%;
        height: 100%;
        padding: 20px;
        overflow-y: auto;
        animation: fadeIn 0.4s ease;
        padding-bottom: 80px;
    }

    .page.active {
        display: block !important;
    }
    
    #start-page.active {
        display: flex !important;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        text-align: center;
    }

    @keyframes fadeIn {
        from { opacity: 0; transform: translateY(10px); }
        to { opacity: 1; transform: translateY(0); }
    }

    /* --- HEADER --- */
    header {
        background: #e63946;
        color: white;
        padding: 15px;
        text-align: center;
        flex-shrink: 0;
        z-index: 10;
        box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        display: flex;
        align-items: center;
        justify-content: center;
        position: relative;
    }
    
    header h1 { 
        margin: 0; 
        font-size: 1.2rem; 
        padding-left: 40px; 
    }

    /* --- LOGO STYLING --- */
    .logo-img {
        width: 45px;
        height: 45px;
        border-radius: 50%;
        border: 2px solid white;
        object-fit: contain;
        position: absolute;
        left: 15px;
        background: white;
        padding: 2px;
    }

    /* --- INPUTS & BUTTONS --- */
    input, select {
        width: 100%;
        padding: 14px;
        margin: 10px 0;
        border: 1px solid #ddd;
        border-radius: 8px;
        background: #f9f9f9;
        font-size: 1rem;
    }

    button {
        width: 100%;
        padding: 15px;
        margin-top: 15px;
        border: none;
        border-radius: 10px;
        background: #e63946;
        color: white;
        font-size: 1.1rem;
        font-weight: bold;
        cursor: pointer;
        transition: transform 0.1s;
        box-shadow: 0 4px 10px rgba(230, 57, 70, 0.4);
    }
    button:active { transform: scale(0.96); }
    
    button.outline {
        background: transparent;
        border: 2px solid #e63946;
        color: #e63946;
        box-shadow: none;
    }

    /* --- SPECIFIC STYLES --- */
    #start-page {
        background: linear-gradient(rgba(255,255,255,0.95), rgba(255,255,255,0.95)), 
                    url('https://images.unsplash.com/photo-1504674900247-0877df9cc836?w=500');
        background-size: cover;
    }

    .food-card {
        background: white;
        border-radius: 12px;
        margin-bottom: 20px;
        overflow: hidden;
        box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        border: 1px solid #eee;
    }
    
    .food-img { width: 100%; height: 180px; object-fit: cover; background: #eee; }
    .card-body { padding: 15px; text-align: center; }
    .card-body h3 { margin: 0 0 10px 0; font-size: 1.1rem; }

    .cart-item {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 15px;
        border-bottom: 1px solid #eee;
        background: #fff;
    }
</style>
</head>
<body>

<div id="mobile-app">
    
    <header>
        <img src="file:///C:/Users/Jeevan%20S.K/AppData/Local/Packages/5319275A.WhatsAppDesktop_cv1g1gvanyjgm/TempState/B635F9E3C038855C68C2704F08CAEEE1/WhatsApp%20Image%202025-11-29%20at%2023.04.33_19e6de43.jpg" class="logo-img" alt="VK Logo">
        <h1>VK Groups & Foods</h1>
    </header>

    <div id="start-page" class="page active">
        <img src="file:///C:/Users/Jeevan%20S.K/AppData/Local/Packages/5319275A.WhatsAppDesktop_cv1g1gvanyjgm/TempState/B635F9E3C038855C68C2704F08CAEEE1/WhatsApp%20Image%202025-11-29%20at%2023.04.33_19e6de43.jpg" style="width:120px; height:120px; margin-bottom:20px; border-radius:50%; object-fit:cover;">
        
        <h2 style="color: #333; margin-bottom: 10px;">Welcome to<br>VK Groups and Foods</h2>
        <p style="color: #666; margin-bottom: 30px;">Delicious food delivered fast.</p>
        <button onclick="navigate('login-page')">Order Now</button>
    </div>

    <div id="login-page" class="page">
        <h2>Login</h2>
        <p>Enter your details to order.</p>
        <input type="email" placeholder="Email">
        <input type="password" placeholder="Password">
        <button onclick="navigate('address-page')">Login</button>
        <button class="outline" onclick="navigate('otp-page')">Login with OTP</button>
    </div>

    <div id="otp-page" class="page">
        <h2>OTP Verification</h2>
        <input id="otp-mobile" placeholder="Mobile Number">
        <button class="outline" onclick="alert('OTP Sent: 1234')">Send OTP</button>
        <input id="otp-code" placeholder="Enter OTP">
        <button onclick="checkOtp()">Verify</button>
        <button class="outline" onclick="navigate('login-page')">Back</button>
    </div>

    <div id="address-page" class="page">
        <h2>Delivery Address</h2>
        <input placeholder="Full Name">
        <input placeholder="City / Area">
        <input placeholder="Pincode" type="number">
        <button onclick="navigate('category-page')">Next</button>
    </div>

    <div id="category-page" class="page">
        <h2>Select Category</h2>
        
        <div class="food-card">
            <img src="https://images.pexels.com/photos/1640777/pexels-photo-1640777.jpeg?auto=compress&cs=tinysrgb&w=600" class="food-img" alt="Veg Food">
            <div class="card-body">
                <h3>Vegetarian 🥦</h3>
                <p>Paneer, Dosa, Pizza & More</p>
                <button onclick="loadMenu('veg')">View Veg Menu</button>
            </div>
        </div>

        <div class="food-card">
            <img src="https://images.pexels.com/photos/2338407/pexels-photo-2338407.jpeg?auto=compress&cs=tinysrgb&w=600" class="food-img" alt="Non Veg Food">
            <div class="card-body">
                <h3>Non-Vegetarian 🍗</h3>
                <p>Chicken, Fish, Biryani & More</p>
                <button onclick="loadMenu('nonveg')">View Non-Veg Menu</button>
            </div>
        </div>
    </div>

    <div id="menu-page" class="page">
        <h2 id="menu-title">Menu</h2>
        <div id="menu-list"></div>
        <button class="outline" onclick="navigate('category-page')">Back to Categories</button>
    </div>

    <div id="details-page" class="page">
        <img id="detail-img" src="" class="food-img" style="border-radius:10px;">
        <h2 id="detail-name" style="margin-top:15px;">Food Name</h2>
        
        <label>Taste:</label>
        <select id="detail-taste">
            <option>Normal</option>
            <option>Spicy 🔥</option>
            <option>Extra Spicy 🥵</option>
        </select>

        <label>Quantity:</label>
        <input id="detail-qty" type="number" value="1" min="1">

        <button onclick="addToCart()">Add to Cart 🛒</button>
        <button class="outline" onclick="navigate('menu-page')">Cancel</button>
    </div>

    <div id="cart-page" class="page">
        <h2>Your Cart 🛍</h2>
        <div id="cart-items"></div>
        <button onclick="navigate('success-page')">Place Order</button>
        <button class="outline" onclick="navigate('category-page')">Add More Items</button>
    </div>

    <div id="success-page" class="page" style="text-align: center;">
        <div style="font-size: 5rem; margin-top: 50px;">🎉</div>
        <h2>Order Placed!</h2>
        <p>Thank you for choosing<br><b>VK Groups and Foods</b></p>
        <p>Your food will arrive in 30 mins.</p>
        <button onclick="location.reload()">Back to Home</button>
    </div>

</div>

<script>
    // --- RELIABLE IMAGE LINKS ---
    const menuData = {
        veg: [
            { name: "Paneer Tikka", img: "https://images.pexels.com/photos/3928854/pexels-photo-3928854.png?auto=compress&cs=tinysrgb&w=400" },
            { name: "Veg Burger", img: "https://images.pexels.com/photos/1600711/pexels-photo-1600711.jpeg?auto=compress&cs=tinysrgb&w=400" },
            { name: "Masala Dosa", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/9/9f/Masala_Dosa_Food.jpg/640px-Masala_Dosa_Food.jpg" }, 
            { name: "Veg Pizza", img: "https://images.pexels.com/photos/315755/pexels-photo-315755.jpeg?auto=compress&cs=tinysrgb&w=400" },
            { name: "French Fries", img: "https://images.pexels.com/photos/1583884/pexels-photo-1583884.jpeg?auto=compress&cs=tinysrgb&w=400" },
            { name: "Gobi Manchurian", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/6/6d/Gobi_Manchurian_Dry.jpg/640px-Gobi_Manchurian_Dry.jpg" },
            { name: "Pav Bhaji", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Pav_Bhaji_in_Mumbai.jpg/640px-Pav_Bhaji_in_Mumbai.jpg" },
            { name: "Veg Biryani", img: "https://images.pexels.com/photos/12737656/pexels-photo-12737656.jpeg?auto=compress&cs=tinysrgb&w=400" },
            { name: "Chole Bhature", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/9/91/Chole_Bhature_delhi_street_food.jpg/640px-Chole_Bhature_delhi_street_food.jpg" },
            { name: "Idli Vada", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/0/0b/Idli_Sambar_Vada.jpg/640px-Idli_Sambar_Vada.jpg" }
        ],
        nonveg: [
            { name: "Chicken Biryani", img: "https://images.pexels.com/photos/12737656/pexels-photo-12737656.jpeg?auto=compress&cs=tinysrgb&w=400" },
            { name: "Grilled Chicken", img: "https://images.pexels.com/photos/106343/pexels-photo-106343.jpeg?auto=compress&cs=tinysrgb&w=400" },
            { name: "Fish Fry", img: "https://images.pexels.com/photos/262959/pexels-photo-262959.jpeg?auto=compress&cs=tinysrgb&w=400" },
            { name: "Chicken Burger", img: "https://images.pexels.com/photos/1600711/pexels-photo-1600711.jpeg?auto=compress&cs=tinysrgb&w=400" },
            { name: "Mutton Curry", img: "https://images.pexels.com/photos/9609848/pexels-photo-9609848.jpeg?auto=compress&cs=tinysrgb&w=400" },
            { name: "Chicken Wings", img: "https://images.pexels.com/photos/60616/fried-chicken-chicken-fried-crunchy-60616.jpeg?auto=compress&cs=tinysrgb&w=400" },
            { name: "Tandoori Chicken", img: "https://images.pexels.com/photos/106343/pexels-photo-106343.jpeg?auto=compress&cs=tinysrgb&w=400" },
            { name: "Egg Curry", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/32/Egg_Curry.jpg/640px-Egg_Curry.jpg" },
            { name: "Prawn Masala", img: "https://images.pexels.com/photos/262959/pexels-photo-262959.jpeg?auto=compress&cs=tinysrgb&w=400" },
            { name: "Butter Chicken", img: "https://images.pexels.com/photos/2474661/pexels-photo-2474661.jpeg?auto=compress&cs=tinysrgb&w=400" }
        ]
    };

    let cart = [];
    let selectedItem = null;

    function navigate(pageId) {
        document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
        const target = document.getElementById(pageId);
        if (target) {
            target.classList.add('active');
            target.scrollTop = 0;
        }
    }

    function checkOtp() {
        if(document.getElementById('otp-code').value === "1234") {
            navigate('address-page');
        } else {
            alert("Wrong OTP! Please use 1234");
        }
    }

    function loadMenu(type) {
        const list = document.getElementById('menu-list');
        list.innerHTML = "";
        document.getElementById('menu-title').innerText = type === 'veg' ? "Vegetarian Menu 🥦" : "Non-Veg Menu 🍗";

        menuData[type].forEach(item => {
            list.innerHTML += `
                <div class="food-card">
                    <img src="${item.img}" class="food-img" alt="${item.name}" onerror="this.src='https://cdn-icons-png.flaticon.com/512/135/135620.png'">
                    <div class="card-body">
                        <h3>${item.name}</h3>
                        <button onclick="openItem('${item.name}', '${item.img}')">Select</button>
                    </div>
                </div>
            `;
        });
        navigate('menu-page');
    }

    function openItem(name, img) {
        selectedItem = { name, img };
        document.getElementById('detail-name').innerText = name;
        document.getElementById('detail-img').src = img;
        navigate('details-page');
    }

    function addToCart() {
        const taste = document.getElementById('detail-taste').value;
        const qty = document.getElementById('detail-qty').value;
        cart.push({ ...selectedItem, taste, qty });
        renderCart();
        navigate('cart-page');
    }

    function renderCart() {
        const container = document.getElementById('cart-items');
        container.innerHTML = "";
        if (cart.length === 0) {
            container.innerHTML = "<p style='text-align:center'>Cart is empty.</p>";
            return;
        }
        cart.forEach(item => {
            container.innerHTML += `
                <div class="cart-item">
                    <img src="${item.img}" style="width:50px; height:50px; border-radius:50%; object-fit:cover;">
                    <div style="flex-grow:1; margin-left:15px;">
                        <b>${item.name}</b><br>
                        <span style="font-size:0.9rem; color:#666;">${item.taste} | Qty: ${item.qty}</span>
                    </div>
                </div>
            `;
        });
    }
</script>

</body>
</html>
