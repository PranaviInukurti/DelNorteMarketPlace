---
layout: page
title: Market Place
permalink: /marketplace/
---

<html>
<style>
ul {
    list-style-type: none;
}
.card {
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
  width: 40%;
}
.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}
.container {
  padding: 2px 16px;
}
</style>
<body>
<h1>Market Place</h1>
<div id="listings" class="grid-container">
</div>
</ul>
</div>
<script>
  const resultContainer = document.getElementById('listings');
  const url = 'https://womeninstem.tk/api/listings/';
  fetch(url)
    .then((response) => {
      return response.json();
    })
    .then((json) => {
      json.map(function(listing) {
        let listingCard = document.createElement('div');
		listingCard.setAttribute("class", "card");
        let name = document.createElement('h1');
        let price = document.createElement('p');
        let seller = document.createElement('p');
        let image = document.createElement('p');
        name.innerHTML = listing.name;
        price.innerHTML = listing.price;
        seller.innerHTML = listing.seller;
        image.innerHTML = listing.image;
        listingCard.appendChild(name);
        listingCard.appendChild(price);
        listingCard.appendChild(seller);
        listingCard.appendChild(image);
        resultContainer.appendChild(listingCard);
      });
    })
    .catch(function(error) {
      console.log(error);
    });
</script>
</body>
</html>