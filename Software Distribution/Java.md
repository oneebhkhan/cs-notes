### JVM - Java Virtual Machine
JVM stands for Java Virtual Machine. It is an integral part of the Java platform and is responsible for executing Java bytecode.

The JVM acts as an abstract computing machine that provides a runtime environment for Java programs. It is a software implementation that emulates a computer system, including a processor and memory, allowing Java programs to run independently of the underlying hardware and operating system.

#### How it works
When you compile a Java source file (with a .java extension) using the Java compiler (`javac`), it generates a bytecode file (with a .class extension) containing the compiled instructions.

The bytecode file contains a platform-independent representation of the Java program's instructions. It is a binary format that the JVM can interpret or compile just-in-time (JIT) into machine code that can be executed by the underlying hardware.

When you run a Java program, the JVM loads the bytecode files (the .class files) and executes the instructions contained within them. The JVM reads and interprets the bytecode sequentially, executing the corresponding operations and performing tasks such as memory management, security checks, and exception handling.

### JAR - Java Archive files
JAR files play a significant role in the execution of Java programs on the JVM (Java Virtual Machine). A JAR file is a file format that combines multiple Java class files, resources, and metadata into a single compressed archive.

JAR files are commonly used for packaging and distributing Java applications and libraries. They serve as a container that encapsulates all the necessary components of a Java program, including compiled bytecode, resources (such as images, configuration files, etc.), and other dependencies.

When a Java program is distributed as a JAR file, it allows for easier deployment and distribution of the application. The JAR file acts as a self-contained unit that can be executed by the JVM without requiring separate handling of individual class files or resources.

### JNI - Java Native Interface