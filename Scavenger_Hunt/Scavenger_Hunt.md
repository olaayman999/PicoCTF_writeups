# Scavenger Hunt

picoCTF 2021 Web Exploitation

## Description

There is some interesting information hidden around this site http://mercury.picoctf.net:55079/. Can you find it?

## Hints

You should have enough hints to find the files, don't run a brute forcer.

## Wlakthrough

1.open the link and click ctrl+shift+i to inspect the inspector, style editor and debugger
```html

		<h3>What</h3>
		<p>I used these to make this site: <br>
		  HTML <br>
		  CSS <br>
		  JS (JavaScript)
		</p>
	<!-- Here's the first part of the flag: picoCTF{t -->
      
```
```css
#tabintro { background-color: #ccc; }
#tababout { background-color: #ccc; }

/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */
```
```javascript
window.onload = function() {
    openTab('tabintro', this, '#222');
}

/* How can I keep Google from indexing my website? */
```
2. _How can I keep Google from indexing my website?_ this is done by **robots.txt** file managment, view it via the link
http://mercury.picoctf.net:55079/robots.txt
```text
User-agent: *
Disallow: /index.html
# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?
```
3. apache server have the permissions data inside the **.htaccess**, view it via
http://mercury.picoctf.net:55079/.htaccess
```text
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.
```
4. the capitalized "Store" and mentioning MacOS leads to the .DS_Store which contain information about system configuration, view it via the link
http://mercury.picoctf.net:55079/.DS_Store
```text
Congrats! You completed the scavenger hunt. Part 5: _74cceb07}
```

flag => **picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_74cceb07}**
