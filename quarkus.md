# Quarkus [Website](https://quarkus.io)

**Notes:** I use [cmder](https://cmder.net/) as bash console emulator 

## Windows: GrallVM configuration for native image

You can find the complete installation instructions here: [Configuring GraalVM: Build Executable Native Image](https://quarkus.io/guides/building-native-image#configuring-graalvm)

1) Install [GraalVM 20.2.x](https://www.graalvm.org/) (Java 11+)
2) Set GRAALVM_HOME environment variable to the GraalVM installation directory

```bash
$: export GRAALVM_HOME="${HOME}/Homeware/graalvm20-java11"
```

3) Install the native-image tool using _gu install_

```bash
$: ${GRAALVM_HOME}/bin/gu.cmd install native-image
```

_**Notes:** Your antivirus (like Avast) can block the execution due to security exception (accept the exception)_

4) (Optional) Set the JAVA_HOME environment variable to the GraalVM installation directory

```bash
$: export JAVA_HOME=${GRAALVM_HOME}
```

5) (Optional) Add the GraalVM bin directory to the path

```bash
$: export PATH=${GRAALVM_HOME}/bin:$PATH
```

### Setup file example

```bash
$: cat .graalvm
#!/bin/bash

echo "Loading profile GraalVM 20.x (Java 11+)..."

export JAVA_HOME="${HOME}/Homeware/java/jdk-11.0.8+10"
export GRAALVM_HOME="${HOME}/Homeware/graalvm20-java11"
export PATH="${JAVA_HOME}/bin:${GRAALVM_HOME}/bin:${PATH}"

$: source .graalvm
```
