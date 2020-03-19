# Maven

## Installation

First of all, donwload [Maven](https://maven.apache.org/) and then unzip it in your developement applications folder.

Then, create a `M2_HOME` environment variable pointing to this maven base folder. Add this environment variable to `PATH` as `%M2_HOME%\bin`.

Example: `M2_HOME=C:\development\applications\apache-maven-3`

**TIP: Keep in mind that *maven* need the `JAVA_HOME` environment variable to work.**

## Configuration

In the case where you want to configure a specific maven repository, here is an example.

### Global settings

```xml
<settings [...]>
  [...]
  <localRepository>C:\development\tmp\mvn_repository</localRepository><!--1-->
  [...]
  <mirrors>
    [...]
    <mirror>
      <id>nexus</id>
      <mirrorOf>*</mirrorOf>
      <url>http://${nexus_host}/content/groups/public</url><!--2-->
    </mirror>
  </mirrors>
  [...]
  <profiles>
    [...]
    <profile>
      <id>nexus</id>
      <repositories>
        <repository>
          <id>central</id>
          <url>http://central</url>
          <releases>
            <enabled>true</enabled>
          </releases>
          <snapshots>
            <enabled>true</enabled>
          </snapshots>
        </repository>
      </repositories>
      <pluginRepositories>
        <pluginRepository>
          <id>central</id>
          <url>http://central</url>
          <releases>
            <enabled>true</enabled>
          </releases>
          <snapshots>
            <enabled>true</enabled>
          </snapshots>
        </pluginRepository>
      </pluginRepositories>
    </profile>
  </profiles>
  [...]
  <activeProfiles>
    <activeProfile>nexus</activeProfile>
  </activeProfiles>
  [...]
</settings>
```
**<1>** Specify a directory accessible by everyone to avoid downloading multiple time the same dependencies.  
**<2>** Configure a mirror to the default maven central web site.

### User settings

#### Specific settings

In `C:\Users\${username}\.m2`, create the following files `settings.xml`:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0 http://maven.apache.org/xsd/settings-1.0.0.xsd">
          <localRepository>${pathToUserMVNRepo}</localRepository> <!--1-->
</settings>
```

**<1>** `${pathToUserMVNRepo}` a path to a folder if it should be different from the default `C:\Users\${username}\.m2`.

#### Security

In `C:\Users\${username}\.m2`, create the following files `settings-security.xml`:

```xml
<settingsSecurity>
  <master>${encrypted_master_password}</master> <!--1-->
</settingsSecurity>
```

**<1>** `${encrypted_master_password}` your maven master passwordencrypted with the command: `mvn --encrypt-master-password`

**TIP: Keep this master password safe.**

```xml
<settings>
  <servers>
    <server>
      <id>nexus</id>
      <username>${username}</username><!--1-->
      <password>${encrypted_password}</password><!--2-->
    </server>
  </servers>
</settings>
```

**<1>** `${username}` your nexus login  
**<2>** `${encrypted_password}` your nexus password encrypted with the command: `mvn --encrypt-password`

More information on [Maven password encryption](https://maven.apache.org/guides/mini/guide-encryption.html) website.
