# Pre-Commit PlantUML

## Getting Started

1. Install Java
2. Graphviz (Optional)
3. Go to your project directory and download a copy of plantuml.jar (https://sourceforge.net/projects/plantuml/files/plantuml.jar/download)
4. Go to your project `.git/hooks` folder
   1. Download a copy of the plantuml.pre-commit.sh
      ```
      curl -O https://raw.githubusercontent.com/weikangchia/pre-commit-hooks-plantuml/main/plantuml.pre-commit.sh
      ```
   2. Make the file executable
      ```
      chmod +x plantuml.pre-commit.sh
      ```
   3. Open your `pre-commit` file and add the following code to run plantuml.pre-commit.sh
      ```
      #!/bin/bash
      
      ...

      "$(git rev-parse --git-dir)/hooks/plantuml.pre-commit.sh"
      ```

## How It Works

During the commit of any PlantUML file (file with extension: .puml), if we
- add or update a PlantUML file, a PlantUML image will be generated based on the file and commit
- delete a PlantUML file, existing PlantUML image will be deleted together in the commit