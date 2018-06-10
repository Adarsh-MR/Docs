# Tips and tricks

## Decompiled apps history  
It's better to keep track of new changes of an app update by creating a git repository with decompiled app resources, so updated resource changes like layout, styles, colors can be seen using `git diff`, `git diff filename.xml`, `git show`, commands. 
We at [ThemersHub](https://github.com/ThemersHub), keeping the history of some Decompiled Google apps at [ThemersHub/DecompiledApps](https://github.com/ThemersHub/DecompiledApps). 

## Layout theming
One of the best thing about `OMS (Overlay manager service)` is, possibility to overlay layout/ resources. 
While overlaying the layout allows us to theme an app more deeply by changing hardcoded colors etc, it's also requires extra efforts from themer. 
if a future update of the app contains changes to that overlay'd layout, those new changes will go missing on the already overlay'd layout, which is outdate, thus leading to a crash. so it's better to avoid overlaying the layout as much as possible.

However, if you overlaying layout, keep updating the layout on every new app update.

## Version control  
It's highly recommended to host your theme on `Version control system`.

not only it'll serve as a backup, it can be also helpful to track regression caused by recent updates, hence it's important to commit each overlay target changes separately with a proper commit message. 

>Some well-known `Git` hosting service are [GitHub](https://github.com), [BitBucket](https://bitbucket.org), [GitLab](https://gitlab.com).

## Platform-specific values resources  
Platform-specific resources (values-v*) override the resources of values/ (base) with the new attributes introduced on the new Android versions. Don't forget to overlay such resources from the values-v* directory.

## Vector drawable  
`Since Android 5.0`, Android added support for Vector images, which is density dependent, high quality, scalable image format.
It's highly recommended to use `Vector drawable's` instead of `png's` as much as possible, `Vector drawable's` not only reduces the pain of resizing images to each resolution, it also helps in reducing the size of the theme by megabytes. it can also replace `9-patch png's` with the `Shape drawable`, creating `Vector drawable's` is easy, just make sure drawable doesn't consist any gradients, shadows or any effects. Export your project as `SVG`, To convert it to `Android VectorDrawable` format; drag and drop the exported `SVG` into [Svg2Drawable converter](http://a-student.github.io/SvgToVectorDrawableConverter.Web/), download the converted drawable and place it inside `assets/target/res/drawable-anydpi`.

>drawable-anydpi directory recomended for overlaying drawable's as it'll override the same `.png's` on drawable-* directories.

>some well-known vector graphic software's are [Inkscape](https://inkscape.org/en/), [Gravit designer](https://gravit.io/), [Affinity designer](https://affinity.serif.com/en-gb/), [Adobe Illustrator](https://www.adobe.com/in/products/illustrator.html). 

>An in-depth overview of `Android VectorDrawable` [https://developer.android.com](https://developer.android.com/guide/topics/graphics/vector-drawable-resources).

## Code editor  
While `Android Studio` comes with robust Code editor. it's better to have an external text editor if using the [command-line method](project_setup.md#setting-up-the-project-with-command-line).  

>some well-known text/code editors are [Notepad++](https://notepad-plus-plus.org/), [Visual Studio code](https://code.visualstudio.com/), [Sublime text editor](https://www.sublimetext.com/3), [Atom](https://atom.io/).