<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta content="width=device-width, initial-scale=1" name="viewport" />
  <title>JL Computer Parts</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link
    href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css"
    rel="stylesheet"
  />
  <link
    href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap"
    rel="stylesheet"
  />
  <style>
    body {
      font-family: "Inter", sans-serif;
    }
    @keyframes fadeInLeft {
      from {
        opacity: 0;
        transform: translateX(-50px);
      }
      to {
        opacity: 1;
        transform: translateX(0);
      }
    }
    @keyframes fadeInRight {
      from {
        opacity: 0;
        transform: translateX(50px);
      }
      to {
        opacity: 1;
        transform: translateX(0);
      }
    }
    .animate-fadeInLeft {
      animation-name: fadeInLeft;
      animation-fill-mode: forwards;
    }
    .animate-fadeInRight {
      animation-name: fadeInRight;
      animation-fill-mode: forwards;
    }
  </style>
</head>
<body class="bg-gray-50 text-slate-900">
  <!-- Navigation Bar -->
  <header
    class="sticky top-0 z-50 bg-white shadow-md transition-all duration-300"
    id="navbar"
  >
    <div
      class="container mx-auto max-w-7xl flex flex-wrap items-center justify-between py-5 px-5 md:px-8"
    >
      <a class="flex items-center gap-3" href="#">
        <span class="text-2xl font-extrabold text-violet-600 select-none">JL Computer Parts</span>
      </a>
      <nav class="hidden md:flex space-x-10 font-medium text-slate-800">
        <a
          class="flex items-center gap-2 hover:text-violet-600 transition-colors duration-300"
          href="#"
          ><i class="fas fa-home text-base"></i> Home</a
        >
        <a
          class="flex items-center gap-2 hover:text-violet-600 transition-colors duration-300"
          href="#products"
          ><i class="fas fa-microchip text-base"></i> Products</a
        >
        <a
          class="flex items-center gap-2 hover:text-violet-600 transition-colors duration-300"
          href="#contact"
          ><i class="fas fa-phone-alt text-base"></i> Contact</a
        >
      </nav>
      <div class="flex items-center space-x-6 text-slate-800 text-lg relative">
        <button
          aria-label="Open search"
          id="search-open-btn"
          class="hover:text-violet-600 transition-colors duration-300 focus:outline-none"
          title="Search"
        >
          <i class="fas fa-search"></i>
        </button>
        <a
          aria-label="User Account"
          class="hover:text-violet-600 transition-colors duration-300"
          href="#"
          ><i class="fas fa-user"></i
        ></a>
        <button
          aria-label="Shopping Cart"
          class="relative hover:text-violet-500 transition-colors duration-300 focus:outline-none"
          id="cart-icon"
          title="Cart"
        >
          <i class="fas fa-shopping-cart"></i>
          <span
            class="absolute -top-2 -right-2 bg-orange-500 text-white rounded-full w-5 h-5 flex items-center justify-center text-xs font-bold"
            id="cart-count"
            >0</span
          >
        </button>
        <!-- Cart dropdown -->
        <div
          id="cart-dropdown"
          class="hidden absolute right-0 mt-12 w-96 bg-white border border-gray-300 rounded-md shadow-lg z-50"
          role="region"
          aria-label="Shopping cart"
        >
          <div
            class="p-4 max-h-96 overflow-y-auto"
            id="cart-items-container"
            tabindex="0"
          >
            <p class="text-center text-gray-500">Your cart is empty.</p>
          </div>
          <div
            class="border-t border-gray-300 p-4 flex justify-between items-center font-semibold"
            id="cart-total-container"
          >
            <span>Total:</span>
            <span id="cart-total-price">$0.00</span>
          </div>
          <div class="p-4 text-center">
            <button
              id="checkout-button"
              class="bg-orange-500 hover:bg-orange-600 text-white font-semibold rounded-full px-6 py-2 shadow-lg transition-transform transform hover:-translate-y-1 disabled:opacity-50 disabled:cursor-not-allowed"
              disabled
            >
              Checkout
            </button>
          </div>
        </div>
        <!-- Search dropdown -->
        <div
          id="search-dropdown"
          class="hidden absolute right-0 mt-12 w-96 bg-white border border-gray-300 rounded-md shadow-lg z-50 p-4"
          role="search"
        >
          <input
            type="search"
            id="search-input"
            aria-label="Search products"
            placeholder="Search products..."
            class="w-full border border-gray-300 rounded-md px-4 py-2 focus:outline-none focus:ring-2 focus:ring-violet-600"
            autocomplete="off"
          />
          <ul
            id="search-results"
            class="mt-2 max-h-64 overflow-y-auto divide-y divide-gray-200"
          ></ul>
          <p
            id="search-no-results"
            class="hidden mt-2 text-center text-gray-500"
          >
            No products found.
          </p>
        </div>
      </div>
      <!-- Mobile menu button -->
      <button
        aria-label="Toggle menu"
        class="md:hidden text-slate-800 hover:text-violet-600 transition-colors duration-300"
        id="mobile-menu-button"
      >
        <i class="fas fa-bars text-2xl"></i>
      </button>
    </div>
    <!-- Mobile menu -->
    <nav
      aria-label="Mobile Navigation"
      class="hidden md:hidden bg-white border-t border-gray-200"
      id="mobile-menu"
    >
      <ul class="flex flex-col space-y-3 py-4 px-5 font-medium text-slate-800">
        <li>
          <a
            class="flex items-center gap-3 hover:text-violet-600 transition-colors duration-300"
            href="#home"
            ><i class="fas fa-home text-base"></i> Home</a>
        </li>
        <li>
          <a
            class="flex items-center gap-3 hover:text-violet-600 transition-colors duration-300"
            href="#products"
            ><i class="fas fa-microchip text-base"></i> Products</a >
        </li>
        <li>
          <a
            class="flex items-center gap-3 hover:text-violet-600 transition-colors duration-300"
            href="#contact"
            ><i class="fas fa-phone-alt text-base"></i> Contact</a>
        </li>
      </ul>
    </nav>
  </header>

  <!-- Hero Section -->
  <main class="container mx-auto max-w-7xl px-5 md:px-8 mt-12">
    <section
      aria-label="Hero section with promotional content"
      class="flex flex-col-reverse md:flex-row items-center justify-between gap-10 md:gap-20 min-h-[80vh]"
    >
      <div
        class="md:flex-1 text-center md:text-left animate-fadeInLeft"
        style="animation-duration: 1s"
      >
        <h1
          class="text-4xl md:text-5xl font-extrabold leading-tight bg-gradient-to-r from-violet-600 to-yellow-500 text-transparent bg-clip-text mb-6">
          Find The Best Computer Parts Collection
        </h1>
        <p class="text-lg text-slate-700 max-w-lg mx-auto md:mx-0 mb-8">
          Up to 50% Off Sale<br>Don't Miss Out!!<br> Check Out Now!
        </p>
        <div
          class="flex flex-col sm:flex-row justify-center md:justify-start gap-4 max-w-xs mx-auto md:mx-0">
          <a
            class="inline-block bg-orange-500 hover:bg-orange-600 text-white font-semibold rounded-full px-8 py-4 shadow-lg transition-transform transform hover:-translate-y-1"
            href="#products"
            >Shop Now</a>
        </div>
      </div>
      <div
        class="md:flex-1 animate-fadeInRight max-w-lg w-full"
        style="animation-duration: 1s">
        <img
          alt="Premium gaming PC with RGB lighting, high-end components, and sleek black case"
          class="rounded-lg shadow-2xl w-full object-cover hover:rotate-0 rotate-[-10deg] transition-transform duration-500"
          decoding="async"
          height="400"
          loading="lazy"
          src="https://storage.googleapis.com/a1aa/image/8f0c9734-9a56-400d-77b0-edbacddceda0.jpg"
          width="600"
        />
      </div>
    </section>

    <!-- Products Section -->
    <section
      aria-label="Featured products section with premium computer parts"
      class="mt-20"
      id="products">
      <h2 class="text-3xl font-extrabold text-center text-violet-600 mb-12">
        This All Product is Discounted 50% Off!.
      </h2>
      <div
        class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-8"
        id="products-grid">
        <!-- Products will be dynamically inserted here -->
      </div>
    </section>
          </div>
        </article>
      </div>
    </section>

    <!-- Contact Section -->
    <section
      aria-label="Contact section with form and company information"
      class="mt-24 mb-20"
      id="contact"
    >
      <h2 class="text-3xl font-extrabold text-center text-violet-600 mb-12">
        Contact Us:</h2>
      <div
        class="max-w-4xl mx-auto bg-white rounded-lg shadow-md p-8 grid grid-cols-1 md:grid-cols-2 gap-10">
        <form
          aria-label="Contact form for customer inquiries"
          class="flex flex-col space-y-6"
          novalidate
          id="contact-form">
          <div>
            <label
              class="block mb-2 font-semibold text-slate-700"
              for="name"
              >Name</label>
            <input
              class="w-full border border-gray-300 rounded-md px-4 py-3 focus:outline-none focus:ring-2 focus:ring-violet-600"
              id="name"
              name="name"
              placeholder="Your Full Name"
              required
              type="text"
            />
          </div>
          <div>
            <label
              class="block mb-2 font-semibold text-slate-700"
              for="email"
              >Email</label
            >
            <input
              class="w-full border border-gray-300 rounded-md px-4 py-3 focus:outline-none focus:ring-2 focus:ring-violet-600"
              id="email"
              name="email"
              placeholder="Email Address"
              required
              type="email"
            />
          </div>
          <div>
            <label
              class="block mb-2 font-semibold text-slate-700"
              for="message"
              >Message</label
            >
            <textarea
              class="w-full border border-gray-300 rounded-md px-4 py-3 resize-none focus:outline-none focus:ring-2 focus:ring-violet-600"
              id="message"
              name="message"
              placeholder="Write your message here..."
              required
              rows="5"
            ></textarea>
          </div>
          <button
            class="bg-orange-500 hover:bg-orange-600 text-white font-semibold rounded-full px-8 py-4 shadow-lg transition-transform transform hover:-translate-y-1"
            type="submit">
            Send Message
          </button>
          <p
            id="contact-success"
            class="hidden text-green-600 font-semibold mt-2"
            role="alert">
            Message sent successfully!
          </p>
          <p
            id="contact-error"
            class="hidden text-red-600 font-semibold mt-2"
            role="alert">
            Please fill all fields correctly.
          </p>
        </form>
        <div class="text-slate-700 flex flex-col justify-center space-y-6">
          <div>
            <h3 class="text-xl font-semibold mb-2">Our Address</h3>
            <p>Damong Maliit RoadNagkaisang Nayon,Novaliches.QuezonCity
            </p>
          </div>
          <div>
            <h3 class="text-xl font-semibold mb-2">Phone</h3>
            <p>0945-1004-760</p>
          </div>
          <div>
            <h3 class="text-xl font-semibold mb-2">Email</h3>
            <p>insaneee.lloyd@gmail.com</p>
          </div>
          <div>
            <h3 class="text-xl font-semibold mb-2">Business Hours</h3>
            <p>Mon - Fri: 10:30 AM - 7:00 PM</p>
            <p>Sat - Sun: Closed</p>
          </div>
        </div>
      </div>
    </section>
  </main>

  <!-- Checkout Modal -->
  <div
    id="checkout-modal"
    class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-60 hidden"
    role="dialog"
    aria-modal="true"
    aria-labelledby="checkout-modal-title"
  >
    <div
      class="bg-white rounded-lg max-w-lg w-full p-6 relative shadow-lg max-h-[90vh] overflow-y-auto"
    >
      <h2
        id="checkout-modal-title"
        class="text-2xl font-extrabold mb-4 text-center text-violet-600">
        Checkout
      </h2>
      <form id="checkout-form" class="space-y-6">
        <div>
          <label
            for="fullName"
            class="block mb-2 font-semibold text-slate-700"
            >Full Name</label
          >
          <input
            type="text"
            id="fullName"
            name="fullName"
            required
            class="w-full border border-gray-300 rounded-md px-4 py-3 focus:outline-none focus:ring-2 focus:ring-blue-600"
            placeholder="Your Full Name"
          />
        </div>
        <div>
          <label
            for="emailCheckout"
            class="block mb-2 font-semibold text-slate-700"
            >Email</label
          >
          <input
            type="email"
            id="emailCheckout"
            name="emailCheckout"
            required
            class="w-full border border-gray-300 rounded-md px-4 py-3 focus:outline-none focus:ring-2 focus:ring-blue-600"
            placeholder="Email Address"
          />
        </div>
        <div>
          <label
            for="address"
            class="block mb-2 font-semibold text-slate-700"
            >Shipping Address</label
          >
          <textarea
            id="address"
            name="address"
            rows="3"
            required
            class="w-full border border-gray-300 rounded-md px-4 py-3 resize-none focus:outline-none focus:ring-2 focus:ring-blue-600"
            placeholder="#House, City,ZIP code"
          ></textarea>
        </div>

        <!-- Payment Method Selection -->
        <fieldset class="border border-gray-300 rounded-md p-4">
          <legend class="text-lg font-semibold text-slate-700 mb-4">Payment Method</legend>
          <div class="flex flex-col space-y-3">
            </label>
            <label class="flex items-center gap-2 cursor-pointer">
              <input
                type="radio"
                name="paymentMethod"
                value="gcash"
                class="form-radio text-blue-600"
              />
              <span>GCash</span>
            </label>
            <label class="flex items-center gap-2 cursor-pointer">
              <input
                type="radio"
                name="paymentMethod"
                value="cod"
                class="form-radio text-blue-600"
              />
              <span>Cash on Delivery (COD)</span>
            </label>
          </div>
        </fieldset>

        <!-- Card Payment Fields -->
        <div id="card-payment-fields" class="space-y-4">
          <div>
            <label
              for="cardNumber"
              class="block mb-2 font-semibold text-slate-700"
              >Card Number</label
            >
            <input
              type="text"
              id="cardNumber"
              name="cardNumber"
              maxlength="19"
              placeholder="1234 5678 9012 3456"
              class="w-full border border-gray-300 rounded-md px-4 py-3 focus:outline-none focus:ring-2 focus:ring-blue-600"
              inputmode="numeric"
              pattern="\d{4} \d{4} \d{4} \d{4}"
            />
          </div>
          <div class="flex gap-4">
            <div class="flex-1">
              <label
                for="expiry"
                class="block mb-2 font-semibold text-slate-700"
                >Expiry Date</label
              >
              <input
                type="text"
                id="expiry"
                name="expiry"
                maxlength="5"
                placeholder="MM/YY"
                class="w-full border border-gray-300 rounded-md px-4 py-3 focus:outline-none focus:ring-2 focus:ring-blue-600"
                pattern="(0[1-9]|1[0-2])\/\d{2}"
              />
            </div>
            <div class="flex-1">
              <label
                for="cvv"
                class="block mb-2 font-semibold text-slate-700"
                >CVV</label
              >
              <input
                type="text"
                id="cvv"
                name="cvv"
                maxlength="4"
                placeholder="123"
                class="w-full border border-gray-300 rounded-md px-4 py-3 focus:outline-none focus:ring-2 focus:ring-blue-600"
                inputmode="numeric"
                pattern="\d{3,4}"
              />
            </div>
          </div>
        </div>

        <div class="text-center">
          <button
            type="submit"
            id="pay-now-button"
            class="bg-orange-500 hover:bg-orange-600 text-white font-semibold rounded-full px-8 py-4 shadow-lg transition-transform transform hover:-translate-y-1"
          >
            Pay Now
          </button>
        </div>
        <p
          id="checkout-success"
          class="hidden text-green-600 font-semibold mt-2 text-center"
          role="alert">
          Payment successful! Thank you for your purchase.
        </p>
        <p
          id="checkout-error"
          class="hidden text-red-600 font-semibold mt-2 text-center"
          role="alert">
          Please fill all fields correctly.
        </p>
      </form>
      <button
        id="checkout-close"
        aria-label="Close checkout modal"
        class="absolute top-3 right-3 text-gray-600 hover:text-gray-900 focus:outline-none"
      >
        <i class="fas fa-times text-2xl"></i>
      </button>
    </div>
  </div>
  <!-- Footer -->
  <footer class="bg-slate-900 text-slate-300 py-16">
    <div class="container mx-auto max-w-7xl px-5 md:px-8">
      <div
        class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 gap-12 border-b border-slate-700 pb-12"
      >
        <div>
          <h3 class="text-xl font-extrabold text-violet-500 mb-6">JL Computer Parts</h3>
          <p class="mb-6 max-w-xs">
            One of the affordable computer components and accessories.
          </p>
          <div class="flex space-x-5">
            <a
              aria-label="Facebook"
              class="w-10 h-10 flex items-center justify-center rounded-full bg-slate-700 hover:bg-violet-500 transition-colors"
              href="https://www.facebook.com/share/1FHV6WdkG5/"
              ><i class="fab fa-facebook-f text-white"></i></a>
            <a
              aria-label="YouTube"
              class="w-10 h-10 flex items-center justify-center rounded-full bg-slate-700 hover:bg-violet-500 transition-colors"
              href="#"
              ><i class="fab fa-youtube text-white"></i
            ></a>
          </div>
        </div>
        <div>
          <h3 class="text-xl font-extrabold text-violet-500 mb-6">Shop</h3>
          <ul class="space-y-3 text-slate-400">
            <li>
              <a
                class="hover:text-violet-500 transition-colors duration-300"
                href="#products"
                >Corsair RM850x 850W</a
              >
            </li>
            <li>
              <a
                class="hover:text-violet-500 transition-colors duration-300"
                href="#products"
                >NZXT H510 Elite</a
              >
            </li>
            <li>
              <a
                class="hover:text-violet-500 transition-colors duration-300"
                href="#products"
                >NZXT H510 Elite</a>
            </li>
          </ul>
        </div>
        <div>
          <h3 class="text-xl font-extrabold text-violet-500 mb-6">Support</h3>
          <ul class="space-y-3 text-slate-400">
            <li>
              <a
                class="hover:text-violet-500 transition-colors duration-300"
                href="#contact"
                >Contact Us</a
              >
            </li>
          </ul>
        </div>
        <div>
          <h3 class="text-xl font-extrabold text-violet-500 mb-6">Newsletter</h3>
          <p class="mb-6 text-slate-400">
            Subscribe to get updates on new products and special offers.
          </p>
          <form
            aria-label="Newsletter subscription form"
            class="flex flex-col space-y-4"
          >
            <input
              class="px-4 py-3 rounded-md border border-slate-700 bg-slate-800 text-slate-200 placeholder-slate-500 focus:outline-none focus:ring-2 focus:ring-violet-500"
              placeholder="Your email address"
              required
              type="email"
            />
            <button
              class="bg-orange-500 hover:bg-orange-600 text-white font-semibold rounded-full px-6 py-3 shadow-lg transition-transform transform hover:-translate-y-1"
              type="submit"
            >
              Subscribe
            </button>
          </form>
        </div>
      </div>
      <p class="text-center text-slate-500 mt-12 text-sm select-none">
        © 2025 JL Computer Parts
      </p>
    </div>
  </footer>

  <script>
    // Sticky Navigation on Scroll
    const navbar = document.getElementById("navbar");
    window.addEventListener("scroll", () => {
      if (window.scrollY > 50) {
        navbar.classList.add("shadow-lg", "py-3");
        navbar.classList.remove("py-5");
      } else {
        navbar.classList.remove("shadow-lg", "py-3");
        navbar.classList.add("py-5");
      }
    });

    // Mobile menu toggle
    const mobileMenuButton = document.getElementById("mobile-menu-button");
    const mobileMenu = document.getElementById("mobile-menu");

    mobileMenuButton.addEventListener("click", () => {
      mobileMenu.classList.toggle("hidden");
    });

    // Smooth scrolling for anchor links
    document.querySelectorAll('a[href^="#"]').forEach((anchor) => {
      anchor.addEventListener("click", function (e) {
        e.preventDefault();
        const target = document.querySelector(this.getAttribute("href"));
        if (target) {
          target.scrollIntoView({
            behavior: "smooth",
          });
          if (!mobileMenu.classList.contains("hidden")) {
            mobileMenu.classList.add("hidden");
          }
        }
      });
    });

    // Product data array
    const productsData = [
      {
        id: "corsair-rm850x-850w",
        name: "Corsair RM850x 850W",
        price: 159.99,
        image:
          "https://storage.googleapis.com/a1aa/image/54d6e0d2-c3b6-4a46-30e1-8b031d571dc3.jpg",
        description:
          "Fully modular 80+ Gold certified PSU with quiet operation and RGB fan.",
      },
      {
        id: "nzxt-h510-elite",
        name: "NZXT H510 Elite",
        price: 199.99,
        image:
          "https://storage.googleapis.com/a1aa/image/b1064027-fd37-4a48-f7cf-9a4624ec73d5.jpg",
        description:
          "Sleek mid-tower case with tempered glass, RGB lighting, and excellent airflow.",
      },
      {
        id: "noctua-nh-d15-chromax",
        name: "Noctua NH-D15 Chromax",
        price: 99.99,
        image:
          "https://storage.googleapis.com/a1aa/image/ae556a30-ac62-4496-8578-5e7e0af3f9c3.jpg",
        description:
          "Premium air cooler with dual fans and excellent thermal performance.",
      },
    ];

    // Render products dynamically
    const productsGrid = document.getElementById("products-grid");
    function renderProducts(products) {
      productsGrid.innerHTML = "";
      products.forEach((product) => {
        const article = document.createElement("article");
        article.setAttribute("aria-label", `Product: ${product.name}`);
        article.className =
          "bg-white rounded-lg shadow-md p-5 flex flex-col";
        article.dataset.id = product.id;
        article.dataset.name = product.name;
        article.dataset.price = product.price;
        article.dataset.image = product.image;

        article.innerHTML = `
          <img
            alt="${product.description}"
            class="rounded-md mb-4 object-cover w-full h-48"
            decoding="async"
            height="300"
            loading="lazy"
            src="${product.image}"
            width="400"
          />
          <h3 class="text-xl font-semibold mb-2">${product.name}</h3>
          <p class="text-slate-600 flex-grow">${product.description}</p>
          <div class="mt-4 flex items-center justify-between">
            <span class="text-violet-500 font-bold text-lg">₱${product.price.toFixed(
              2
            )}</span>
            <button
              aria-label="Add${product.name} to cart"
              class="add-to-cart bg-blue-600 hover:bg-blue-700 text-white px-4 py-2 rounded-full font-semibold transition"
              type="button"
            >
              Add to Cart
            </button>
          </div>
        `;
        productsGrid.appendChild(article);
      });
    }
    renderProducts(productsData);

    // Cart functionality with localStorage persistence
    const cartIcon = document.getElementById("cart-icon");
    const cartDropdown = document.getElementById("cart-dropdown");
    const cartItemsContainer = document.getElementById("cart-items-container");
    const cartCount = document.getElementById("cart-count");
    const cartTotalPrice = document.getElementById("cart-total-price");
    const checkoutButton = document.getElementById("checkout-button");

    // Load cart from localStorage or initialize empty
    let cart = JSON.parse(localStorage.getItem("JL Computer PartsCart")) || {};

    // Update cart UI
    function updateCartUI() {
      const items = Object.values(cart);
      cartCount.textContent = items.reduce((acc, item) => acc + item.quantity, 0);
      if (items.length === 0) {
        cartItemsContainer.innerHTML =
          '<p class="text-center text-gray-500">Your cart is empty.</p>';
        cartTotalPrice.textContent = "₱0.00";
        checkoutButton.disabled = true;
        return;
      }
      checkoutButton.disabled = false;
      cartItemsContainer.innerHTML = "";
      let total = 0;
      items.forEach((item) => {
        total += item.price * item.quantity;
        const itemEl = document.createElement("div");
        itemEl.className =
          "flex items-center gap-3 border-b border-gray-200 py-3 last:border-b-0";
        itemEl.innerHTML = `
          <img src="${item.image}" alt="${item.name} product image" class="w-16 h-16 object-cover rounded" />
          <div class="flex-1">
            <h4 class="font-semibold text-slate-900">${item.name}</h4>
            <p class="text-sm text-slate-600">₱${item.price.toFixed(2)}</p>
            <div class="flex items-center gap-2 mt-1">
              <button aria-label="Decrease quantity of ${item.name}" class="quantity-btn px-2 py-0.5 bg-gray-200 rounded text-lg font-bold" data-id="${item.id}" data-action="decrease">−</button>
              <span class="text-sm font-semibold">${item.quantity}</span>
              <button aria-label="Increase quantity of ₱{item.name}" class="quantity-btn px-2 py-0.5 bg-gray-200 rounded text-lg font-bold" data-id="${item.id}" data-action="increase">+</button>
            </div>
          </div>
          <button aria-label="Remove ${item.name} from cart" class="remove-btn text-red-600 hover:text-red-800 text-xl font-bold" data-id="${item.id}">&times;</button>
        `;
        cartItemsContainer.appendChild(itemEl);
      });
      cartTotalPrice.textContent = `₱${total.toFixed(2)}`;
    }
    // Save cart to localStorage
    function saveCart() {
      localStorage.setItem("JL Computer PartsCart", JSON.stringify(cart));
    }
    // Add product to cart
    function addToCart(product) {
      if (cart[product.id]) {
        cart[product.id].quantity += 1;
      } else {
        cart[product.id] = { ...product, quantity: 1 };
      }
      saveCart();
      updateCartUI();
    }
    // Remove product from cart
    function removeFromCart(productId) {
      delete cart[productId];
      saveCart();
      updateCartUI();
    }
    // Change quantity of product in cart
    function changeQuantity(productId, delta) {
      if (!cart[productId]) return;
      cart[productId].quantity += delta;
      if (cart[productId].quantity <= 0) {
        removeFromCart(productId);
      } else {
        saveCart();
        updateCartUI();
      }
    }
    // Event delegation for quantity buttons and remove buttons inside cart dropdown
    cartItemsContainer.addEventListener("click", (e) => {
      if (e.target.classList.contains("quantity-btn")) {
        const id = e.target.getAttribute("data-id");
        const action = e.target.getAttribute("data-action");
        if (action === "increase") {
          changeQuantity(id, 1);
        } else if (action === "decrease") {
          changeQuantity(id, -1);
        }
      } else if (e.target.classList.contains("remove-btn")) {
        const id = e.target.getAttribute("data-id");
        removeFromCart(id);
      }
    });

    // Add to cart buttons (delegated)
    productsGrid.addEventListener("click", (e) => {
      if (e.target.classList.contains("add-to-cart")) {
        const article = e.target.closest("article");
        if (!article) return;
        const product = {
          id: article.getAttribute("data-id"),
          name: article.getAttribute("data-name"),
          price: parseFloat(article.getAttribute("data-price")),
          image: article.getAttribute("data-image"),
        };
        addToCart(product);
        // Show cart dropdown briefly
        cartDropdown.classList.remove("hidden");
        setTimeout(() => {
          cartDropdown.classList.add("hidden");
        }, 4000);
      }
    });

    // Toggle cart dropdown on cart icon click
    cartIcon.addEventListener("click", (e) => {
      e.preventDefault();
      cartDropdown.classList.toggle("hidden");
      searchDropdown.classList.add("hidden");
    });

    // Close cart dropdown if clicked outside
    document.addEventListener("click", (e) => {
      if (
        !cartDropdown.contains(e.target) &&
        !cartIcon.contains(e.target) &&
        !searchDropdown.contains(e.target) &&
        !searchOpenBtn.contains(e.target)
      ) {
        cartDropdown.classList.add("hidden");
        searchDropdown.classList.add("hidden");
      }
    });

    // Checkout modal elements
    const checkoutModal = document.getElementById("checkout-modal");
    const checkoutCloseBtn = document.getElementById("checkout-close");
    const checkoutForm = document.getElementById("checkout-form");
    const checkoutSuccess = document.getElementById("checkout-success");
    const checkoutError = document.getElementById("checkout-error");
    const payNowButton = document.getElementById("pay-now-button");
    const cardPaymentFields = document.getElementById("card-payment-fields");

    // Open checkout modal on checkout button click
    checkoutButton.addEventListener("click", () => {
      if (Object.keys(cart).length === 0) return;
      checkoutModal.classList.remove("hidden");
      cartDropdown.classList.add("hidden");
      checkoutSuccess.classList.add("hidden");
      checkoutError.classList.add("hidden");
      checkoutForm.reset();
      updatePaymentFieldsVisibility();
    });

    // Close checkout modal
    checkoutCloseBtn.addEventListener("click", () => {
      checkoutModal.classList.add("hidden");
    });

    // Close modal on outside click
    checkoutModal.addEventListener("click", (e) => {
      if (e.target === checkoutModal) {
        checkoutModal.classList.add("hidden");
      }
    });

    // Payment method radio buttons
    const paymentMethodRadios = checkoutForm.elements["paymentMethod"];

    function updatePaymentFieldsVisibility() {
      const selectedMethod = checkoutForm.paymentMethod.value;
      if (selectedMethod === "card") {
        cardPaymentFields.classList.remove("hidden");
        // Make card fields required
        checkoutForm.cardNumber.required = true;
        checkoutForm.expiry.required = true;
        checkoutForm.cvv.required = true;
      } else {
        cardPaymentFields.classList.add("hidden");
        // Remove required from card fields
        checkoutForm.cardNumber.required = false;
        checkoutForm.expiry.required = false;
        checkoutForm.cvv.required = false;
      }
    }

    // Listen for payment method changes
    Array.from(paymentMethodRadios).forEach((radio) => {
      radio.addEventListener("change", updatePaymentFieldsVisibility);
    });

    // Checkout form submission (mock payment)
    checkoutForm.addEventListener("submit", (e) => {
      e.preventDefault();
      checkoutSuccess.classList.add("hidden");
      checkoutError.classList.add("hidden");

      // Simple validation
      const fullName = checkoutForm.fullName.value.trim();
      const email = checkoutForm.emailCheckout.value.trim();
      const address = checkoutForm.address.value.trim();
      const paymentMethod = checkoutForm.paymentMethod.value;

      const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;

      if (!fullName || !emailRegex.test(email) || !address) {
        checkoutError.classList.remove("hidden");
        return;
      }

      if (paymentMethod === "card") {
        const cardNumber = checkoutForm.cardNumber.value.trim();
        const expiry = checkoutForm.expiry.value.trim();
        const cvv = checkoutForm.cvv.value.trim();

        const cardNumberRegex = /^\d{4} \d{4} \d{4} \d{4}$/;
        const expiryRegex = /^(0[1-9]|1[0-2])\/\d{2}$/;
        const cvvRegex = /^\d{3,4}$/;

        if (
          !cardNumberRegex.test(cardNumber) ||
          !expiryRegex.test(expiry) ||
          !cvvRegex.test(cvv)
        ) {
          checkoutError.classList.remove("hidden");
          return;
        }
      }

      // Simulate payment processing delay
      payNowButton.disabled = true;
      payNowButton.textContent = "Processing...";

      setTimeout(() => {
        checkoutSuccess.classList.remove("hidden");
        payNowButton.disabled = false;
        payNowButton.textContent = "Pay Now";
        // Clear cart
        cart = {};
        saveCart();
        updateCartUI();
        // Close modal after delay
        setTimeout(() => {
          checkoutModal.classList.add("hidden");
        }, 3000);
      }, 2000);
    });

    // Search functionality
    const searchOpenBtn = document.getElementById("search-open-btn");
    const searchDropdown = document.getElementById("search-dropdown");
    const searchInput = document.getElementById("search-input");
    const searchResults = document.getElementById("search-results");
    const searchNoResults = document.getElementById("search-no-results");

    searchOpenBtn.addEventListener("click", () => {
      searchDropdown.classList.toggle("hidden");
      cartDropdown.classList.add("hidden");
      if (!searchDropdown.classList.contains("hidden")) {
        searchInput.focus();
      }
    });

    // Close search dropdown on outside click handled in document click listener above

    // Filter products on search input
    searchInput.addEventListener("input", () => {
      const query = searchInput.value.trim().toLowerCase();
      if (!query) {
        searchResults.innerHTML = "";
        searchNoResults.classList.add("hidden");
        return;
      }
      const filtered = productsData.filter((p) =>
        p.name.toLowerCase().includes(query)
      );
      if (filtered.length === 0) {
        searchResults.innerHTML = "";
        searchNoResults.classList.remove("hidden");
        return;
      }
      searchNoResults.classList.add("hidden");
      searchResults.innerHTML = "";
      filtered.forEach((product) => {
        const li = document.createElement("li");
        li.className =
          "flex items-center gap-3 py-2 cursor-pointer hover:bg-gray-100 rounded px-2";
        li.tabIndex = 0;
        li.innerHTML = `
          <img src="${product.image}" alt="${product.name} product image" class="w-12 h-12 object-cover rounded" />
          <div class="flex-1">
            <p class="font-semibold text-slate-900">${product.name}</p>
            <p class="text-sm text-orange-500">₱${product.price.toFixed(2)}</p>
          </div>
          <button class="search-add-to-cart bg-blue-600 hover:bg-blue-700 text-white px-3 py-1 rounded font-semibold text-sm" aria-label="Add ${product.name} to cart">Add</button>
        `;
        // Clicking the li (except button) scrolls to product
        li.addEventListener("click", (e) => {
          if (e.target.classList.contains("search-add-to-cart")) return;
          const productEl = document.querySelector(
            `article[data-id="${product.id}"]`
          );
          if (productEl) {
            productEl.scrollIntoView({ behavior: "smooth", block: "center" });
            searchDropdown.classList.add("hidden");
          }
        });
        // Keyboard accessibility for li
        li.addEventListener("keydown", (e) => {
          if (e.key === "Enter" || e.key === " ") {
            e.preventDefault();
            li.click();
          }
        });
        // Add to cart button inside search results
        li.querySelector(".search-add-to-cart").addEventListener("click", (e) => {
          e.stopPropagation();
          addToCart(product);
          searchDropdown.classList.add("hidden");
          // Show cart dropdown briefly
          cartDropdown.classList.remove("hidden");
          setTimeout(() => {
            cartDropdown.classList.add("hidden");
          }, 4000);
        });
        searchResults.appendChild(li);
      });
    });

    // Contact form submission (mock)
    const contactForm = document.getElementById("contact-form");
    const contactSuccess = document.getElementById("contact-success");
    const contactError = document.getElementById("contact-error");

    contactForm.addEventListener("submit", (e) => {
      e.preventDefault();
      contactSuccess.classList.add("hidden");
      contactError.classList.add("hidden");

      const name = contactForm.name.value.trim();
      const email = contactForm.email.value.trim();
      const message = contactForm.message.value.trim();

      const emailRegex =
        /^[^\s@]+@[^\s@]+\.[^\s@]+$/;

      if (!name || !emailRegex.test(email) || !message) {
        contactError.classList.remove("hidden");
        return;
      }

      // Simulate sending message
      contactForm.querySelector("button[type=submit]").disabled = true;
      contactForm.querySelector("button[type=submit]").textContent = "Sending...";

      setTimeout(() => {
        contactSuccess.classList.remove("hidden");
        contactForm.querySelector("button[type=submit]").disabled = false;
        contactForm.querySelector("button[type=submit]").textContent = "Send Message";
        contactForm.reset();
      }, 1500);
    });

    // Initialize cart UI on page load
    updateCartUI();
  </script>
</body>
</html>
