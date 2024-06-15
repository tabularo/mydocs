# Installation @Ubuntu

## Add the OpenJDK PPA:
Continue by pressing `ENTER` to add the PPA.

 ```{code-block} bash
 :caption: Terminal @guest
 
sudo add-apt-repository ppa:openjdk-r/ppa
sudo apt update
 
```

## Install OpenJDK 21:
After adding the PPA, install OpenJDK 21:

 ```{code-block} bash
 :caption: Terminal @guest
 
sudo apt install openjdk-21-jdk -y
 
 ```

## Verify the Java version:
Check the installed Java version to ensure OpenJDK 21 is installed correctly:

 ```{code-block} bash
 :caption: Terminal @guest
 
java -version
 
 ```

##  Set JAVA_HOME Environment Variable:
Set the `JAVA_HOME` environment variable to point to the newly installed Java version. Add the following lines to your `.bashrc` or `.zshrc` file:

 ```{code-block} bash
 :caption: .bashrc
 
export JAVA_HOME=/usr/lib/jvm/java-21-openjdk-amd64
export PATH=$JAVA_HOME/bin:$PATH
 
 ```

##  Reload Your Shell Configuration: 
Ensure the JAVA_HOME variable is set correctly:

 ```{code-block} bash
 :caption: Terminal @guest
 
echo $JAVA_HOME

 
 ```