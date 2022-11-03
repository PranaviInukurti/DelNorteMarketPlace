---
layout: page
title: Listings
permalink: /listings/
---

<html>
<body>
<h1>DN Market Place</h1>
<ul id="listings">
</ul>
<script>
  const ul = document.getElementById('listings');
  const list = document.createDocumentFragment();
  const url = 'https://womeninstem.tk/api/listings/';
  fetch(url)
    .then((response) => {
      return response.json();
    })
    .then((json) => {
      json.map(function(listing) {
        let li = document.createElement('li');
        let name = document.createElement('h2');
		let price = document.createElement('h2');
		let seller = document.createElement('h2');
		let image = document.createElement('h2');
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