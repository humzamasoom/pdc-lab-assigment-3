# Java Hello World with Jenkins

A small Java program built automatically when changes are pushed to `main`.

## Run manually

```sh
mkdir -p build
javac -d build HelloWorld.java
java -cp build HelloWorld
```

Expected output: `Hello World!`

## Build flow

1. Commit and push a change to GitHub.
2. GitHub sends a push event to Jenkins at `/github-webhook/`.
3. Jenkins checks out `main`, compiles the Java source, and runs it.
4. Open the build's **Console Output** to see the result.

The `Jenkinsfile` contains the build stages and GitHub trigger.
A commit kept only on your computer does not trigger Jenkins; push it to GitHub.
