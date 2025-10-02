# Openspherex
This is a digital products selling website 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Digital Products Store - Home</title>
    <style>
        /* Global Styles */
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f7fa;
            color: #333;
            line-height: 1.6;
        }

        header {
            background: linear-gradient(135deg, #4a90e2, #50e3c2);
            color: white;
            padding: 60px 20px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        header h1 {
            font-size: 3em;
            margin: 0;
            animation: fadeInDown 1s ease-out;
        }

        header p {
            font-size: 1.2em;
            margin: 10px 0 0;
            animation: fadeInUp 1s ease-out 0.5s;
            opacity: 0;
            animation-fill-mode: forwards;
        }

        /* Navigation */
        nav {
            background: #fff;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        nav ul {
            list-style: none;
            padding: 0;
            margin: 0;
            display: flex;
            justify-content: center;
        }

        nav li {
            margin: 0 15px;
        }

        nav a {
            text-decoration: none;
            color: #4a90e2;
            font-weight: bold;
            padding: 15px 20px;
            display: block;
            transition: color 0.3s, background 0.3s;
        }

        nav a:hover {
            color: #fff;
            background: #4a90e2;
            border-radius: 5px;
        }

        /* Hero Section Animation */
        .hero-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('https://via.placeholder.com/1920x400?text=Digital+Products+Hero') no-repeat center/cover;
            opacity: 0.2;
            animation: zoomIn 10s infinite alternate;
        }

        /* Products Section */
        #products {
            max-width: 1200px;
            margin: 40px auto;
            padding: 20px;
        }

        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .product-card {
            background: #fff;
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            overflow: hidden;
            transition: transform 0.3s, box-shadow 0.3s;
            animation: fadeIn 1s ease-out;
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.2);
        }

        .product-img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .product-card:hover .product-img {
            transform: scale(1.1);
        }

        .product-info {
            padding: 20px;
            text-align: center;
        }

        .product-info h3 {
            margin: 0 0 10px;
            font-size: 1.5em;
            color: #4a90e2;
        }

        .product-info p {
            margin: 0 0 15px;
            color: #666;
        }

        .price {
            font-size: 1.2em;
            font-weight: bold;
            color: #50e3c2;
            margin-bottom: 15px;
        }

        .buy-btn {
            background: #4a90e2;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            transition: background 0.3s;
        }

        .buy-btn:hover {
            background: #357abd;
        }

        /* Admin Section */
        #admin {
            max-width: 800px;
            margin: 40px auto;
            padding: 20px;
            background: #fff;
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            display: none; /* Hidden by default */
        }

        #admin h2 {
            text-align: center;
            color: #4a90e2;
        }

        form {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        input, textarea {
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1em;
        }

        button {
            background: #50e3c2;
            color: white;
            border: none;
            padding: 12px;
            border-radius: 5px;
            cursor: pointer;
            transition: background 0.3s;
        }

        button:hover {
            background: #3bb89f;
        }

        #product-list {
            margin-top: 30px;
        }

        .admin-product {
            border-bottom: 1px solid #ddd;
            padding: 10px 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .admin-product button {
            background: #e94e77;
            padding: 5px 10px;
            margin-left: 10px;
        }

        .admin-product button.edit {
            background: #4a90e2;
        }

        /* Footer */
        footer {
            background: #333;
            color: white;
            text-align: center;
            padding: 20px;
            margin-top: 40px;
        }

        /* Animations */
        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes zoomIn {
            from { transform: scale(1); }
            to { transform: scale(1.2); }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            header h1 { font-size: 2.5em; }
            .product-grid { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>
    <header>
        <div class="hero-bg"></div>
        <h1>Welcome to Digital Products Store</h1>
        <p>Your one-stop shop for premium digital downloads: eBooks, courses, software, and more!</p>
    </header>

    <nav>
        <ul>
            <li><a href="#home" onclick="showSection('home')">Home</a></li>
            <li><a href="#products" onclick="showSection('products')">Products</a></li>
            <li><a href="#admin" onclick="showSection('admin')">Admin Panel</a></li>
            <li><a href="#cart">Cart (0)</a></li>
        </ul>
    </nav>

    <section id="products">
        <h2>Featured Products</h2>
        <div class="product-grid" id="product-grid"></div>
    </section>

    <section id="admin">
        <h2>Admin Panel - Manage Products</h2>
        <form id="product-form">
            <input type="hidden" id="product-id">
            <input type="text" id="product-name" placeholder="Product Name" required>
            <textarea id="product-desc" placeholder="Product Description" required></textarea>
            <input type="number" id="product-price" placeholder="Price (USD)" step="0.01" required>
            <input type="url" id="product-img" placeholder="Image URL" required>
            <button type="submit">Add/Update Product</button>
        </form>
        <div id="product-list"></div>
    </section>

    <footer>
        &copy; 2025 Digital Products Store. All rights reserved. | Designed by Expert Software Engineer with 15+ Years Experience.
    </footer>

    <script>
        // Data Storage using LocalStorage (Simulating a Database)
        let products = JSON.parse(localStorage.getItem('products')) || [
            { id: 1, name: 'Ultimate JavaScript Guide', desc: 'Comprehensive eBook on modern JS.', price: 19.99, img: 'https://via.placeholder.com/300x200?text=JS+Guide' },
            { id: 2, name: 'Python for Data Science', desc: 'Online course with videos and projects.', price: 49.99, img: 'https://via.placeholder.com/300x200?text=Python+Course' },
            { id: 3, name: 'Graphic Design Toolkit', desc: 'Software bundle for designers.', price: 29.99, img: 'https://via.placeholder.com/300x200?text=Design+Toolkit' }
        ];

        // Function to Save Products
        function saveProducts() {
            localStorage.setItem('products', JSON.stringify(products));
        }

        // Function to Render Products on Home Page
        function renderProducts() {
            const grid = document.getElementById('product-grid');
            grid.innerHTML = '';
            products.forEach(product => {
                const card = document.createElement('div');
                card.className = 'product-card';
                card.innerHTML = `
                    <img src="${product.img}" alt="${product.name}" class="product-img">
                    <div class="product-info">
                        <h3>${product.name}</h3>
                        <p>${product.desc}</p>
                        <div class="price">$${product.price.toFixed(2)}</div>
                        <button class="buy-btn" onclick="addToCart(${product.id})">Buy Now</button>
                    </div>
                `;
                grid.appendChild(card);
            });
        }

        // Function to Render Admin Product List
        function renderAdminProducts() {
            const list = document.getElementById('product-list');
            list.innerHTML = '<h3>Existing Products</h3>';
            products.forEach(product => {
                const div = document.createElement('div');
                div.className = 'admin-product';
                div.innerHTML = `
                    <span>${product.name} - $${product.price.toFixed(2)}</span>
                    <button class="edit" onclick="editProduct(${product.id})">Edit</button>
                    <button onclick="deleteProduct(${product.id})">Delete</button>
                `;
                list.appendChild(div);
            });
        }

        // Add/Update Product
        document.getElementById('product-form').addEventListener('submit', (e) => {
            e.preventDefault();
            const id = parseInt(document.getElementById('product-id').value) || Date.now();
            const name = document.getElementById('product-name').value;
            const desc = document.getElementById('product-desc').value;
            const price = parseFloat(document.getElementById('product-price').value);
            const img = document.getElementById('product-img').value;

            const index = products.findIndex(p => p.id === id);
            if (index > -1) {
                products[index] = { id, name, desc, price, img };
            } else {
                products.push({ id, name, desc, price, img });
            }

            saveProducts();
            renderProducts();
            renderAdminProducts();
            e.target.reset();
            document.getElementById('product-id').value = '';
        });

        // Edit Product
        function editProduct(id) {
            const product = products.find(p => p.id === id);
            if (product) {
                document.getElementById('product-id').value = product.id;
                document.getElementById('product-name').value = product.name;
                document.getElementById('product-desc').value = product.desc;
                document.getElementById('product-price').value = product.price;
                document.getElementById('product-img').value = product.img;
            }
        }

        // Delete Product
        function deleteProduct(id) {
            if (confirm('Are you sure you want to delete this product?')) {
                products = products.filter(p => p.id !== id);
                saveProducts();
                renderProducts();
                renderAdminProducts();
            }
        }

        // Simple Cart Functionality (Placeholder)
        let cart = JSON.parse(localStorage.getItem('cart')) || [];
        function addToCart(id) {
            const product = products.find(p => p.id === id);
            if (product) {
                cart.push(product);
                localStorage.setItem('cart', JSON.stringify(cart));
                alert(`${product.name} added to cart!`);
                // Update cart count in nav (simplified)
                document.querySelector('a[href="#cart"]').textContent = `Cart (${cart.length})`;
            }
        }

        // Section Navigation (SPA-like)
        function showSection(section) {
            document.querySelectorAll('section').forEach(sec => sec.style.display = 'none');
            const target = document.getElementById(section);
            if (target) target.style.display = 'block';
        }

        // Initial Render
        renderProducts();
        renderAdminProducts();
        showSection('products'); // Default to products

        // Animation Trigger on Load
        window.addEventListener('load', () => {
            document.querySelector('header p').style.animation = 'fadeInUp 1s ease-out forwards';
        });
    </script>
</body>
</html>
