# Sushi
> Tasty, bite sized, Sass grid system


#### Basic Grid Pattern

```scss
.grid__# {
	@include sushi__grid-pattern(#);
}
```

For example: Grid pattern of 4 || 3 columns

```scss
.grid__4 {
	@include sushi__grid-pattern(4);
}
```

#### Static Pattern
(Doesn't collapse at 'smart breakpoint')

```scss
.grid__#--static {
	@include sushi__grid-pattern(#, false);
}
```

For example: Grid pattern of 6 || 2 columns that doesn't collapse

```scss
.grid__6--static {
	@include sushi__grid-pattern(6, false);
}
```

#### Offset

```scss
.grid__#--offset {
	@include sushi__grid-offset(#);
}
```

For example: Grid offset of 4 || 3 columns of space to the left

```scss
.grid__4--offset {
	@include sushi__grid-offset(4);
}
```

#### Cascading Grid Pattern

```scss
.grid__#--breakpoint {
	@include sushi__grid-pattern(#, true, $breakpoint);
}

.grid__#--breakpoint--static {
	@include sushi__grid-pattern(#, false, $breakpoint);
}
```

For example, to create a **4 then 3 then 2 column layout**, casacading at the predefined breakpoints respectivly:
(All calculated in the default 12 column system)

```scss
$narrow: 480px;
$medium: 720px;
$wide:   1140px;

/* Grid pattern of 6 || 2 columns @ the narrow breakpoint, that doesn't collapse */
.grid__6--narrow--static {
	@include sushi__grid-pattern(6, false, $narrow);
}

/* Grid pattern of 4 || 3 columns @ the medium breakpoint */
.grid__4--medium {
	@include sushi__grid-pattern(4, true, $medium);
}

/* Grid pattern of 3 || 4 columns @ the wide breakpoint */
.grid__3--wide {
	@include sushi__grid-pattern(3, true, $wide);
}
```

The HTML class would be (mobile first approach)

```
column grid__6--narrow--static grid__4--medium grid__3--wide
```

**Issues**

https://github.com/beaucharman/sushi/issues