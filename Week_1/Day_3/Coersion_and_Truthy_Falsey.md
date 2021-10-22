## Coersion and Truthy/Falsey
---
### Coersion
---

Triple Equals ===
* Compares value AND type

```javascript
100 === "100"
returns false
```

Double Equals ==
* Compares value but not type

```javascript
100 == "100"
returns true
```
* Before comparison, the  == operator will try to *force* the values to be the same type! TYPE COERSION !

!== vs != works the same way, where != will attempt type coersion. 

---
### Truthy and Falsey
---
In JS, everything has an inherant Boolean value - a "truthiness" or a "falsiness"

#### Falsey Values:
* 0
* ""
* NaN
* null
* undefined
* false

#### Truthey Values:
* Pretty much everything else


Truthy and falsey values are an easy way to check conditions in our code.

Eg: If I want to set value for username only if there isn't already a value:
```javascript
username = '';

if (!username) {
  username = 'Siobhan';
}
```

