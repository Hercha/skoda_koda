# Developer Guide

## GIT Started (pun intended)
First fork the project by clicking fork in the upper right corner of this window (you need to be logged in). Now open your terminal (or command prompt) and run:
```
$ git clone https://www.github.com/<yourusername>/skoda_koda && cd skoda_koda
```
You now have a local clone of your fork, let's create a reference to the original (real) repo also:
```shell
$ git remote add original https://github.com/joseflekardal/skoda_koda
```
Whenever you need to pull a updated version from it just run:
```shell
$ git pull orignal master
```
The idea here is that everyone works in their separate fork (copy) of the repository. Whenever a [commit](#commit) or a [push](#push) is made it only happens on your fork. Whenever you complete an assignment you should make a [pull request](#pull). Your request will be reviewed and then pulled into the real project.
___

## Commit
*Commiting* is essentially saving your changes, whenever something is fixed, improved or changed you should commit it.
In this project we like to keep things tidy and therefore a commit should be formated like so:
```
<type>: <subject>
```
Eg: `$ git commit -m "fix: An endless loop was triggered on submit, now fixed"`

**Types:**
* feat: New feature
* fix: Bug fix
* format: Change not affecting the meaning of code (white-space, formatting, etc)
* docs: Documentation-only change
* style: Stylesheet-only change
* refactor: Change that neither fixes a bug or adds a feature

## Push
Whenever you're done working, you should always push your changes to your Github (what if there was a fire or someone stole your computer etc, always push before you close your machine). To push you first need to select what commits that should be pushed. Most of the time you want to add all and this is how you do it in terminal or command prompt:
```shell
$ git add .
```
Cool, almost done - now we are ready to push to Github:
```shell
$ git push origin master
```
Easy hey?

## Pull Request
Let's say you've just defeated the most annoying bug and now you want to push your changes to the original repo (the real one). Let's first do our [push](#push) (we already know this one). Now lets go to your space on github and into the repo (github.com/<username>/skoda_koda) find the button that says **"new pull request"** and follow the given steps. When your code has been reviewed it will be pulled to the real project!

**Still confused?** Check out [this guide](https://guides.github.com/activities/forking/) from Github. This can obviously all be done through a graphic interface like [Sourcetree](https://www.sourcetreeapp.com/) or [Github desktop client](https://desktop.github.com/)
___

## HTML
HTML5 elements will always be used when possible!

## STYLESHEETS
This project embraces [BEM](http://getbem.com/introduction/), it will help us to keep a good structure as the application grows. We don't use IDs for styling (id's will be used for functionality in JS only. Everything will be targeted by class names, not tag names. Eg.
```html
<main class="tweet-wrapper">
  <article class="tweet">
    <p class="tweet__text">I love snowy weather! #notsomuch</p>
    <div class="tweet__author">by: @joseflekardal</div>
    <span class="tweet__like"><i class="tweet__like-icon"></i></span>
    <span class="tweet__like-count tweet__like-count--no-likes">0</span>
  </article>
  <article class="tweet tweet--latest">
    <p class="tweet__text">I want summer so bad!! #nowplease</p>
    <div class="tweet__author">by: @hkrei</div>
    <span class="tweet__like"><i class="tweet__like-icon"></i></span>
    <span class="tweet__like-count">410</span>
  </article>
</main>
```

Will give SCSS like this:
```scss
.tweet-wrapper {
  display: flex;
}

.tweet {
  background: salmon;
  
  &__text {
    color: #333;
  }
  
  &__author {
    font-size: .8em;
  }
  
  &__like {
    color: $red;
  }
  
  &__like-icon {
    font-size: 1.2em;
  }
  
  &__like-count {
    color: $blue;
    
    &--no-likes {
      color: #666;
    }
  }
}
```
