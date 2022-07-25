~~~
pragma version 0;

Person is PB-Message {
  Identity  is mandatory UUID   as Binary   keyed 0;
  Firstname is mandatory String as UTF-8    keyed 1;
  Lastname  is mandatory String as UTF-8    keyed 2;
  Birthdate is optional  Date   as ISO-8601 keyed 3;
};
~~~
