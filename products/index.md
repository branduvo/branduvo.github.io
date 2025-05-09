---
layout: default
title: Branduvo Products
permalink: /products/
---

<div class="products-container">
  <header class="products-header">
    <h1>Our Products</h1>
    <p class="section-intro">Discover our carefully selected range of productivity and marketing tools designed to help your business thrive.</p>
  </header>

  <div class="filter-container">
    <div class="search-box">
      <input type="text" id="productSearch" placeholder="Search products..." onkeyup="filterProducts()">
      <span class="search-icon">🔍</span>
    </div>
  </div>

  <div class="products-grid">
    {% for product in site.pages %}
      {% if product.path contains 'products/' and product.name != 'index.md' %}
        <div class="product-card" data-name="{{ product.title | downcase }}">
          <a href="{{ site.baseurl }}{{ product.url }}">
            <div class="product-image">
              <img src="{{ site.baseurl }}/assets/images/products/svg/{{ product.name | remove: '.md' }}-logo.svg" 
                   alt="{{ product.title }}" 
                   loading="lazy"
                   onerror="this.src='{{ site.baseurl }}/assets/images/placeholder.png'">
            </div>
            <div class="product-content">
              <h3>{{ product.title }}</h3>
              {% if product.tags %}
                <div class="product-tags">
                  {% for tag in product.tags limit:3 %}
                    <span class="tag">{{ tag }}</span>
                  {% endfor %}
                </div>
              {% endif %}
              <p class="product-description">{{ product.description }}</p>
              <div class="learn-more-btn">Learn More <span class="arrow">→</span></div>
            </div>
          </a>
        </div>
      {% endif %}
    {% endfor %}
  </div>

  <div id="no-results" class="no-results-message" style="display: none;">
    <p>No products match your search. Please try different keywords.</p>
  </div>
</div>

<style>
  .products-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
  }

  .products-header {
    text-align: center;
    margin-bottom: 40px;
  }

  .products-header h1 {
    font-size: 2.5rem;
    color: #333;
    margin-bottom: 16px;
    position: relative;
    display: inline-block;
  }

  .products-header h1:after {
    content: "";
    position: absolute;
    width: 60px;
    height: 4px;
    background-color: #4a6bfa;
    bottom: -12px;
    left: 50%;
    transform: translateX(-50%);
    border-radius: 2px;
  }

  .section-intro {
    font-size: 1.2rem;
    color: #666;
    max-width: 700px;
    margin: 20px auto 0;
    line-height: 1.6;
  }

  .filter-container {
    margin-bottom: 30px;
  }

  .search-box {
    position: relative;
    max-width: 400px;
    margin: 0 auto;
  }

  .search-box input {
    width: 100%;
    padding: 12px 20px 12px 45px;
    border: 2px solid #e0e0e0;
    border-radius: 30px;
    font-size: 16px;
    transition: all 0.3s ease;
  }

  .search-box input:focus {
    border-color: #4a6bfa;
    outline: none;
    box-shadow: 0 0 0 3px rgba(74, 107, 250, 0.2);
  }

  .search-icon {
    position: absolute;
    left: 15px;
    top: 50%;
    transform: translateY(-50%);
    color: #888;
  }

  .products-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
    gap: 30px;
    margin-top: 30px;
  }

  .product-card {
    border: 1px solid #e0e0e0;
    border-radius: 12px;
    overflow: hidden;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    background-color: #fff;
  }

  .product-card:hover {
    transform: translateY(-8px);
    box-shadow: 0 15px 30px rgba(0,0,0,0.1);
  }

  .product-card a {
    display: block;
    color: inherit;
    text-decoration: none;
  }

  .product-image {
    height: 200px;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #f9f9f9;
    padding: 20px;
    border-bottom: 1px solid #eee;
  }

  .product-image img {
    max-width: 100%;
    max-height: 160px;
    object-fit: contain;
    transition: transform 0.3s ease;
  }

  .product-card:hover .product-image img {
    transform: scale(1.05);
  }

  .product-content {
    padding: 25px;
  }

  .product-card h3 {
    margin-top: 0;
    margin-bottom: 10px;
    font-size: 1.5rem;
    color: #333;
    font-weight: 600;
  }

  .product-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 12px;
  }

  .tag {
    background-color: #f0f4ff;
    color: #4a6bfa;
    font-size: 0.8rem;
    padding: 4px 10px;
    border-radius: 20px;
    font-weight: 500;
  }

  .product-description {
    color: #666;
    margin-bottom: 20px;
    line-height: 1.5;
    font-size: 1rem;
  }

  .learn-more-btn {
    display: inline-flex;
    align-items: center;
    background-color: #4a6bfa;
    color: white;
    padding: 10px 20px;
    border-radius: 6px;
    font-weight: 500;
    transition: all 0.2s ease;
  }

  .arrow {
    margin-left: 6px;
    transition: transform 0.2s ease;
  }

  .product-card:hover .learn-more-btn {
    background-color: #3651d3;
  }

  .product-card:hover .arrow {
    transform: translateX(4px);
  }

  .no-results-message {
    text-align: center;
    padding: 40px 0;
    color: #666;
    font-size: 1.1rem;
  }

  /* Responsive design */
  @media (max-width: 768px) {
    .products-grid {
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 20px;
    }

    .products-header h1 {
      font-size: 2rem;
    }

    .section-intro {
      font-size: 1.1rem;
    }

    .product-image {
      height: 180px;
    }
  }

  @media (max-width: 480px) {
    .products-grid {
      grid-template-columns: 1fr;
    }

    .product-content {
      padding: 20px;
    }

    .products-header h1 {
      font-size: 1.8rem;
    }
  }
</style>

<script>
  function filterProducts() {
    const searchInput = document.getElementById('productSearch');
    const filter = searchInput.value.toLowerCase();
    const productCards = document.querySelectorAll('.product-card');
    let resultsFound = false;
    
    productCards.forEach(card => {
      const productName = card.getAttribute('data-name');
      if (productName.includes(filter)) {
        card.style.display = "block";
        resultsFound = true;
      } else {
        card.style.display = "none";
      }
    });
    
    document.getElementById('no-results').style.display = resultsFound ? 'none' : 'block';
  }

  // Add animation when products are loaded
  document.addEventListener('DOMContentLoaded', function() {
    const productCards = document.querySelectorAll('.product-card');
    productCards.forEach((card, index) => {
      card.style.opacity = '0';
      card.style.transform = 'translateY(20px)';
      card.style.transition = 'opacity 0.4s ease, transform 0.4s ease';
      
      setTimeout(() => {
        card.style.opacity = '1';
        card.style.transform = 'translateY(0)';
      }, 100 * index);
    });
  });
</script>