<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>FoodReserve - Buy Now, Collect Later</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f5f5f5;
        }

        header {
            background-color: #ff9900;
            color: white;
            padding: 20px;
            text-align: center;
            position: relative;
        }

        h1 {
            font-size: 36px;
        }

        /* Loading Indicator */
        .loading {
            position: absolute;
            top: 20px;
            right: 20px;
            width: 30px;
            height: 30px;
            border: 5px solid white;
            border-top: 5px solid #ff9900;
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Navigation Menu */
        nav {
            background-color: #333;
            overflow: hidden;
        }

        nav a {
            float: left;
            display: block;
            color: white;
            text-align: center;
            padding: 14px 16px;
            text-decoration: none;
        }

        nav a:hover {
            background-color: #ff9900;
            color: black;
        }

        .container {
            margin: 20px;
        }

        /* Product Cards */
        .product {
            display: inline-block;
            border: 1px solid #ccc;
            padding: 20px;
            margin: 10px;
            text-align: center;
            width: 250px;
            background-color: white;
            box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
        }

        .product img {
            max-width: 200px;
            height: auto;
        }

        .product h3 {
            font-size: 20px;
        }

        .product p {
            font-size: 16px;
        }

        /* Price and Cart Actions */
        .product-price {
            color: green;
            font-weight: bold;
        }

        .cart-action {
            margin-top: 10px;
        }

        .cart-action button {
            padding: 10px;
            background-color: #ff9900;
            color: white;
            border: none;
            cursor: pointer;
            border-radius: 5px;
        }

        .cart-action button:hover {
            background-color: #e68a00;
        }

        /* Cart Section */
        #cart {
            background-color: #fff;
            padding: 20px;
            margin: 20px 0;
            border: 1px solid #ccc;
            box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
        }

        #cart h2 {
            font-size: 28px;
        }

        .cart-items {
            list-style: none;
            padding: 0;
        }

        .cart-items li {
            padding: 10px;
            border-bottom: 1px solid #ccc;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .cart-items li span {
            font-size: 18px;
        }

        .remove-btn {
            background-color: #ff3333;
            color: white;
            padding: 5px 10px;
            border: none;
            cursor: pointer;
            border-radius: 5px;
        }

        .remove-btn:hover {
            background-color: #cc0000;
        }

        /* Total Price */
        #cart-total {
            font-size: 24px;
            margin-top: 20px;
            text-align: right;
        }

        /* Checkout and Payment Button */
        #checkout, #payment {
            display: none;
            background-color: #28a745;
            color: white;
            padding: 10px;
            text-align: center;
            font-size: 18px;
            cursor: pointer;
            margin-top: 20px;
            border-radius: 5px;
            position: flex;
        }

        #checkout.show, #payment.show {
            display: block;
        }

        /* Always visible Payment Button */
        #payment {
            display: block; /* Make Payment button is always visible */
        }

        /* Social Media Icons */
        .social-media {
            margin: 40px 0;
            text-align: center;
        }

        .social-media img {
            width: 40px;
            height: 40px;
            margin: 0 10px;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .social-media img:hover {
            transform: scale(1.2);
        }

        /* Footer Section */
        footer {
            background-color: #333;
            color: white;
            padding: 20px;
            text-align: center;
            font-size: 14px;
        }

        footer p {
            margin: 0;
        }

        /* Media Query for Larger Screens */
        @media (min-width: 768px) {
            .product {
                width: 300px; /* Adjust product card width */
            }
        }

        @media (min-width: 1024px) {
            .container {
                max-width: 1200px; /* Limit max width for larger screens */
                margin: auto;
                display: flex;
                flex-wrap: wrap;
                justify-content: space-around;
            }
            nav a {
                padding: 14px 20px; /* Increase padding on larger screens */
            }
        }
    </style>
</head>
<body>

    <!-- Header Section -->
    <header>
        <h1>FoodReserve</h1>
        <p>Buy Non-Perishable Food Now, Collect Later - Beat Inflation</p>
        <div class="loading"></div> <!-- Loading indicator -->
    </header>

    <!-- Navigation Section -->
    <nav>
        <a href="#products">Products</a>
        <a href="#cart">Your Cart</a>
        <a href="#value-tracker">Market Value</a>
        <a href="#contact">Contact Us</a>
    </nav>

    <!-- Product Display Section -->
    <section id="products" class="container">
        <h2>Shop Non-Perishable Food</h2>
        <div class="product">
            <img src="https://example.com/rice.jpg" alt="Rice">
            <h3>Bag of Rice (50kg)</h3>
            <p class="product-price">₦50,000</p>
            <div class="cart-action">
                <button onclick="addToCart('Bag of Rice (50kg)', 50000)">Add to Cart</button>
            </div>
        </div>
        <div class="product">
            <img src="https://example.com/sugar.jpg" alt="Sugar">
            <h3>Bag of Sugar (25kg)</h3>
            <p class="product-price">₦30,000</p>
            <div class="cart-action">
                <button onclick="addToCart('Bag of Sugar (25kg)', 30000)">Add to Cart</button>
            </div>
        </div>
        <div class="product">
            <img src="https://example.com/oil.jpg" alt="Vegetable Oil">
            <h3>25L Vegetable Oil</h3>
            <p class="product-price">₦20,000</p>
            <div class="cart-action">
                <button onclick="addToCart('Vegetable Oil (25L)', 20000)">Add to Cart</button>
            </div>
        </div>
        <div class="product">
            <img src="https://example.com/pasta.jpg" alt="Pasta">
            <h3>500g Pasta</h3>
            <p class="product-price">₦2,000</p>
            <div class="cart-action">
                <button onclick="addToCart('500g Pasta', 2000)">Add to Cart</button>
            </div>
        </div>
        <div class="product">
            <img src="https://example.com/tomato-sauce.jpg" alt="Tomato Sauce">
            <h3>1L Tomato Sauce</h3>
            <p class="product-price">₦5,000</p>
            <div class="cart-action">
                <button onclick="addToCart('1L Tomato Sauce', 5000)">Add to Cart</button>
            </div>
        </div>
        <div class="product">
            <img src="https://example.com/canned-beans.jpg" alt="Canned Beans">
            <h3>400g Canned Beans</h3>
            <p class="product-price">₦1,500</p>
            <div class="cart-action">
                <button onclick="addToCart('400g Canned Beans', 1500)">Add to Cart</button>
            </div>
        </div>
        <div class="product">
            <img src="https://example.com/peanut-butter.jpg" alt="Peanut Butter">
            <h3>500g Peanut Butter</h3>
            <p class="product-price">₦3,500</p>
            <div class="cart-action">
                <button onclick="addToCart('500g Peanut Butter', 3500)">Add to Cart</button>
            </div>
        </div>
        <div class="product">
            <img src="https://example.com/jam.jpg" alt="Jam">
            <h3>400g Jam</h3>
            <p class="product-price">₦2,500</p>
            <div class="cart-action">
                <button onclick="addToCart('400g Jam', 2500)">Add to Cart</button>
            </div>
        </div>
        <div class="product">
            <img src="https://example.com/instant-noodles.jpg" alt="Instant Noodles">
            <h3>5 Pack Instant Noodles</h3>
            <p class="product-price">₦1,200</p>
            <div class="cart-action">
                <button onclick="addToCart('5 Pack Instant Noodles', 1200)">Add to Cart</button>
            </div>
        </div>
        <div class="product">
            <img src="https://example.com/salt.jpg" alt="Salt">
            <h3>1kg Salt</h3>
            <p class="product-price">₦500</p>
            <div class="cart-action">
                <button onclick="addToCart('1kg Salt', 500)">Add to Cart</button>
            </div>
        </div>
    </section>

    <!-- Cart Section -->
    <section id="cart" class="container">
        <h2>Your Cart</h2>
        <ul class="cart-items" id="cart-items">
            <!-- Cart items will be added here dynamically -->
        </ul>
        <div id="cart-total">Total: ₦0</div>
        <div id="checkout">Proceed to Checkout</div>
        <div id="payment">Make Payment</div> <!-- Always visible payment button -->
    </section>

    <!-- Social Media Section -->
    <div class="social-media">
        <a href="https://facebook.com" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/733/733547.png" alt="Facebook"></a>
        <a href="https://instagram.com" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/2111/2111463.png" alt="Instagram"></a>
        <a href="https://twitter.com" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/733/733579.png" alt="Twitter"></a>
    </div>

    <!-- Footer Section -->
    <footer>
        <p>Developed by ChallelEnterprise © 2024</p>
    </footer>

    <script>
        let cartTotal = 0;
        const cartItems = [];

        function addToCart(itemName, itemPrice) {
            const existingItem = cartItems.find(item => item.name === itemName);
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                cartItems.push({ name: itemName, price: itemPrice, quantity: 1 });
            }
            updateCart();
        }

        function removeFromCart(index) {
            cartItems.splice(index, 1);
            updateCart();
        }

        function updateCart() {
            const cartItemsContainer = document.getElementById('cart-items');
            cartItemsContainer.innerHTML = ''; // Clear cart

            cartTotal = 0;

            cartItems.forEach((item, index) => {
                const listItem = document.createElement('li');
                listItem.innerHTML = `<span>${item.name} x${item.quantity} - ₦${item.price * item.quantity}</span> 
                                      <button class="remove-btn" onclick="removeFromCart(${index})">Remove</button>`;
                cartItemsContainer.appendChild(listItem);

                cartTotal += item.price * item.quantity;
            });

            // Update cart total
            document.getElementById('cart-total').innerText = `Total: ₦${cartTotal}`;

            // Show checkout button if total >= ₦100,000
            if (cartTotal >= 100000) {
                document.getElementById('checkout').classList.add('show');
            } else {
                document.getElementById('checkout').classList.remove('show');
            }
        }

        // Rotating loading indicator
        setInterval(() => {
            document.querySelector('.loading').style.display = 
                document.querySelector('.loading').style.display === 'none' ? 'block' : 'none';
        }, 10000);
    </script>

</body>
</html>
