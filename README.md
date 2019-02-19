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
3. `setx PATH "%PATH%;C:\Python27\Scripts"`

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
`brew install python@2`
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
    `install.packages("jsonlite")`
  
    1. Install PhantomJS for R:<br/>
    `webshot::install_phantomjs()`

## Run Instagram scraper:

To scrape a user's account:<br/>
`instagram-scraper username -u yourusername -p yourpassword –-media-metadata –-comments –d path`

To scrape a hashtag:<br/>
`instagram-scraper hashtag --tag`

The program will produce images for each instagram post and a json file with all metadata (tag, post, likes, comments, etc.).

Check full documentation [here](https://github.com/rarcega/instagram-scraper)

## Data manipulation in R
This operation outputs a readable Microsoft Excel file.

1. Download this repos and save to a location where the scraper downloaded images and json file
2. Open RStudio
3. Create new project and choose the same save location
4. Change the variable `input` to json filename (without the .json extension)
    1. E.g. `input <- "somejsonfile"`
5. Change the variable `fileLoc` to the the full path of where the images from the scrape are saved:
    1. E.g. `fileLoc <- "C:\myfiles\"` 
    2. Works also with online drives such as Microsoft Onedrive or Sharepoint:
        - E.g. `fileLoc <- https://corpname.sharepoint.com/Sites/sitename/Shared%20Documents/images/`
6. Run both "chunks" (wait for one to finish before you start the second)
    1. the command: <br/>
    `webshot(c(df$url),delay = 3, file="InstaShot.png")` <br/>
    downloads screenshots of instagram post. This process might take a very long time for especially big datasets. This command may also exit with an error saying it cannot open a specific link. Usually this can be resolved by running this line again.
    
