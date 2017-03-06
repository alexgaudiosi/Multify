# Multify

Multify allows your clients to preemptively see stock levels for all variants of a product, and order multiple quantities of each one simultaneously with a single Add To Cart click. Perfect for wholesale Shopify sites handling bulk orders.

![Multift Image](/assets/multify-table.png)

**NOTE:** This repository still a work in progress, the functionalty is there but I currently can't guarentee it will work instantly if you copy/paste the contents into your project, I'm working to make everything more dynmaic then do a few test runs but it's very likely you'll need to do some tweaking to get it attuned to your store.

---

### How it works

As you can only add a single variant in a given call to the Shopify API, Multify will queue up your orders and fire off each cart addition in succession, it even has a max range set on the variant dropdown to stop over ordering based on its stock level, and greying out sold out items.

---

### How to use

1. Create a new snippet called `multify.liquid` in your snippets folder and paste the contents of `snippets/multify.liquid` in it. The default variant titles are 'Colour' and 'Size', take note of the British spelling and change these so as to match your backend.

2. In your `product.liquid` file, find the opening `<form>` tag, and remove it, then place an z{% include 'multify.liquid' %}` in its place.

3. Still in your `product.liquid`, insert the contents of `multify.js.liquid` before the closing body tag.

4. Give it a test run, and you should see the products fire off to the Shopify API in the console, on completion the table should reset all values to 0. 

---

**NOTE:** I haven't implemented to the functionality to update the max quantity selectors, as the stock isn't updated on the backend until an order is placed, it would get too sticky to try work out the new max ranges, but feel free to have a go.


JS coming soon.
