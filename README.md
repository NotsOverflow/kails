
# Kails
## Bringing Rails To 2019
![enter image description here](http://www.primeale.fr/wp-content/uploads/2016/01/4_choux.jpg)
### TL;DR
> type ```kails -n my_project``` and watch Rails offering a native reactive Front-end, watch it reload the page each edit automatically, watch it edit your css and js according to airb'n'b guideline and more... :D

### Hello World

> You need Rails, Yarn and Hivemind in order to run this

```bash
$> kails -n my_app && cd my_app
$> rails g controller home index
$> rails g komponent hello
```
Edit the following files:
```javascript
// frontend/packs/application.js
import "init";
import "komponents/hello/hello";
```
```css
/* frontend/komponents/hello/hello.css */
.hello {
	font-weight: bolder;
	font-size: x-large;
}
```
```slim
/ frontend/komponents/hello/_hello.html.slim
div[class="hello"]
	= yield
```
```slim
/ app/views/home/index.html.slim
= komponent "hello"
	p= "this is inside hello"
```
### Run it localy!
```bash
$> hivemind Procfile.dev
```
Go to ``` http://localhost:5000/home/index ``` and voila! :)

### Deploy on heroku!
```bash
$> heroku create
$> git add . && git commit -m "clean commit"
$> git push heroku master
```
### Whats next ?
- Automation of action cables to get real-time notification
- Turbolinks to load komponents on the fly :)