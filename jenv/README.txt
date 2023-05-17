# Steps to setup [Jenv](https://github.com/jenv/jenv) on Mac

## 1. Install [Homebrew](https://brew.sh/)
```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## 2. Install jenv

```sh
brew install jenv
```

Add the following commands to your `.zshrc` or `.zprofile`:
    
```sh
export PATH="$HOME/.jenv/bin:$PATH"
eval "$(jenv init -)"
```

To verify jenv was installed, run 

```sh
jenv doctor
```

To make sure JAVA_HOME is set, make sure to enable the export plugin:

```sh
jenv enable-plugin export
exec $SHELL -l
```

## 3. Add and use java
1. Install JDK (to /Library/Java/JavaVirtualMachines)

2. Add it to jenv:

  ```sh
  jenv add /Library/Java/JavaVirtualMachines/amazon-corretto-17.jdk/Contents/Home
  ```
  
3. Use it:

  ```sh
  jenv global 17.0
  ```

  Now you should see it works:
  ```sh
  java --version
  openjdk 17.0.7 2023-04-18 LTS
  OpenJDK Runtime Environment Corretto-17.0.7.7.1 (build 17.0.7+7-LTS)
  OpenJDK 64-Bit Server VM Corretto-17.0.7.7.1 (build 17.0.7+7-LTS, mixed mode, sharing)
  ```

  ```sh
  echo $JAVA_HOME
  /Users/user/.jenv/versions/17.0
  ```
