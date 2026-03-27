
real-estate-lead-system/
├── index.html
├── dashboard.html
├── styles.css
├── script.js
├── leads.js
├── .gitignore
└── README.md

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Real Estate Lead Management System</title>
    <link rel="stylesheet" href="styles.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
</head>
<body>
    <nav class="navbar">
        <div class="container">
            <div class="logo">
                <h1>🏠 RealEstate Leads</h1>
            </div>
            <div class="nav-links">
                <a href="index.html" class="active">Home</a>
                <a href="dashboard.html">Dashboard</a>
            </div>
        </div>
    </nav>

    <div class="hero">
        <div class="container">
            <h2>Find Your Perfect Property Match</h2>
            <p>Join thousands of buyers and sellers in our real estate network</p>
        </div>
    </div>

    <div class="container">
        <div class="registration-section">
            <div class="card buyer-card">
                <div class="card-header">
                    <div class="icon">🏠</div>
                    <h3>Looking to Buy?</h3>
                    <p>Register to find your dream property</p>
                </div>
                <form id="buyerForm">
                    <div class="form-group">
                        <label for="buyerName">Full Name *</label>
                        <input type="text" id="buyerName" required>
                    </div>
                    <div class="form-group">
                        <label for="buyerEmail">Email Address *</label>
                        <input type="email" id="buyerEmail" required>
                    </div>
                    <div class="form-group">
                        <label for="buyerPhone">Phone Number *</label>
                        <input type="tel" id="buyerPhone" required>
                    </div>
                    <div class="form-group">
                        <label for="propertyType">Property Type Interested In</label>
                        <select id="propertyType">
                            <option value="house">House</option>
                            <option value="apartment">Apartment</option>
                            <option value="condo">Condo</option>
                            <option value="land">Land</option>
                            <option value="commercial">Commercial</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="budget">Budget Range</label>
                        <select id="budget">
                            <option value="0-200k">$0 - $200,000</option>
                            <option value="200k-400k">$200,000 - $400,000</option>
                            <option value="400k-600k">$400,000 - $600,000</option>
                            <option value="600k-800k">$600,000 - $800,000</option>
                            <option value="800k+">$800,000+</option>
                        </select>
                    </div>
                    <button type="submit" class="btn btn-primary">Register as Buyer</button>
                </form>
            </div>

            <div class="card seller-card">
                <div class="card-header">
                    <div class="icon">💰</div>
                    <h3>Looking to Sell?</h3>
                    <p>List your property and find buyers</p>
                </div>
                <form id="sellerForm">
                    <div class="form-group">
                        <label for="sellerName">Full Name *</label>
                        <input type="text" id="sellerName" required>
                    </div>
                    <div class="form-group">
                        <label for="sellerEmail">Email Address *</label>
                        <input type="email" id="sellerEmail" required>
                    </div>
                    <div class="form-group">
                        <label for="sellerPhone">Phone Number *</label>
                        <input type="tel" id="sellerPhone" required>
                    </div>
                    <div class="form-group">
                        <label for="propertyAddress">Property Address *</label>
                        <input type="text" id="propertyAddress" required>
                    </div>
                    <div class="form-group">
                        <label for="askingPrice">Asking Price ($) *</label>
                        <input type="number" id="askingPrice" required>
                    </div>
                    <div class="form-group">
                        <label for="bedrooms">Bedrooms</label>
                        <input type="number" id="bedrooms" min="0">
                    </div>
                    <div class="form-group">
                        <label for="bathrooms">Bathrooms</label>
                        <input type="number" id="bathrooms" min="0" step="0.5">
                    </div>
                    <div class="form-group">
                        <label for="sqft">Square Footage</label>
                        <input type="number" id="sqft">
                    </div>
                    <button type="submit" class="btn btn-secondary">Register as Seller</button>
                </form>
            </div>
        </div>

        <div class="stats-section">
            <div class="stat-card">
                <h3 id="buyerCount">0</h3>
                <p>Active Buyers</p>
            </div>
            <div class="stat-card">
                <h3 id="sellerCount">0</h3>
                <p>Active Sellers</p>
            </div>
            <div class="stat-card">
                <h3 id="totalLeads">0</h3>
                <p>Total Leads</p>
            </div>
        </div>
    </div>

    <div class="toast" id="toast"></div>

    <script src="leads.js"></script>
    <script src="script.js"></script>
</body>
</html>
