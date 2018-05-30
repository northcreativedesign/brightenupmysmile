# Creating Checkout Form



## What Am I Trying To Acomplish

- The shopping cart needs to take the color and quantity of each product and add it to a checkout/page.
- Check out needs to be able to update quantity as well as remove products.
- Check out will need a stripe payment gateway for orders to be processed.    



## Form Code

``` {html}
<input id="productQuantity" type="hidden" name="quantity" value="1"/>
 <input id="productId" type="hidden" name="product_id" value="91801160"/>
 <input id="productName" type="hidden" name="product_name" value="Red Hat"/>
 <div class="cta" id="addit"><a class="getstarted-button">Add to Cart!</a></div>
```



## Javascript Code

```{javascript}
$("#addit").click(function(){
  var productId = $("#productId").val();
  var productName = $("#productName").val();
  var productQuantity = $("#productQuantity").val();
  var data = {
    'product_id': productId,
    'product_name': productName,
    'quantity': productQuantity
  };

  $.post("/cart/add", data, showDone);
 });
 
 var showDone = function() {
  /* Make something happen here*/
 }
```



This might need some tweaking and I'll probably need to be able to post the data from the form into the cart.html and then pull checkout data when the page loads. Each color should porbably have a **productId** Will also need to calculate the quantity that is in the viewer window. 

Checkout Page needs to be able to calculate a price and then make a total price, and add price to Checkout form.