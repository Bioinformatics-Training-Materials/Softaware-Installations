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

Install essential R packages:
```r
install.packages(c("tidyverse", "ggplot2", "dplyr"))
library(ggplot2)
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



