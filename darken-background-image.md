## Darken Background Image while keeping Text Bright

![screen shot](./images/darken-bg.webp)

### CSS (simplified)
```
.main-container {
  background-color: rgba(0, 0, 0, 0.783);
  background-image: url("bg-1.webp");
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  background-attachment: fixed;

  background-blend-mode: color;
}
```

### HTML (Simplified)
```
<div class="main-container>
  <h1>Hello, my name is Jiho Sohn</h1>
  <p>I am a software engineer residing in south Florida. I love JavaScript, React.js, CSS, Python, MongoDB and more. When I'm not crafting code, you will find me tending to my garden, keeping my Belgian Malinois on her toes (paws), and revving up my Ducati like it's an API.</p>
</div>
```

### Live Sample
[jsohndata.github.io/neo-tokyo-portfolio](https://jsohndata.github.io/neo-tokyo-portfolio)

<br>

## Note:
Edge prior 79 do not support the `background-blend-mode` property.