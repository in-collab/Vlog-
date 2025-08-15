<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tripti Clothing</title>
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            background-color: #fdfdfd;
            color: #333;
        }
        header {
            background-color: #ff4b5c;
            color: white;
            padding: 15px 30px;
            text-align: center;
        }
        header h1 {
            margin: 0;
            font-size: 2rem;
        }
        nav {
            display: flex;
            justify-content: center;
            gap: 20px;
            background: #ff6f81;
            padding: 10px 0;
        }
        nav a {
            color: white;
            text-decoration: none;
            font-weight: bold;
        }
        .container {
            padding: 20px;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }
        .card {
            background: white;
            border-radius: 10px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
            overflow: hidden;
            text-align: center;
            transition: transform 0.3s ease;
        }
        .card:hover {
            transform: translateY(-5px) rotate(-1deg);
        }
        .card img {
            width: 100%;
            height: auto;
        }
        .card h3 {
            margin: 10px 0;
            font-size: 1.2rem;
        }
        .card p {
            color: #777;
            font-size: 0.9rem;
            margin-bottom: 10px;
        }
        .btn {
            display: inline-block;
            padding: 8px 15px;
            background-color: #ff4b5c;
            color: white;
            border-radius: 5px;
            text-decoration: none;
            margin-bottom: 15px;
        }
        footer {
            background: #ff4b5c;
            color: white;
            text-align: center;
            padding: 15px;
            margin-top: 30px;
        }
        footer a {
            color: yellow;
            text-decoration: none;
        }
    </style>
</head>
<body>

  <header>
        <h1>Tripti Clothing</h1>
        <p>Elegant Outfits for Every Occasion</p>
    </header>

   <nav>
        <a href="#">Home</a>
        <a href="#">Shop</a>
        <a href="https://instagram.com/tripu__dubey" target="_blank">Instagram</a>
        <a href="mailto:tripudubey@gmail.com">Contact</a>
    </nav>

   <section class="container">
        <div class="card">
            <img src="https://i.ibb.co/LnDPvjM/red-dress.jpg" alt="Red Dress">
            <h3>Elegant Red Gown</h3>
            <p>Flowy, stylish, and perfect for parties.</p>
            <a href="https://instagram.com/tripu__dubey" target="_blank" class="btn">Shop Now</a>
        </div>
        <div class="card">
            <img src="https://i.ibb.co/BGPkmtG/black-dress.jpg" alt="Black Dress">
            <h3>Classic Black Dress</h3>
            <p>Simple yet glamorous for any event.</p>
            <a href="https://instagram.com/tripu__dubey" target="_blank" class="btn">Shop Now</a>
        </div>
        <div class="card">
            <img src="https://i.ibb.co/Wg8pwyc/blue-dress.jpg" alt="Blue Dress">
            <h3>Royal Blue Outfit</h3>
            <p>Graceful look with designer touch.</p>
            <a href="https://instagram.com/tripu__dubey" target="_blank" class="btn">Shop Now</a>
        </div>
    </section>

  <footer>
        <p>Follow me on <a href="https://instagram.com/tripu__dubey" target="_blank">@tripu__dubey</a> | Email: <a href="mailto:tripudubey@gmail.com">tripudubey@gmail.com</a></p>
    </footer>

</body>
</html>
