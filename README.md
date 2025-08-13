# DatCon
http://www.datfile.net/DatCon/downloads.html

## Running on macOS with VS Code

1. **Install JDK 8.**
   - If Homebrew is not installed, follow the instructions at  
     https://brew.sh to set it up.
   - Install the JDK and make it available to the system:

     ```bash
     brew install openjdk@8
     sudo ln -sfn $(brew --prefix openjdk@8)/libexec/openjdk.jdk \
         /Library/Java/JavaVirtualMachines/openjdk-8.jdk
     echo 'export PATH="$(brew --prefix openjdk@8)/bin:$PATH"' >> ~/.zshrc
     echo 'export JAVA_HOME=$(/usr/libexec/java_home -v1.8)' >> ~/.zshrc
     source ~/.zshrc
     java -version
     javac -version
     ```

2. **Install Visual Studio Code and the Java Extension Pack.**
   - Download VS Code from https://code.visualstudio.com and install it.
   - Launch VS Code, open the Extensions view (⇧⌘X), and install “Extension Pack for Java”.

3. **Clone this repository and open it in VS Code:**

   ```bash
   git clone <repository-url>
   cd DatConM300
   code .
   ```

   When the folder opens, allow the Java extension to configure the project.

4. **Build the sources.** From the integrated terminal (⌃`)
   run:

   ```bash
   javac --release 8 -classpath DatCon/lib/ia_math.jar -d bin $(find DatCon/src -name "*.java")
   ```

   This compiles the Java files into the `bin` directory.

5. **Launch the program:**

   ```bash
   java -cp bin:DatCon/lib/ia_math.jar src.apps.DatCon
   ```

6. **Use the graphical interface** to select a `.DAT` file from the M300 RTK and
   choose an output directory for the converted CSV files.

