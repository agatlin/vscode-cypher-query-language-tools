# Cypher Query Language Tools for Neo4j

## Description

This [Visual Studio Code](https://code.visualstudio.com/) extension provides basic syntax highlighting, code completion (coming soon), and related tools for [Neo4j's](http://neo4j.com/) [Cypher Query Language](http://neo4j.com/developer/cypher/) with support for Neo4j's [Awesome Procedures on Cypher (APOC)](https://neo4j.com/docs/labs/apoc/current/), [Graph Algorithms](https://neo4j.com/docs/graph-algorithms/current/), and [GraphQL](https://neo4j.com/labs/grandstack-graphql/) libraries.

This extension also works with Cypher files conforming to the [OpenCypher](https://www.opencypher.org/) standard such as those from [AnzoGraph](https://www.cambridgesemantics.com/product/anzograph/), [Memgraph](https://memgraph.com/), [RedisGraph](https://oss.redislabs.com/redisgraph/), [SAP Hana Graph](https://help.sap.com/viewer/f381aa9c4b99457fb3c6b53a2fd29c02/2.0.00/en-US/4c3ee700e7a8458baed3f1141d9380f3.html), or [OpenCypher for Apache Spark (Codename: Morpheus)](https://github.com/opencypher/morpheus). Please note that none of these tools yet provide a complete Cypher implementation.

## Installation

The simplest way to use this extension is to install it from the VS Code Extension Marketplace from within VS Code.

### Installation From Within VSCode

1. From within VS Code, click on the ```extensions icon``` in the left sidebar, press ```Ctrl-Shift-X``` (on Windows or Linux) or ```Cmd-Shift-X``` (on Mac), or click ```View ->  Extensions``` from the main navigation bar at the top of the screen. Any of these should bring up the Extensions Marketplace search box.
2. Type ```Cypher Query Language Tools for Neoj```.
3. Click ``Install``.

### Installation from the VS Code Marketplace

1. Go to  https://marketplace.visualstudio.com/items?itemName=AnthonyJGatlin.vscode-cypher-query-language-tools
2. Click the ```Install``` button. You will be prompted to open Visual Studio Code.

### Installation from the Command Line (using a VSIX file)

1. Download the VSIX file from the GitHub repository. (https://github.com/agatlin/vscode-cypher-query-language-tools/blob/master/vscode-cypher-query-language-tools-0.1.1.vsix)
2. Open a shell or command prompt.
3. Change to the directory where the extension file was downloaded.
4. Execute ```code vscode-cypher-query-language-tools-0.1.1.vsix<enter>```

More information on installing a VSIX file can be found at https://vscode-docs.readthedocs.io/en/stable/extensions/install-extension/.

### Installation from source (for editing/debugging)

Theoretically, the version of the extension in the VS Code Marketplace will always be the same as what is in the master [GitHub repository](https://github.com/agatlin/vscode-cypher-query-language-tools). If for any reason, you would like to run the extension directly (as for testing), you can do the following:

1. Clone the Git repository. ```git clone https://github.com/agatlin/vscode-cypher-query-language-tools.git```.
2. Open a shell window for your particular operating system. 
3. ```cd``` into the ```vscode-cypher-query-language-tools``` directory.
4. Execute the command ```code . <enter>``` to open VS Code in the current directory.
5. Press ```F5``` to bring up an Extension Shell debugging window

## Usage

This extension is automatically active whenever files with ```cypher```, ```cql```, or ```cyp``` extensions are loaded. (Per the [Cypher Style Guide](https://neo4j.com/developer/cypher-style-guide/), ```cypher``` is the preferred file extension for Cypher files.)

You may also force activation of the extension on any file by overriding the language mode for any open file. This can be done by any of the following:

1. Clicking on the file type by in the lower navigation bar and then selecting ```Cypher Query Language (Cypher)```.
2. Click ```Ctrl+K, M``` (or ```Cmd-K, M``` on Mac) to bring up the Language Mode dialog. Select ```Cypher Query Language (Cypher)``` from the list of available languages.
3. Press ```Ctrl-Shift-P``` (or ```Cmd-Shift-P``` on Mac) to bring up the Command Palette. Then, select the ```Change Language Mode``` command. Select ```Cypher Query Language (Cypher)``` from the list of available languages.

## Issues

Any bugs or other issues can be submitted through the [Issues](https://github.com/agatlin/vscode-cypher-query-language-tools/issues) section of this repository. If you feel comfortable in correcting the issue, please feel free to make the correction and submit a pull request.

## Roadmap

The initial version of this extension is very simple but has ambitious long term goals. Some of the planned functionality is described below.

- Review existing functionality to find gaps in implmented Cypher keywords (including deprecated keywords) and functions for syntax highlighting.
- Develop a matrix of supported Cypher keywords by graph database vendor and version.
- Allow users to choose syntax highlighting and other functionality based on graph database vendor and version.
- Provide embedded syntax highlighting for SQL in commands such as [apoc.load.jdbc](http://neo4j-contrib.github.io/neo4j-apoc-procedures/3.5/database-integration/load-jdbc/).
- Provide intelligent quote replacement and escaping. (Cypher statements frequently include quotes within quotes within quotes as with apoc.load.jdbc wrapped inside apoc.periodic.iterate.)
- Support user-configurable options for syntax highlighting and other functionality.
- Collect information for all functions including method signatures, descriptions, usage examples, links to documentation and other references, and links to replacement methods for deprecated items.
- Provide access within the extension to code completion, documentation, examples, and links to official Neo4j documentation for all Neo4j, APOC, Graph Algorithms, and GraphQL functions and procedures, links to outside references (where appropriate), and links to replacement functions for deprecated items.
- Provide on-hover documentation for Cypher clauses and functions and those of other Neo4j libraries.
- Provide code snippets and keyboard shortcuts for useful Cypher queries. (This includes many data profiling and administrative queries.)
- Provide support for auto-complete of properties and labels which can be reflected through db.labels() and db.properties().
- Implement FlexiSearch module to provide basic search functionality across library procedures, descriptions, and other documentation. (Finding the right procedure or function now can be confusing for new users.)
- Provide the ability to connect to running Neo4j instances through the bolt JavaScript driver.
- Provide the ability to store connection information for multiple Neoj databases.
- Provide the ability to integrate directly with the Cypher Shell as a VS Code Terminal.
- Provide the ability to run queries through Visual Studio Code.
- Provide the ability to store common parameters for re-use in multiple queries.
- Provide a superset of Cypher commands such as a USING statement which allows users to choose which connection should be used for running a specific query or set of queries.
- Provide support for named paramterized commands which can be reused as functions within other commands.
- Provide support for snippet sets or snippet groups where users can quickly run sets of related queries. 
Provide support for the notion of "chainable Cypher snippet groups" where the output of one snippet can be piped into another snippet, exported, or stored for later use.
- Implement a pluggable architecture so other libraries in the Neo4j ecosystem, like those from GraphAware can also benefit from code completion and built-in hover documentation.
- Provide the ability to download and run Docker images for Enterprise or Community Edition along with relevant version-associated plugins for APOC, the Graph Algorithms Library, Graph QL, and from elsewhere in the Neo4j ecosystem.
- Provide basic capabailities to wrap queries in EXPLAIN, PROFILE so queries can be better analyzed and timed.
- Provide :begin, :commit to support to database changes can be tested and rolled back if desired.
- Provide code re-formatting functionality to reformat code according to the Cypher Style Guide.
- Implement a true Language Server and Language Client for Cypher. Implementation of an actual Language Server/Language Client architecture will allow the code to run within Visual Studio (not just VS Code) as well as other Language Server compliant platforms.
- Begin preparations for addingGraph Query Language (GQL) support.
- Provide basic graph visualization and exploration using one of the available Force Directed Graph JavaScript libraries. 

Coming Soon...

Code completion is under development should be available sometime around October 4th or 5th.

## Contribute

We definitely could benefit from and would welcome help in building out this extension. There are many areas to contribute beyond actually writing code. If you are interested in working on this extension, please don't hesitate to jump in.

Pull requests are extremely welcome.

## General Cypher and Neo4j Help

The Neo4j/Cypher community is very active and helpful. Believe me on this! They have been absolutely amazing in helping me to come up to speed on Cypher and Neo4j. I highly recommend joining the the [Neo4j Community Site](https://community.neo4j.com/?_ga=2.201721425.1386257111.1569456106-1047916977.1567363285).

## Learning Cypher

If you are new to Cypher and would like a little guidance, I recommend you start with Ryan Boyd's short video series, [An Introduction to Graph Databases](https://www.youtube.com/watch?v=5Tl8WcaqZoc&list=PL9Hl4pk2FsvWM9GWaguRhlCQ-pa-ERd4U) on YouTube. This series will provide a good foundation for moving deeper into Cypher. Ryan's videos are very easy to follow.

William Lyon also has a great [Introduction to Cypher](https://www.youtube.com/watch?v=pMjwgKqMzi8&t=7s) video tht is worth a watch or two.

There are many great videos on the [Neo4j YouTube Channel](https://www.youtube.com/channel/UCvze3hU6OZBkB1vkhH2lH9Q), but the sheer volume of content can be overwhelming for a someone new to graphs. As you progress, this channel will become an invaluable resource.

Neo4j also has several free courses available through their [Graph Academy](https://neo4j.com/graphacademy/online-training/). Of particular interest is the [Introduction to Neo4j](https://neo4j.com/graphacademy/online-training/introduction-to-neo4j/) course which only takes a few hours to complete.

There are also many great resources on the [Neo4j Developer site](https://neo4j.com/developer/) and the [Neo4j Documentation Site](https://neo4j.com/docs/).

Of course, no reference list would be complete without mentioning the super-handy [Cypher Reference Card](https://neo4j.com/docs/cypher-refcard/current/)

Beyond these, Google will present you with many additional free learning options.

## Credits

This extension is based on previous code extensions from [Ionut Botizan](https://github.com/ionut-botizan/vscode-cypher-ql) and [Jake Boone](https://github.com/jakeboone02/cypher-query-language). Both of these extensions were based on TextMate language packages for [Atom](http://atom.io) ([language-cypher](https://github.com/tobiashm/language-cypher)) and [Sublime Text](https://www.sublimetext.com/) ([Cypher](https://github.com/kollhof/sublime-cypher)).
