## Rust Graph DBs and CLIs

![Untitled 4](https://github.com/nogibjj/graph-databases/assets/58792/aa9943e7-1528-4bfe-9752-bd35e33a8aee)


### Lab Instructions

Add Clap as a dependency in Cargo.toml:
Copy code

```
[dependencies]
clap = "3.2.6"
```

Import Clap and define a CLI struct:
rust

Copy code

```
use clap::Parser;

#[derive(Parser, Debug)]
#[clap(author, version, about)]
struct Args {
  // CLI args here
}
```

Add a CLI argument for the input file:

```
#[clap(short, long)]
input: String
Parse the CLI arguments:
```


```
let args = Args::parse();
Open the input file and populate the graph:

```

```
let file = File::open(args.input)?;
// read file and populate graph

```
Print the results after running the algorithm.


### Additional Challenges:

* Make the output format (text, JSON) configurable via a CLI arg
* Add an optional CLI argument to control the algorithm used
* Allow multiple input files to be passed in
* Read input from stdin instead of a file argument
* Add a subcommand for different modes (analyze, visualize, etc)
* Save output to a file specified on the CLI
* Print help text and handle errors
* Add logging and progress output
