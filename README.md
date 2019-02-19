# instaRanalysis
Guide and requirements for analysing posts on Instragram
1. Install required software<br/>
2. Scraping<br/>
3. Data manipulation in R and export to Microsoft Excel<br/>

## Required software:
* Python
* Instagram Scraper
* R
* RStudio (optional)

### Install Python on Windows:
1. [Download](https://www.python.org/downloads/release/python-2715/) <br/>
2. Open Command Prompt (on some corporate networks you need to run the command prompt as administrator)
3. `setx PATH "%PATH%;C:\Python34\Scripts"`

### Install Python on Mac:
1. Install Xcode tools <br/>
    1. Open Terminal and copy/paste the following code:<br/>
    `xcode-select --install`

2. Install Homebrew <br/>
    1. Paste following code into the terminal window:<br/>
    `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
    2. Add Homebrew to your path. Paste following code into the terminal windows: <br/>
    `export PATH="/usr/local/bin:/usr/local/sbin:$PATH"`
  
3. Install Python (2.7) via terminal:<br/>
´brew install python@2´
    1. Add Python to your path:<br/>
    `export PATH="/usr/local/opt/python@2/libexec/bin:$PATH"`

### Install Instagram scraper:
1. Open command prompt (windows) or terminal (mac)
2. Paste the following command: <br/>
`pip install instagram-scraper`

### Install R and RStudio
1. [Download R](https://cran.r-project.org/)
2. [Download RStudio](https://www.rstudio.com/products/rstudio/download/)
3. Install packages for R:<br/>
    - jsonlite
    - stringr
    - tidyr
    - dplyr
    - openxlsx
    - plyr
    - repurrrsive
    - purrr
    - webshot
  
    e.g.:<br/>
    ´install.packages("jsonlite")
  
    1. Install PhantomJS for R:
    `webshot::install_phantomjs()`

## Run Instagram scraper:

*To scrape a user's account:*<br/>
`Instagram-scraper username -u yourusername -p yourpassword –-media-metadata –-comments –d path`

*To scrape a hashtag:*<br/>
`instagram-scraper hashtag --tag`

Check full documentation [here](https://github.com/rarcega/instagram-scraper)
