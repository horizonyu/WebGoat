## Release WebGoat


### Version numbers

For WebGoat we use milestone releases first before we release the official version, we use `v8.0.0.M3` while tagging
 and 8.0.0.M3 in the `pom.xml`. When we create the final release we remove the milestone release and use 
 `v8.0.0` and 8.0.0 in the `pom.xml`

At the moment we use Gitflow, for a release you create a new release branch and take the following steps:

```
git checkout develop
git flow release start <version>
mvn versions:set <<version>  
git commit -am "New release, updating pom.xml" 
git flow release publish
git push --tags
```

Now Travis takes over and will create the release in Github and on Docker Hub.

NOTE: the `mvn versions:set` command above is just there to make sure the master branch contains the latest version


