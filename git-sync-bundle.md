# Workflow for synchronising offline

create a sync bundle

``` console
$ git clone --mirror https://repo.git
$ cd repo.git
$ git bundle create ../repo.bundle --all
```

get the bundle on to your target machine...

``` console
$ mkdir repo.git
$ cd repo.git
$ git init --bare
$ cd ..
$ git clone repo.git
$ cd repo
$ git pull ../repo.bundle
```

Synchronisation complete...

Now in the other direction, applying a patch set via a bundle

``` console
$ cd repo
$ git log
```

Take note of the hash before the change set you need, then create a bundle from the commit range, in this case up to HEAD

``` console
$ git bundle create ../patch.bundle 4bd3ea6a6f46dd9a7114d460889a762727c9701e..HEAD --branches –tags
```

move the bundle to the target machine

``` console
$ cd repo
$ git pull ../patch.bundle
$ git push
```
