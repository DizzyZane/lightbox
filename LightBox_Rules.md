# Rules for various elements in a `lightbox`.

## `<iframe>` element

* Please don't load a full page, UNLESS the user explressively clicks on it. For instance, use a `srcdoc="<a href='//example.com'>Click here to view the page at<br>example.com</a>"`, `src='data/html,<meta http-equiv="Refresh" content="5; url=//example.com">'` (least preferred) or `src="data/html,<a href='//example.com'>Click here to view the page at<br>example.com</a>"` to make it not load instantly. 
* iFrames in any `lightbox` that link to any ad-serving websites will be set to `display:none!important`. This does not affect anything other than iframes in the `lightbox`.

