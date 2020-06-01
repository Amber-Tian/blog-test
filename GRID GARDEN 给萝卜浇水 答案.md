## level1

~~~html
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

#water {
  grid-column-start: 3;
}
~~~

## level2

~~~html
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

#poison {
  grid-column-start: 5;
}
~~~

## level3

~~~html
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

#water {
  grid-column-start: 1;
  grid-column-end:4;
}
~~~

## level4

~~~html
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

#water {
  grid-column-start: 5;
  grid-column-end:2;
}
~~~

## level5

~~~html
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

#water {
  grid-column-start: 1;
  grid-column-end:-2;
}

~~~

## level6

~~~html
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

#poison {
  grid-column-start:-3;
}
~~~

## level7

~~~html
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

#water {
  grid-column-start: 2;
  grid-column-end: span 2;
}
~~~

## level8

~~~html
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

#water {
  grid-column-start: 1;
  grid-column-end:span 5;
}
~~~

## level9

~~~html
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

#water {
  grid-column-start:3;
  grid-column-end: 6;
}
~~~

## level10

~~~html
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

#water {
  grid-column:4/6;
}
~~~

## level11

~~~html
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

#water {
  grid-column:2/5;
}
~~~

## level12

~~~html
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

#water {
  grid-row-start:3;
}
~~~

## level13

~~~html
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

#water {
  grid-row:3/6;
}
~~~

## level14

~~~html
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

#poison {
  grid-column:2;
  grid-row:5;
}
~~~

## level15

~~~html
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

#water {
  grid-column:2/6;
  grid-row:1/6;
}
~~~

## level16

~~~html
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

#water {
  grid-area:1/2/4/6;
}
~~~

## level17

~~~html
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

#water-1 {
  grid-area: 1 / 4 / 6 / 5;
}

#water-2 {
  grid-area:2/3/5/6;
}
~~~

## level18

~~~html
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

.water {
  order: 0;
}

#poison {
  order:1;
}
~~~

## level19

~~~html
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

.water {
  order: 0;
}

.poison {
  order:-1;
}
~~~

## level20

~~~html
#garden {
  display: grid;
  grid-template-columns:50%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

#water {
  grid-column: 1;
  grid-row: 1;
}

~~~

## level21

~~~html
#garden {
  display: grid;
  grid-template-columns:repeat(8, 12.5%);
  grid-template-rows: 20% 20% 20% 20% 20%;
}

#water {
  grid-column: 1;
  grid-row: 1;
}
~~~

## level22

~~~html
#garden {
  display: grid;
  grid-template-columns:100px 3em 40%;
  grid-template-rows: 20% 20% 20% 20% 20%;
}
~~~

## level23

~~~html
#garden {
  display: grid;
  grid-template-columns:1fr 5fr;
  grid-template-rows: 20% 20% 20% 20% 20%;
}
~~~

## level24

~~~html
#garden {
  display: grid;
  grid-template-columns:50px 1fr 1fr 1fr 50px;
  grid-template-rows: 20% 20% 20% 20% 20%;
}

#water {
  grid-area: 1 / 1 / 6 / 2;
}

#poison {
  grid-area: 1 / 5 / 6 / 6;
}
~~~

## level25

~~~html
#garden {
  display: grid;
  grid-template-columns:75px 3fr 2fr;
  grid-template-rows: 100%;
}
~~~

## level26

~~~html
#garden {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
  grid-template-rows: repeat(4, 12.5px) 1fr;
}

#water {
  grid-column: 1 / 6;
  grid-row: 5 / 6;
}
~~~

## level27

~~~html
#garden {
  display: grid;
  grid-template: 60% 40%/200px;
}

#water {
  grid-column: 1;
  grid-row: 1;
}
~~~

## level28

~~~html
#garden {
  display: grid;
  grid-template:1fr 50px/20% 80%
}
~~~
