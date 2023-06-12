`Check the Gradle Installation below!`

Reference :

https://docs.gradle.org/8.1.1/userguide/installation.html
https://spring.io/quickstart
https://chat.openai.com/c/2e321acb-cc10-4921-b392-be4cc0be0cca
https://chat.openai.com/c/9aa09d34-1f93-42f3-9645-d87b95e48a7c
https://docs.gradle.org/8.1.1/userguide/installation.html
https://docs.gradle.org/current/userguide/compatibility.html
https://chat.openai.com/c/1e707a84-59f5-42a9-a9a4-19bb77da5b1c


Check this line! :

https://linuxize.com/post/how-to-install-gradle-on-ubuntu-20-04/



___

export PATH=$PATH:/home/nemesis/Documents/technology/gradle/gradle-8.1.1/bin

PATH=$PATH:/usr/lib/jvm/jdk-20/bin/java

or 

export PATH=$PATH:/usr/lib/jvm/jdk-20/bin/java

___

sudo nano /etc/profile.d/gradle.sh

inside the above file add the following lines(with common sense):

export GRADLE_HOME=/gradle/gradle-8.1.1
export PATH=${GRADLE_HOME}/bin:${PATH}

___


sudo nano /etc/profile

inside the above file add the following lines(with common sense):


export JAVA_HOME=/usr/lib/jvm/jdk-20
export PATH=$PATH:$JAVA_HOME/bin
export PATH=$PATH:/home/nemesis/Documents/technology/gradle/gradle-8.1.1/bin

___


nano ~/.bashrc



___


If warning like below appear...Check the first solution below


```
nemesis@nemesis:~/Documents/Project/spring_boot/demo$ ./gradlew bootRun

Welcome to Gradle 7.4.2!

Here are the highlights of this release:
 - Aggregated test and JaCoCo reports
 - Marking additional test source directories as tests in IntelliJ
 - Support for Adoptium JDKs in Java toolchains

For more details see https://docs.gradle.org/7.4.2/release-notes.html

Starting a Gradle Daemon, 1 incompatible Daemon could not be reused, use --status for details

FAILURE: Build failed with an exception.

* Where:
Settings file '/home/nemesis/Documents/Project/spring_boot/demo/settings.gradle'

* What went wrong:
Could not compile settings file '/home/nemesis/Documents/Project/spring_boot/demo/settings.gradle'.
> startup failed:
  General error during conversion: Unsupported class file major version 64
  
  java.lang.IllegalArgumentException: Unsupported class file major version 64
        at groovyjarjarasm.asm.ClassReader.<init>(ClassReader.java:199)
        at groovyjarjarasm.asm.ClassReader.<init>(ClassReader.java:180)
        at groovyjarjarasm.asm.ClassReader.<init>(ClassReader.java:166)
        at groovyjarjarasm.asm.ClassReader.<init>(ClassReader.java:287)
        at org.codehaus.groovy.ast.decompiled.AsmDecompiler.parseClass(AsmDecompiler.java:81)
        at org.codehaus.groovy.control.ClassNodeResolver.findDecompiled(ClassNodeResolver.java:251)
        at org.codehaus.groovy.control.ClassNodeResolver.tryAsLoaderClassOrScript(ClassNodeResolver.java:189)
```



The error message suggests that there is an issue with the class file version in your Gradle project. It appears that the class file being processed has a major version of 64, which is unsupported.

Typically, major version 64 corresponds to Java 10, but Gradle 7.4.2 may not support that version. To resolve this issue, you have a few options:

1. Update Gradle: Check if there is a newer version of Gradle available that supports Java 10 or higher. You can update Gradle by modifying the `gradle/wrapper/gradle-wrapper.properties` file and changing the `distributionUrl` to the URL of the newer Gradle version. Then, run `./gradlew wrapper --gradle-version <new-version>` to update the Gradle wrapper.

2. Update Java version: If you have Java 10 installed, you can try using a lower version of Java that is supported by Gradle 7.4.2. You can install a different JDK version and configure your project to use that version instead.

3. Check project configuration: Ensure that your project's configuration is correct. Make sure that the Java version specified in the Gradle build files or project settings matches the version of Java you have installed.

4. Check dependencies: If your project depends on external libraries or plugins, make sure they are compatible with the Java version you are using. Check their documentation or release notes for compatibility information.

By taking these steps, you should be able to resolve the "Unsupported class file major version 64" error and successfully run your Spring Boot application.

___


Gradle Installation :


Installing Gradle on Debian can be a straightforward process if you follow the correct steps. Here's a guide to help you install Gradle on Debian:

Step 1: Update the package lists
Open a terminal and run the following command to update the package lists:

```
sudo apt update
```

Step 2: Install Java Development Kit (JDK)
Gradle requires Java to run. You can install OpenJDK, which is a popular open-source implementation of the Java Development Kit. Run the following command to install OpenJDK:

```
sudo apt install default-jdk
```

During the installation process, you may be prompted to accept the terms of the license agreement. Follow the instructions on the screen to proceed.

Step 3: Download Gradle
Visit the Gradle website (https://gradle.org/releases/) and check for the latest stable version. At the time of writing, the latest version is 7.0.2. Adjust the commands below if there's a newer version available.

In the terminal, navigate to a directory where you want to download and install Gradle. For example:

```
cd /opt
```

Download the Gradle distribution using `wget`:

```
sudo wget https://services.gradle.org/distributions/gradle-7.0.2-bin.zip
```

Step 4: Unzip the Gradle distribution
Unzip the Gradle distribution using the following command:

```
sudo unzip gradle-7.0.2-bin.zip
```

This will extract the Gradle files to a new directory named `gradle-7.0.2`.

Step 5: Set up environment variables
To use Gradle globally on your system, you'll need to set up environment variables. Open the `/etc/profile` file using a text editor such as nano:

```
sudo nano /etc/profile
```

Add the following lines at the end of the file:

```
export GRADLE_HOME=/opt/gradle-7.0.2
export PATH=$PATH:$GRADLE_HOME/bin
```

Save the file and exit the text editor.

Step 6: Apply the environment variable changes
To apply the environment variable changes, run the following command:

```
source /etc/profile
```

Step 7: Verify the installation
To verify that Gradle is installed correctly, run the following command:

```
gradle --version
```

You should see the Gradle version and other information displayed in the terminal, indicating a successful installation.

That's it! You have successfully installed Gradle on Debian. You can now use Gradle to build and manage your projects.
