# Learn Node Core Concepts — Routing
*Request Has all the information*
*Response has all the methods for sending data back*
---
### Request.query
_req.query_ https://localhost*?name=“tomy”&age=“16”*
_req.query.name_ https://localhost?*name=“tomy”*&age=“16”

---
### Request.params
```
router.get(‘/reverse/:name’, (req, res) => {
	res.send('Hello')
}
```
_req.params_ https://localhost/reverse/*tomy*
```
router.get(‘/reverse/:name’, (req, res) => {
	res.send(req.params.name)
}
```
// In _https://localhost/reverse/tomy_ 
// Will Display `tomy`

---
### Routing with app.use and express().Router
`app.use(‘/‘, router) `
*will get anything /—anything* in router
```
router.get('/',(req, res) => {
	res.send('Hello')
}
```
In https://localhost // _displays *Hello*_

```
router.get('/second',(req,res)=> {
	res.send('Hello You Two')
}
```
In https://localhost/second // _displays *Hello You Two*_

#### Example 2 with Routing 
so  `app.use(‘/panda‘,router)`  will get anything /panda/—anything	
```
router.get('/',(req, res) => {
	res.send('Bulok')
}
```
In https://localhost/panda // _display *Bulok*_

```
router.get('/second',(req,res) => {
	res.send('Bulok You Two’)
}
```
In https://localhost/panda/second // _display *Bulok You Two*_
---
### Some Response Methods
`res.send()`  
`res.json()` 
*Read Express Documentation*
*Will be Learning // req.body* 