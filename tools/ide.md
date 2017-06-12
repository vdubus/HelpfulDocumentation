# IDE

## [Atom](https://atom.io/)

A nice text editor developed and maintained by GitHub, with lot of functionalities and package that you can install to match your needs.

### Recommanded [packages](https://atom.io/packages)

Atom allow us to install lot of plugins (named packages) which can be quite useful.  
Here a list of some of them which should, I think, be installed by default.

-   [atom-beautify](https://atom.io/packages/atom-beautify) - To format your source code for lot of languages.
-   [file-icons](https://atom.io/packages/file-icons) - To add more relevant icons to files.
-   [minimap](https://atom.io/packages/minimap) - To display a preview of the full source code.

### Alternatives

-   [SublimeText](https://www.sublimetext.com/) - A commercial product which offer lot of functionalities using plugins.
-   [Visual Studio Code](https://code.visualstudio.com/) - The Microsoft's Atom like application.

## [Eclipse](https://www.eclipse.org/)

Eclipse is one of the most used editor for Java Developers because:

-   It is free
-   It have lot of plugins available

There also exist some modified version for specific needs:

-   [Spring Tool Suite](https://spring.io/tools/sts) - A modified version of [Eclipse](https://www.eclipse.org/) to develop Spring based applications.

### Configuration

#### [Lombok](https://projectlombok.org/)

This project, allow us to forget about writing:

-   Setter
-   Getter
-   Logger

To install it, simply follow the [installation process](https://projectlombok.org/setup/eclipse) from Lombok.  
Also, to enable the functionality, don't forget to add the [lombok dependency](https://www.mvnrepository.com/artifact/org.projectlombok/lombok) to your project.

Example for Maven:

```xml
<dependency>
    <groupId>org.projectlombok</groupId>
    <artifactId>lombok</artifactId>
    <version>1.16.16</version>
</dependency>
```

### Recommanded plugins

#### [MyRegexp](http://www.myregexp.com/eclipsePlugin.html)

A plugin allowing you to test your [Regex](https://en.wikipedia.org/wiki/Regular_expression) inside your favorite IDE.  
There is also an online counterpart.

### Alternatives

-   [IntelliJ](https://www.jetbrains.com/idea/) - Existe in both community and commercial use packages.
-   [NetBeans](https://netbeans.org/) - Just like Eclipse, it is free to use.
