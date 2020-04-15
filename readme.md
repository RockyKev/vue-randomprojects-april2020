# What is this?

This is a collection of random vue-esque projects I've built that demonstrate a specific action or thing. My intention was to keep it scoped as small as possible.

## April 14

### navigation.html

This is a nav bar.

What's interesting is the CSS. If the parent (nav) has the same classname as the child, then give it a pink background color.

```nav.home .home,
nav.projects .projects,
nav.services .services,
nav.contact .contact {
  background-color: #e35885;
}
```

Of course, what class the parent has is controlled by the onclick function of vue.

### inline-editor.html

This is an example of two-way binding, and showing/hiding elements.
If you click on the text, it turns on the toolbar. Any clicks outside of the toolbar (anywhere else in the div element) triggers the hide toolbar function.

Design-wise: this is kind of a shitty set-up, as the 'toolbar' is absoluted into position.

### price-tally.html

This does a lot of cool stuff.

```
<li
    v-for="service in services"
    v-on:click="toggleActive(service)"
    v-bind:class="{ 'active' : service.active }"
>
```

1. it loops through each element in the services object.
2. It binds a onclick function to each <li>
3. Vue's Class & Style Bindings. If the element has active == true, then set the class 'active'.

Also, this uses Vue Filters.

### searching.html

This is simulating a getting a JSON file.

What's cool is this pattern.

```
    articles_array = articles_array.filter(function (item) {
        //this turns the title string into a array.
        if (item.title.toLowerCase().indexOf(searchString) !== -1) {
        return item;
        }
    });
```

With Vue's Computed Property, it runs this filter with every character you type in the search bar.

### display-style.html

This works. It's kinda a weird 'show this, otherwise this'.
What's really funky that this lives in a FORM!
