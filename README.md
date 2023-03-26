# Create the final HTML

We use `revealjs` and `pandoc`
```bash
pandoc -t revealjs -s -o Intro2R.html  Intro2R.md  -V revealjs-ur\
l=https://unpkg.com/reveal.js/  --include-in-header=instituteStyle.html  -V them\
e=sky
```

To create a self container HTML with images as well:
```bash
 pandoc -t revealjs -s -o Intro2R.html  Intro2R.md  -V revealjs-ur\
l=https://unpkg.com/reveal.js/  --include-in-header=instituteStyle.html  -V them\
e=sky --embed-resources
```
note the `--embed-resources`
