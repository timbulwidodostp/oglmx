# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Estimation of Ordered Generalized Linear Models Use Package oglmx With (In) R Software
# Fit Ordered Generalized Linear Model Use Package oglmx With (In) R Software
install.packages("readxl")
install.packages("httr")
install.packages("oglmx")
library("httr")
library("readxl")
library("oglmx")
# Import Data Excel Into R From Github Olah Data Semarang (timbulwidodostp)
github_link <- "https://github.com/timbulwidodostp/oglmx/raw/main/oglmx/oglmx.xlsx"
temp_file <- tempfile(fileext = ".xlsx")
req <- GET(github_link, 
# authenticate using GITHUB_PAT
authenticate(Sys.getenv("GITHUB_PAT"), ""),
# write result to disk
write_disk(path = temp_file))
oglmx <- readxl::read_excel(temp_file)
# Estimation of Ordered Generalized Linear Models
results.oprob<-oglmx(y~x1+x2,data=oglmx,link="probit",constantMEAN=FALSE,constantSD=FALSE,delta=0,threshparam=NULL)
coef(results.oprob)
summary(results.oprob)
# Estimation of Ordered Generalized Linear Models Use Package oglmx With (In) R Software
# Fit Ordered Generalized Linear Model Use Package oglmx With (In) R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished
