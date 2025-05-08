---
layout: default
title: Branduvo Products
permalink: /products/
---
---
---
# Our Products

Discover our carefully selected range of productivity and marketing tools designed to help your business thrive.

<div class="products-grid">
  {% for product in site.pages %}
    {% if product.path contains 'products/' and product.name != 'index.md' %}
      <div class="product-card">
        <a href="{{ site.baseurl }}{{ product.url }}">
          <div class="product-image">
            <img src="{{ site.baseurl }}/assets/images/products/{{ product.name | remove: '.md' }}.png" alt="{{ product.title }}" onerror="this.src='{{ site.baseurl }}/assets/images/placeholder.png'">
          </div>
          <h3>{{ product.title }}</h3>
          <p>{{ product.description }}</p>
          <div class="learn-more-btn">Learn More</div>
        </a>
      </div>
    {% endif %}
  {% endfor %}
</div>

<style>
  .products-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 25px;
    margin-top: 30px;
  }
  
  .product-card {
    border: 1px solid #e0e0e0;
    border-radius: 8px;
    overflow: hidden;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }
  
  .product-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 20px rgba(0,0,0,0.1);
  }
  
  .product-card a {
    display: block;
    padding: 20px;
    color: inherit;
    text-decoration: none;
  }
  
  .product-image {
    height: 180px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 15px;
  }
  
  .product-image img {
    max-width: 100%;
    max-height: 150px;
    object-fit: contain;
  }
  
  .product-card h3 {
    margin-top: 0;
    margin-bottom: 10px;
    font-size: 1.4em;
  }
  
  .product-card p {
    color: #666;
    margin-bottom: 15px;
  }
  
  .learn-more-btn {
    display: inline-block;
    background-color: #4a6bfa;
    color: white;
    padding: 8px 16px;
    border-radius: 4px;
    font-weight: 500;
    transition: background-color 0.2s ease;
  }
  
  .learn-more-btn:hover {
    background-color: #3651d3;
  }
</style>