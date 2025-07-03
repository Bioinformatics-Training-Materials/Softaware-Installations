# Setting Up R and RStudio
### 1. Install R

#### Linux
```bash
sudo apt update
sudo apt install r-base
R --version
```

#### macOS  
Download R from [CRAN R Project](https://cran.r-project.org) and install the `.pkg` file.  
Then verify the installation:
```bash
R --version
```

#### Windows  
Download R from [CRAN R Project](https://cran.r-project.org) and install the `.exe` file.  
Then verify the installation:
```bash
R --version
```

### 2. Install RStudio

#### Linux  
Download the RStudio `.deb` file from the [RStudio Download Page](https://posit.co/download/rstudio-desktop/).  
Then install:
```bash
sudo dpkg -i ~/Downloads/rstudio-*.deb
sudo apt --fix-broken install
rstudio
```

#### macOS  
Download the `.dmg` file from the [RStudio Download Page](https://posit.co/download/rstudio-desktop/).  
Drag the RStudio icon into the Applications folder and launch it from your menu.

#### Windows  
Download the `.exe` file from the [RStudio Download Page](https://posit.co/download/rstudio-desktop/).  
Run the installer and follow the setup instructions.  
Launch RStudio from the Start menu.

### 3. Configure RStudio

Verify R version in RStudio:
```r
version
```

## Install essential R packages:

Indivual package installation:

```r
# Install BiocManager if not already installed
if (!requireNamespace("BiocManager", quietly = TRUE))
  install.packages("BiocManager")

# --- CRAN packages ---
install.packages("tidyverse")
install.packages("naniar")
install.packages("dplyr")
install.packages("seqRFLP")
install.packages("ape")
install.packages("phangorn")
install.packages("seqinr")
install.packages("msa")
install.packages("phyloseq")
install.packages("vegan")
install.packages("microbiome")
install.packages("janitor")
install.packages("metagMisc")
install.packages("gplots")
install.packages("ggpubr")
install.packages("picante")
install.packages("psych")
install.packages("schoolmath")
install.packages("igraph")
install.packages("dada2")
install.packages("ggplot2")
install.packages("plotly")
install.packages("corrplot")
install.packages("RColorBrewer")

# --- Bioconductor packages ---
BiocManager::install("Biostrings")
BiocManager::install("DECIPHER")
BiocManager::install("taxonomizr")
BiocManager::install("edgeR")
BiocManager::install("DESeq2")
BiocManager::install("KEGGREST")
```

# Note: If you installed all the above you are done, Nothing more unless you understand the below codes

```r
# Install BiocManager if not already installed
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")

# CRAN packages
cran_packages <- c(
  "tidyverse", "naniar", "dplyr", "seqRFLP", "ape", "phangorn", "seqinr", "msa",
  "phyloseq", "vegan", "microbiome", "janitor", "metagMisc", "gplots", "ggpubr",
  "picante", "psych", "schoolmath", "igraph", "dada2",
  "ggplot2", "plotly", "corrplot", "RColorBrewer"
)

install.packages(cran_packages)

# Bioconductor packages
bioc_packages <- c(
  "Biostrings", "DECIPHER", "taxonomizr", "edgeR", "DESeq2", "KEGGREST"
)

BiocManager::install(bioc_packages)

```

### 4. Optional: Update R and RStudio

#### Update R
```r
update.packages(ask = FALSE)
```

#### Update RStudio  
Download and install the latest version from the [RStudio Download Page](https://posit.co/download/rstudio-desktop/).

### 5. Troubleshooting

#### Dependency Errors (Linux)
```bash
sudo apt --fix-broken install
```

#### R Not Detected in RStudio  
Make sure R is installed and added to your system’s `PATH`.

### 6. Resources

- [R Project](https://cran.r-project.org)
- [RStudio Guide](https://posit.co/resources/)



