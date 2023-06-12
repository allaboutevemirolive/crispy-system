References:

https://chat.openai.com/c/7fdb7f50-48c5-4cf3-894c-57c64223acdd

https://chat.openai.com/c/9aa09d34-1f93-42f3-9645-d87b95e48a7c

https://www.digitalocean.com/community/tutorials/install-maven-linux-ubuntu

___



```
The line below is for gradle...How about maven?


./gradlew wrapper --gradle-version <new-version>
```


The equivalent command for Maven would be:

```
mvn wrapper:wrapper -Dmaven=version=<new-version>
```

This Maven command sets up the Maven Wrapper with the specified `<new-version>` for Maven. The Maven Wrapper is a shell script (`mvnw` or `mvnw.cmd`) and a small Maven distribution bundled with your project. It allows you to run Maven builds without needing to install Maven separately on your system.

When running the above command, replace `<new-version>` with the desired version of Maven that you want to use. This will update the Maven Wrapper configuration in your project to use the specified version.

___


```
I want to set maven in my environtment
```

To set up Maven in your environment, you can follow these steps:

1. Open the terminal.

2. Edit the `.bashrc` file in your home directory using a text editor. For example:
   ```
   nano ~/.bashrc
   ```

3. Add the following lines to the end of the file:
   ```
   export MAVEN_HOME=/home/nemesis/Documents/technology/maven/apache-maven-3.9.2
   export PATH=$MAVEN_HOME/bin:$PATH
   ```

   Replace `/home/nemesis/Documents/technology/maven/apache-maven-3.9.2` with the actual path to your Maven installation directory.

4. Save the changes and exit the text editor.

5. Run the following command to apply the changes to the current terminal session:
   ```
   source ~/.bashrc
   ```

6. Verify that Maven is set up correctly by running the following command:
   ```
   mvn -version
   ```

   You should see the Maven version and other details displayed in the terminal.

By adding the `MAVEN_HOME` and `PATH` environment variables to the `.bashrc` file, you ensure that Maven is available in your environment and that you can run Maven commands from any location in the terminal.