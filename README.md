# Sushi
> Tasty, bite sized, Sass grid system


### Basic Grid Pattern

```scss
.grid__# {
	@include sushi__grid-pattern(#);
}
```

### Static Pattern (Dosn't no collapse at 'smart breakpoint')

```scss
.grid__#--static {
	@include sushi__grid-pattern(#, false);
}
```

### Offset

```scss
.grid__offset--# {
	@include sushi__grid-offset(#);
}

### Cascading Grid Pattern

```scss
.grid__#--query {
	@include sushi__grid-pattern(#, true, $query);
}

.grid__#--query--static {
	@include sushi__grid-pattern(#, false, $query);
}
```

For example, to create a 4 - 3 - 2 column layout, casacading at the predefined breakpoints respectivly:
(All calculated in the default 12 column system)

```scss
$narrow: 480px;
$medium: 720px;
$wide: 1140px;

/* Grid pattern of 6 = 2 columns @ the narrow breakpoint */
.grid__6--static {
	@include sushi__grid-pattern(6, false, $narrow);
}

/* Grid pattern of 4 = 3 columns @ the medium breakpoint */
.grid__4--query {
	@include sushi__grid-pattern(4, true, $medium);
}

/* Grid pattern of 3 = 4 columns @ the wide breakpoint */
.grid__3--wide {
	@include sushi__grid-pattern(3, true, $wide);
}
```