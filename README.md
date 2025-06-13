# DatCon
http://www.datfile.net/DatCon/downloads.html

## Running on macOS with VS Code

1. Install a Java Development Kit (JDK 8 or later). Using Homebrew you can run:

   ```bash
   brew install openjdk
   ```

2. Clone this repository and open the folder in VS Code. The Java extension
   pack will offer to configure the project automatically.

3. Build the sources (``src`` directory) and include `lib/ia_math.jar` on the
   classpath. From the VS Code terminal you can run:

   ```bash
   javac -classpath DatCon/lib/ia_math.jar -d bin $(find DatCon/src -name "*.java")
   ```

4. Launch the program by executing the main class `src.apps.DatCon`:

   ```bash
   java -cp bin:DatCon/lib/ia_math.jar src.apps.DatCon
   ```

5. Use the graphical interface to select a `.DAT` file from the M300 RTK and
   choose an output directory for the converted CSV files.

