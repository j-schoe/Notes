~~~
Counter := {

  ./Count :: {
    .     :: Int32;
    .:set :: (::Int32) {};
  };

  ./Increase :: (::Int32 default 1) {};
  ./Decrease :: (::Int32 default 1) {};

};

$counter :: Counter := Import();
$counter/Count |> stdout; ## 0
$counter/Increase();
{} |> $counter/Increase;
$counter/Count |> stdout; ## 2
0 |> $counter/Count:set;
$counter/Count |> stdout; ## 0
~~~

~~~
ConfigFolder := {
  ./readme.txt    :: FsFile const;
  ./main.cfg      :: FsFile;
  ./netw.cfg      :: FsFile optional;
  ./custom/**.cfg :: FsFile optional;
};

$cf :: ConfigFolder := Import();
cat $cf/readme.txt         |> stdout;
cat $cf/main.cfg           |> stdout;
cat $cf/custom/Foo/Bar.cfg |> stdout;
~~~
