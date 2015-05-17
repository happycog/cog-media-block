# cog-media-block

The Media Block cog is inspired by the pattern first developed by [Nicole Sullivan](http://www.stubbornella.org/content/2010/06/25/the-media-object-saves-hundreds-of-lines-of-code/). An image or other HTML element is float to the left of a body element. Text or other HTML elements in the body will not wrap around the floated image.

## Default Structure

By default, the following mark-up floats the `media--img` element to the left and assigns a default margin of `1em`.

```
<div class="media">
    <div class="media__img">
        ...
    </div>
    <div class="media__body">
        ...
    </div>
</div>
```

To float to the left, replace `media__img` with `media__img-ext`, like so:

```
<div class="media">
    <div class="media__img-ext">
        ...
    </div>
    <div class="media__body">
        ...
    </div>
</div>
```

The default margin will be retained but set to the `margin-left` of the `media__img-ext` rather than on the right, since it's now floating the opposite direction.

## Mixins

For creating custom media block patterns, a mixin is available. You can set it on any single class, like so:

```
.new-module {
    @include media(2em);
}
```

This will produce the following mark-up, and set margins to `2em` rather than the default `1em`:

```
<div class="new-module">
    <div class="new-module__img">
        ...
    </div>
    <div class="new-module__body">
        ...
    </div>
</div>
```

|Mixin|Usage|
|------|------|
|`media`|`media` can be called on any element to create a new media block pattern. The `margin` parameter defaults to `1em`|