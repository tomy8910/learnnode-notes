# Learn Node Core Concepts — Templating
## Setup
```
	// view engine setup
	app.set('views', path.join(__dirname, 'views')) // or any other named folder

app.set('view engine', 'pug')
```

---

```
router.get('/', (req, res) => {
  res.render('hello', {
		name: 'Tomy',
		dog: 'Gibo'
	})
})
```
*Renders hello.pug* 
Passes options as well which can be accessed 
```
	p.hello Hello my dogs name is #{dog}
```
*#{}* — use this to access passed data 
You can even use /req.query or req.params/ to pass in options

*Use template literals to pass values into attributes
alt=`Dog ${dog}`
---
Pug is about indentation

```
.wrapper.ohno
  p.hello Hello
	span#yo Yo!!
	img.dog(src="dog.jpg" alt="Dog"

h2 
	| Hello
	em How are you?
```

gets compiled to
```
<div class="wrapper ohno">
	<p class="hello">Hello</p>
	<span id="yo">Yo!!</span>
	<img class="dog" src="dog.jpg" alt="Dog">
</div>

<h2>
	Hello
	<em>How are you?</em>
</h2>
```

*You may use javaScript inside pug*
```
- const shit = 'haha'
```
*Note the dash*

---
*For extension*

// layout.pug 

```
header
	h1 Shit

.content
	block content
```


```
extends layout

block content
	Haha
```

#### Compiles to

```
	<h1>Shit</h1>

	<div class="content">
		Haha
	</div>
```

Blocks may be overwritten if they have default content