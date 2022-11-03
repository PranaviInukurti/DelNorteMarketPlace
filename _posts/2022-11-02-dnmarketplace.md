---
title: Add Listing
layout: default
description: Fetch listing data from backend
---
<html>
<body>
<h1>DN Market Place</h1>
<ul id=“listings”>
</ul>
<script>
  const ul = document.getElementById(‘listings’);
  const list = document.createDocumentFragment();
  const url = ‘https://womeninstem.tk/api/listings/’;
  fetch(url)
    .then((response) => {
      return response.json();
    })
    .then((json) => {
      json.map(function(listing) {
        let li = document.createElement(‘li’);
        let name = document.createElement(‘h2’);
        let price = document.createElement(‘h2’);
        let seller = document.createElement(‘h2’);
        let image = document.createElement(‘h2’);
        name.innerHTML = ${listing.name};
        price.innerHTML = ${listing.price};
        seller.innerHTML = ${listing.seller};
        image.innerHTML = ${listing.image};
        li.appendChild(name);
        li.appendChild(price);
        li.appendChild(seller);
        li.appendChild(image);
        list.appendChild(li);
        ul.appendChild(list);
      });
    })
    .catch(function(error) {
      console.log(error);
    });
</script>
</body>
</html>
white_check_mark
eyes
raised_hands
9:44
<html>
<body>
  <form onsubmit=“javascript:handleClick();return false”>
  <label for=“object”>Object:</label>
  <input type=“text” id=“object” name=“object”><br><br>
  <label for=“price”>Price:</label>
  <input type=“text” id=“price” name=“price”><br><br>
  <label for=“seller”>Seller:</label>
  <input type=“text” id=“seller” name=“seller”><br><br>
  <label for=“imageURL”>Image URL:</label>
  <input type=“text” id=“imageURL” name=“imageURL”><br><br>
  <input type=“submit” value=“Submit”>
</form>
</body>
<script>
    function handleClick() {
        if (window.confirm(‘If you click “ok” you would be redirected . Cancel will load this website ’))
        {
        window.location.href=‘https://mann223.github.io/fastpages/2022/10/01/dnMarketPlace.html’;
        };;
    console.log(“test”);
        var requestOptions = {
        method: ‘POST’,
        redirect: ‘follow’
        };
        const item = document.getElementById(“object”).value;
        const price = document.getElementById(“price”).value;
        const seller = document.getElementById(“seller”).value;
        const imageURL = ‘&url=’ + encodeURIComponent(document.getElementById(“imageURL”).value);
        fetch(`https://womeninstem.tk/api/listings/create/${item}/${price}/${seller}/${imageURL}`, requestOptions)
    }
</script>
</html>