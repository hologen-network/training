# training
Open online resource for training materials

In order to generate the website, do this:

```
quarto render quarto
cp -r quarto/_site/* docs/
```

Then commit and push to main (or preferably, open a PR).

Could be automated with Github Actions later.