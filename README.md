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
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard - Lead Management</title>
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
                <a href="index.html">Home</a>
                <a href="dashboard.html" class="active">Dashboard</a>
            </div>
        </div>
    </nav>

    <div class="container">
        <div class="dashboard-header">
            <h2>Lead Management Dashboard</h2>
            <div class="dashboard-actions">
                <button id="exportData" class="btn btn-outline">📊 Export Data</button>
                <button id="clearAllData" class="btn btn-danger">🗑️ Clear All Data</button>
            </div>
        </div>

        <div class="tabs">
            <button class="tab-btn active" data-tab="buyers">Buyers</button>
            <button class="tab-btn" data-tab="sellers">Sellers</button>
        </div>

        <div class="tab-content">
            <div id="buyersTab" class="tab-pane active">
                <div class="search-bar">
                    <input type="text" id="searchBuyers" placeholder="Search buyers by name or email...">
                </div>
                <div class="table-container">
                    <table id="buyersTable">
                        <thead>
                            <tr>
                                <th>Name</th>
                                <th>Email</th>
                                <th>Phone</th>
                                <th>Property Type</th>
                                <th>Budget</th>
                                <th>Date Registered</th>
                                <th>Actions</th>
                            </tr>
                        </thead>
                        <tbody id="buyersTableBody">
                        </tbody>
                    </table>
                </div>
            </div>

            <div id="sellersTab" class="tab-pane">
                <div class="search-bar">
                    <input type="text" id="searchSellers" placeholder="Search sellers by name, email, or address...">
                </div>
                <div class="table-container">
                    <table id="sellersTable">
                        <thead>
                            <tr>
                                <th>Name</th>
                                <th>Email</th>
                                <th>Phone</th>
                                <th>Property Address</th>
                                <th>Asking Price</th>
                                <th>Bed/Bath</th>
                                <th>Sq Ft</th>
                                <th>Date Registered</th>
                                <th>Actions</th>
                            </tr>
                        </thead>
                        <tbody id="sellersTableBody">
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>

    <div class="modal" id="detailsModal">
        <div class="modal-content">
            <span class="close">&times;</span>
            <div id="modalContent"></div>
        </div>
    </div>

    <div class="toast" id="toast"></div>

    <script src="leads.js"></script>
    <script src="script.js"></script>
</body>
</html>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Inter', sans-serif;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    min-height: 100vh;
    color: #333;
}

.container {
    max-width: 1400px;
    margin: 0 auto;
    padding: 0 20px;
}

/* Navigation */
.navbar {
    background: white;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    position: sticky;
    top: 0;
    z-index: 1000;
}

.navbar .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 20px;
}

