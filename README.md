# Algo Visualizer

## Table of Contents

* [About](#about)
* [Build Instructions](#build-instructions)
  * [Dependencies](#dependencies)
  * [Dev Build](#dev-build)
  * [Prod Build](#prod-build)
* [Contributing](#contributing)
* [Adding an Algorithm](#adding-an-algorithm)
* [Reporting Issues](#reporting-issues)
* [Notes](#notes)

---

## About

**Algo Visualizer** is an educational tool designed to help students or curious people understand how algorithms work. It provides step-by-step visualizations of algorithm executions, allowing users to observe how data evolves over time.

The software also includes supplementary information such as:

* Time and space complexity
* Algorithm origin and history
* Implementations in different programming languages
* A concise summary of how the algorithm operates

*Code documentation is not online yet.*
*No screenshot are available at the moment.*

---

## Build Instructions

### Dependencies

| Dependency | Version |
| ---------- | ------- |
| Maven      | 3.9.12  |
| JDK        | 25.0.2  |
| JavaFX     | 24      |
| FXmisc     | 0.11.5  |
| Jackson    | 2.19    |

### Dev Build

It is highly recommended to at least run the `build.sh` script once, even if you're going the manual way. This way, you will be warned if your version of Maven / JDK is not suitable.

#### Manually

1. **Run tests:**

```bash
mvn clean test
```

2. **Compile the project:**

```bash
mvn clean compile
```

3. **Run the project:**

```bash
mvn javafx:run
```

### Using the build script

1. **Execute the script:**

```bash
./build.sh
```

2. **Select the correct option:**

When prompted, type C for compile. The project will be compiled and, if you did not make any changes to the script, the tests will run automatically.

3. **Run the project:**

Here you have two choices: either start the `build.sh` script and select R, or use this command:

```bash
mvn javafx:run
```

### Prod Build

#### Manually

1. **Package the application:**

```bash
mvn clean package
```

2. **Build the application with JavaFX support:**

```bash
mvn clean javafx:jlink
```

3. **Copy the build artifacts:**

```bash
cp -r target/visualizer /path/to/your/binaries
```

4. **Run the application:**

Execute the file located at: `visualizer/bin/visualizer`

#### Automated

1. **Launch the script:**

```bash
./build.sh
```

2. **Select the correct option:**

When prompted, type B for bundle.

3. **Copy the build artifacts:**

```bash
cp -r target/visualizer /path/to/your/binaries
```

4. **Run the application:**

Execute the file located at: `visualizer/bin/visualizer`

---

## Contributing

Contributions are welcome!

To get started:

1. Clone the repository:

```bash
git clone https://github.com/Riley-dsv/Algo-visualiser.git
```

2. Create a new branch:

```bash
git checkout -b <feature-name>
```

3. Follow the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) specification for your commit messages.

4. Push your branch and open a pull request:

```bash
git push origin <feature-name>
```

---

## Adding an Algorithm

To implement a new algorithm:

1. Create a dedicated branch.
2. Use a straightforward and educational implementation; one-liners are prohibited.
3. Ensure the code closely follows the standard pseudocode logic.
4. Place the Java source code into the relevant category (e.g., `Pathfinding`, `Sort`, `Search`, etc.).
5. Add a script version of the algorithm in the `resources/script` directory, using the naming format:
   `<AlgorithmName>/<language-extension>.txt`
   *Example:* `BubbleSort/py.txt`
6. Add all standard information such as: name, category, average complexity, description, history, and author in the `resources/json/algorithm.json` file.

NOTE: Do not forget to run `mvn clean package` every time you add something new to the resources folder. It might not get added to the classpath otherwise.

---

## Reporting Issues

If you find a bug or issue, please submit it via the [GitHub Issues](https://github.com/Riley-dsv/Algo-visualiser/issues) page.
Bugs will be reviewed as soon as possible.

---

## Notes

Have a better name idea for this project ? 

“Visualizer” / "Algo-Visualizer" are just placeholders, so feel free to open an issue if you have a better idea.

