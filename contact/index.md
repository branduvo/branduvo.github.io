---
layout: default
title: "Contact Us - Get Support & Inquiries | Your Site Name" # SEO-optimized page title
permalink: /contact/ # Clean, SEO-friendly URL
description: "Reach out to Your Site Name easily through our contact form. Whether you have questions, need support, or want to provide feedback, we're here to help. Get in touch today!" # Compelling meta description
# Optional: For Open Graph (Facebook/LinkedIn) & Twitter Cards - often handled by SEO plugins or layout includes
# og_title: "{{ page.title }}"
# og_description: "{{ page.description }}"
# og_image: "/assets/images/contact-og-image.jpg" # Path to an image for social sharing
# twitter_card: summary_large_image
---

<style>
  /* Basic styling - move to your main CSS file for better organization */
  .contact-container {
    max-width: 700px; /* Constrain width for readability */
    margin: 20px auto;
    padding: 20px;
    /* background-color: #f9f9f9; */ /* Optional: light background for the section */
    /* border-radius: 8px; */
  }

  .contact-container h1 {
    text-align: center;
    margin-bottom: 20px;
    color: #333;
  }

  .contact-intro {
    margin-bottom: 30px;
    line-height: 1.6;
    text-align: center; /* Or left, depending on your design */
  }

  .form-group {
    margin-bottom: 20px;
  }
  .form-group label {
    display: block;
    margin-bottom: 8px;
    font-weight: bold;
    color: #555;
  }
  .form-group input[type="text"],
  .form-group input[type="email"],
  .form-group textarea {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
    font-size: 16px;
  }
  .form-group input:focus,
  .form-group textarea:focus {
    border-color: #007bff;
    outline: none;
    box-shadow: 0 0 0 0.2rem rgba(0,123,255,.25);
  }
  .form-group textarea {
    resize: vertical;
    min-height: 120px;
  }
  .submit-button {
    background-color: #007bff;
    color: white;
    padding: 12px 20px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 16px;
    transition: background-color 0.3s ease;
  }
  .submit-button:hover {
    background-color: #0056b3;
  }
  .honeypot-field {
    display: none !important;
  }
</style>

<div class="contact-container">
  <h1>Get in Touch with Us</h1>

  <p class="contact-intro">
    We'd love to hear from you! Whether you have a question about our services, need assistance,
    or just want to share your feedback, please fill out the form below. Our team
    will get back to you as soon as possible.
  </p>

  <form method="POST" action="https://formspree.io/f/YOUR_FORM_ID_HERE" id="contactForm">
    <!-- Important: Replace YOUR_FORM_ID_HERE with your actual Formspree ID -->

    <div class="form-group">
      <label for="name">Full Name:</label>
      <input type="text" id="name" name="name" placeholder="e.g., Jane Doe" required aria-required="true">
    </div>

    <div class="form-group">
      <label for="email">Your Email:</label>
      <input type="email" id="email" name="_replyto" placeholder="e.g., jane.doe@example.com" required aria-required="true">
      <!-- Using name="_replyto" allows direct reply from your email client -->
    </div>

    <div class="form-group">
      <label for="subject">Subject (Optional):</label>
      <input type="text" id="subject" name="subject" placeholder="e.g., Question about Services">
    </div>

    <!-- Hidden subject for your email, if you prefer a fixed one -->
    <input type="hidden" name="_subject" value="New Contact Form Submission from [Your Site Name]!">

    <div class="form-group">
      <label for="message">Message:</label>
      <textarea id="message" name="message" rows="6" placeholder="Please type your message here..." required aria-required="true"></textarea>
    </div>

    <!-- Honeypot field for spam prevention -->
    <div class="honeypot-field" aria-hidden="true">
      <label for="honeypot">Do not fill this out if you are human:</label>
      <input type="text" id="honeypot" name="_gotcha" tabindex="-1" autocomplete="off">
    </div>

    <!-- Optional: Redirect to a thank-you page -->
    <!-- <input type="hidden" name="_next" value="https://yourdomain.com/thank-you/"> -->

    <button type="submit" class="submit-button">Send Message</button>
  </form>
</div>

<!--
SEO & Accessibility Notes:
1.  Meta Title & Description: Set in the front matter for optimal SERP display.
2.  Permalink: Clean URL (/contact/) set in front matter.
3.  <h1> Tag: Main heading for the page content.
4.  Semantic Labels: <label for="id"> links labels to inputs.
5.  Required Fields: `required` attribute for client-side validation. `aria-required="true"` for accessibility.
6.  Honeypot: `name="_gotcha"` and `tabindex="-1"`, `autocomplete="off"` for spam prevention.
7.  Keywords: Naturally integrate relevant keywords (e.g., "contact", "support", "inquiries", "Your Site Name")
    in the title, description, h1, and introductory text.
8.  Mobile-Friendly: The CSS aims for basic responsiveness. Ensure your overall site theme is responsive.
9.  Page Speed: Keep the page light. Minify CSS/JS if possible (usually handled by Jekyll build process or plugins).
10. Structured Data (Advanced SEO):
    Consider adding JSON-LD structured data for `ContactPage` and `Organization` or `LocalBusiness`.
    This can be added in your layout's <head> or at the bottom of this page.
    Example for Organization (put in <script type="application/ld+json"> tags):
    {
      "@context": "https://schema.org",
      "@type": "Organization",
      "name": "Your Site Name",
      "url": "https://yourdomain.com",
      "logo": "https://yourdomain.com/assets/images/logo.png",
      "contactPoint": {
        "@type": "ContactPoint",
        "telephone": "+1-YOUR-PHONE-NUMBER", // If you have one
        "contactType": "customer service", // or "sales", "technical support" etc.
        "areaServed": "US", // Or your specific regions
        "availableLanguage": ["en"]
      }
    }
    For ContactPage:
    {
      "@context": "https://schema.org",
      "@type": "ContactPage",
      "name": "Contact Us - Your Site Name",
      "description": "How to contact Your Site Name for support and inquiries.",
      "url": "https://yourdomain.com/contact/"
    }
-->