.logo h1 {
    font-size: 1.5rem;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

.nav-links a {
    text-decoration: none;
    color: #666;
    margin-left: 2rem;
    font-weight: 500;
    transition: color 0.3s;
}

.nav-links a:hover,
.nav-links a.active {
    color: #667eea;
}

/* Hero Section */
.hero {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    text-align: center;
    padding: 4rem 0;
}

.hero h2 {
    font-size: 2.5rem;
    margin-bottom: 1rem;
}

.hero p {
    font-size: 1.2rem;
    opacity: 0.9;
}

/* Registration Section */
.registration-section {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
    gap: 2rem;
    margin: -3rem 0 3rem 0;
}

.card {
    background: white;
    border-radius: 15px;
    box-shadow: 0 10px 30px rgba(0,0,0,0.1);
    overflow: hidden;
    transition: transform 0.3s, box-shadow 0.3s;
}

.card:hover {
    transform: translateY(-5px);
    box-shadow: 0 15px 40px rgba(0,0,0,0.15);
}

.card-header {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    padding: 2rem;
    text-align: center;
}

.card-header .icon {
    font-size: 3rem;
    margin-bottom: 1rem;
}

.card-header h3 {
    font-size: 1.5rem;
    margin-bottom: 0.5rem;
}

form {
    padding: 2rem;
}

.form-group {
    margin-bottom: 1.5rem;
}

label {
    display: block;
    margin-bottom: 0.5rem;
    font-weight: 500;
    color: #555;
}

input, select {
    width: 100%;
    padding: 0.75rem;
    border: 2px solid #e0e0e0;
    border-radius: 8px;
    font-size: 1rem;
    transition: border-color 0.3s;
}

input:focus, select:focus {
    outline: none;
    border-color: #667eea;
}

.btn {
    width: 100%;
    padding: 0.875rem;
    border: none;
    border-radius: 8px;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s;
}

.btn-primary {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
}

.btn-primary:hover {
    transform: translateY(-2px);
    box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
}

.btn-secondary {
    background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
    color: white;
}

.btn-secondary:hover {
    transform: translateY(-2px);
    box-shadow: 0 5px 15px rgba(245, 87, 108, 0.4);
}

.btn-outline {
    background: transparent;
    border: 2px solid #667eea;
    color: #667eea;
}

.btn-outline:hover {
    background: #667eea;
    color: white;
}

.btn-danger {
    background: linear-gradient(135deg, #eb3349 0%, #f45c43 100%);
    color: white;
}

/* Stats Section */
.stats-section {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 1.5rem;
    margin: 3rem 0;
}

.stat-card {
    background: white;
    padding: 2rem;
    text-align: center;
    border-radius: 15px;
    box-shadow: 0 5px 15px rgba(0,0,0,0.1);
}

.stat-card h3 {
    font-size: 2.5rem;
    color: #667eea;
    margin-bottom: 0.5rem;
}

/* Dashboard */
.dashboard-header {
    background: white;
    padding: 2rem;
    border-radius: 15px;
    margin: 2rem 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 1rem;
}

.dashboard-actions {
    display: flex;
    gap: 1rem;
}

.dashboard-actions .btn {
    width: auto;
    padding: 0.75rem 1.5rem;
}

.tabs {
    display: flex;
    gap: 1rem;
    margin-bottom: 2rem;
}

.tab-btn {
    padding: 0.75rem 2rem;
    background: white;
    border: none;
    border-radius: 8px;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s;
}

.tab-btn.active {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
}

.tab-pane {
    display: none;
}

.tab-pane.active {
    display: block;
}

.search-bar {
    margin-bottom: 1.5rem;
}

.search-bar input {
    width: 100%;
    max-width: 400px;
}

.table-container {
    background: white;
    border-radius: 15px;
    overflow-x: auto;
    box-shadow: 0 5px 15px rgba(0,0,0,0.1);
}

table {
    width: 100%;
    border-collapse: collapse;
}

thead {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
}

th, td {
    padding: 1rem;
    text-align: left;
    border-bottom: 1px solid #e0e0e0;
}

tbody tr:hover {
    background: #f5f5f5;
}

.action-btn {
    padding: 0.5rem 1rem;
    margin: 0 0.25rem;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 0.875rem;
    transition: all 0.3s;
}

.view-btn {
    background: #667eea;
    color: white;
}

.delete-btn {
    background: #eb3349;
    color: white;
}

/* Modal */
.modal {
    display: none;
    position: fixed;
    z-index: 1000;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0,0,0,0.5);
}

.modal-content {
    background-color: white;
    margin: 10% auto;
    padding: 2rem;
    border-radius: 15px;
    width: 90%;
    max-width: 500px;
    position: relative;
    animation: slideDown 0.3s ease;
}

.close {
    position: absolute;
    right: 1.5rem;
    top: 1rem;
    font-size: 1.5rem;
    cursor: pointer;
    color: #999;
}

.close:hover {
    color: #333;
}

/* Toast Notification */
.toast {
    position: fixed;
    bottom: 20px;
    right: 20px;
    background: white;
    padding: 1rem 1.5rem;
    border-radius: 8px;
    box-shadow: 0 5px 15px rgba(0,0,0,0.2);
    display: none;
    z-index: 1100;
    animation: slideIn 0.3s ease;
}

.toast.show {
    display: block;
}

.toast.success {
    border-left: 4px solid #4caf50;
}

.toast.error {
    border-left: 4px solid #f44336;
}

/* Animations */
@keyframes slideDown {
    from {
        transform: translateY(-50px);
        opacity: 0;
    }
    to {
        transform: translateY(0);
        opacity: 1;
    }
}

@keyframes slideIn {
    from {
        transform: translateX(100%);
        opacity: 0;
    }
    to {
        transform: translateX(0);
        opacity: 1;
    }
}

/* Responsive Design */
@media (max-width: 768px) {
    .registration-section {
        grid-template-columns: 1fr;
        margin-top: -2rem;
    }
    
    .dashboard-header {
        flex-direction: column;
        text-align: center;
    }
    
    .tabs {
        flex-direction: column;
    }
    
    .tab-btn {
        width: 100%;
    }
    
    th, td {
        padding: 0.75rem;
        font-size: 0.875rem;
    }
    
    .action-btn {
        padding: 0.375rem 0.75rem;
        font-size: 0.75rem;
    }
}
