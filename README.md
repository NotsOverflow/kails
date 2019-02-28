
# Kails
## Bringing Rails To 2019
![enter image description here](http://www.primeale.fr/wp-content/uploads/2016/01/4_choux.jpg)
### TL;DR
> type ```kails -n my_project``` and watch Rails offer a native reactive Front-end, edit your css and js according to airb'n'b guideline and more... :D

### Hello World

> You need Ruby Gem, Yarn and [Hivemind](https://github.com/DarthSim/hivemind) in order to run this


```bash
$> kails -n my_app && cd my_app
# edit config/database.yml according to your configuration
$> rails db:create
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
	p[id="1"]
		= yield
	p[id="2"]= "yolo!"
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
### Enjoy :D
