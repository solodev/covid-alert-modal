# covid-alert-modal
Include disclaimers and other details in a collapsible window

## Tutorial

For detailed instructions, view the [COVID Alert Modal](http://www.covidresponse19.com/free-website-tools/covid-alert-modal.stml) article.

## Demo

Check out a working example on [JSFiddle](https://jsfiddle.net/solodev/73oyvgah/).

## HTML

Add the HTML snippet your templates or webpages, preferably at the bottom since the element will be fixed to the bottom of the page. Add a URL to the "Learn More" link so that users can get additional information.

```
<div class="covid-banner">
  <div>
    <p>
      We are committed to providing updates during this time.
      <a class="banner-more" href="#">Learn More</a>
      <a class="banner-dismiss" href="#">Dismiss</a>
    </p>
  </div>
</div>
```


## CSS

Customize all colors to meet your individual brand needs. The main "covid-banner" selector uses the fixed position so that a user prominently sees it when the page loads.

```
.covid-banner {
	border-top: 2px solid #d10000;
	position: fixed;
	bottom: 0;
	left: 0;
	width: 100%;
	max-width: 100%;
	padding: 1rem .5rem;
	background: #fff;
	z-index: 1030;
	color: #000;
	font-size: 14px;
	margin: 0;
}
.covid-banner p {
	margin: 0;
	color: #000;
	text-align: center;
}
.covid-banner .banner-wrapper p {
		padding-right: 3rem;
}
.covid-banner a {
	text-decoration: none;
	margin: 20px auto 0 auto;
	display: block;
	max-width: 150px;
}
.covid-banner a:hover {
	text-decoration: underline;
}
.covid-banner button {
	position: absolute;
	right: 5px;
	top: calc(50% - 12.5px);
	color: #fff;
	outline: 0;
	height: 25px;
	width: 25px;
	border: 0;
	display: flex;
	align-items: center;
	justify-content: center;
	font-size: 1.35rem;
	font-weight: 700;
	border-radius: 50%;
	text-align: center;
	padding: 0;
	line-height: 1;
	background: #000;
	cursor: pointer;
}
.banner-dismiss {
	color: #000;
}
.banner-more {
	padding: 7px 15px;
	color: #fff;
	border-radius: 5px;
	background: #d10000;
}
@media (min-width: 768px) {
	.covid-banner {
		padding: 1.5rem .5rem;
	}
	.covid-banner a {
		display: inline-block;
		margin: 0 10px;
	}
}
```

## HTML

The below JavaScript is optional if you want to enable the "dismiss" feature. Using the below JS (with jQuery needed), you can set a local storage cookie so that users can dismiss the modal and have it not re-appear.

```
<script src="https://code.jquery.com/jquery-3.2.1.slim.min.js"></script>
<script>
// Banner Trigger if Not Closed
if (!localStorage.bannerClosed) {
  $('.covid-banner').css('display', 'inherit');
} else {
  $('.covid-banner').css('display', 'none');
}
$('.covid-banner button').click(function() {
  $('.covid-banner').css('display', 'none');
  localStorage.bannerClosed = 'true';
});
$('.banner-dismiss').click(function() {
  $('.covid-banner').css('display', 'none');
  localStorage.bannerClosed = 'true';
});
if (navigator.userAgent.match(/Opera|OPR\//)) {
  $('.covid-banner').css('display', 'inherit');
}
</script>
```


