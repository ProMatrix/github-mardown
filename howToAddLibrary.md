[![A Back to Readme](media/arrow-circle-left.svg)](../readme.md)

# How to Add Subsystem

* We have many different sections inside our legend back office such as file management system, account history system etc.   We treat each of them as a subsystem.  All of them (except several isolated ones, they will be treated as applcations as we will talk in the last section) will be a part of back office application of our new oculus project, we add a library for each of them and we will refer it from back office application.

Add a new subsystem abc: (adding a new library)

1. cd oculus/projects - use "mkdir abc" to create a directory
2. ng generate library abc-lib - Angular will generate a library for you with all needed files/configurations and we can modify later
3. Relocate inside of visual studio code the newly generated library from projects folder to your newly generated directory
4. cd abc/abc-lib/src/lib
5. open the tsconfig.spec.json and tsconfig.lib.json files then make sure there is three ../ on line three ex: "extends": "../../../tsconfig.json"
6. open the ng-package.json file and make sure there is three ../ on line two and three ex: "$schema": "../../../node_modules/ng-packagr/ng-package.schema.json" and "dest": "../../../dist/ahs-lib"
7. ng generate component `<abc-lib-component>`  (repeat to create all components) - Angular will generate a component for you with all needed files/configurations, and we can customize it later.
8. Nagivate back to the root directory and inside scripts/buildConfig.json, insert "abc-lib" into buildOrder section,
   it should be the last one of lib but before all app's
9. Within oculus/angular.json, inside the section of abc-lib, we need to add "abc" as an additional level directory.
   Such as: "sourceRoot": "projects/abc-lib/src" needs to modified to ""sourceRoot": "projects/abc/abc-lib/src". This needs to be done multiple times.
   Also, for your newly added library, please check section of "configurations", change production and development to prod and dev respectively. Also change
   "defaultConfiguration": "production" to "defaultConfiguration": "prod".
10. open package.json and then after the last one of watch-(directory)-lib but before watch-(directory)-app add "watch-abc-lib": "node ./scripts/buildDevTargetAndWatch abc-lib",
11. do a build to make sure your new lib can be built.
12. when committing make sure there is no untracked files inside the abc directory


==========

* We also add application under oculus/projects if a subsystem is kind of "isolated" from our back office, for example: embedded hpp, it has own UI and we do not need to login to traditional back office to navigate to it.   Also, login page, it will not need navigation bar and it is kind of ourside of back office although we have to login first to access the back office. So far, we only have 2 applications (hpp and login) besides the main one (back office).  Both are located under projects and we expect we may only have a couple additional applications for oculus but not many.

Add a application xyz: (adding a new application)

1. cd oculus/projects       use "mkdir xyz" to create a directory, then "cd xyz"
2. ng generate application xyz-app// Angular will generate a application for you with all needed files/configurations and we can modify later
3. use section "Add a new subsystem abc (mimic hpp)" steps to add a xyz-lib and its components for this application to refer to
4. cd oculus/projects/xyz/src
5. create a file called indexForWebZip.html,  content should be same as index.html, but should have line `<base href="/oculus/xyz/">` instead of `<base `href="">
6. inside build.xml under oculus directory:   inside section of   `<target name="copy-index-files" unless="build.local">` add below line

`<copy file="projects/xyz/src/indexForWebZip.html" tofile="projects/xyz/src/index.html" overwrite="true"/>`

Along with other project’s index file copy

7. Inside scripts/buildConfig.json, insert "xyz-app" into buildOrder section, it should be the last one of app but before the default app
8. within xyz-app, double check the tsconfig.lib.json, tscofnig.spec.json to make sure the relative directory are good, you need to change ../.. to ../../../ as we did add a one more level of directory "xyz" under projects.
9. within angular.json, inside the section of xyz-app, we need to add "xyz" as an addtional level directory as we did add an extra level directory of xyz.   Such as:        "sourceRoot": "projects/xyz-app/src" needs to modified as "      "sourceRoot": "projects/xyz/xyz-app/src"       Also, for your newly added application, please check section of "configurations", change production and development to prod and dev respectively.
10. do a build to make sure your new app can be build good.

--  We need to do step 5,6 for our main application back office as well.
