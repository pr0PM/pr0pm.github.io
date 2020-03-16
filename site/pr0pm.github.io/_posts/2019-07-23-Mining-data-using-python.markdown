---
layout: post
title:  "Mining Data Using Python"
categories: jekyll update
---
```python
##################################################################################
##################################################################################
###Dear X, 
### Last semester I faced a very nice website on which our results were published. 
### It was as very nicely layed out UI (you got me right or uhhmm..) with a nice
### text box called Fathers Name to see your results which was the BUG and most 
### of us exploited to see your friend's results.
### But basically it had (and sadly still has) the same bug and which I will 
### be exploiting to mine your data from the website (I do have some privacy 
### policies email me to get a copy ) as no 
### reliable systems for slowing me down are in place like captcha etc.
### 
### Yours Truely,
###                  ____  ____  __  ___
###      ____  _____/ __ \/ __ \/  |/  /
###     / __ \/ ___/ / / / /_/ / /|_/ / 
###    / /_/ / /  / /_/ / ____/ /  / /  
###   / .___/_/   \____/_/   /_/  /_/   
###  /_/
### 
###P.S
### This piece of will be openly avilable in my github account but I will be kind
### enough to remove the website from the code for my personal privacy on a global
### platform AND to protect it from a DDOS attack that won't take a n00b like me 
### to perform in an hour (Including the time to find  
### the right tools) ¯\_(ツ)_/¯
### >>>>>>>>>>   --------------------------   <<<<<<<<<<
###        >>If you done it, it ain't bragging.<<
### >>>>>>>>>>   --------------------------   <<<<<<<<<<                    
####################################################################################
####################################################################################
#   Dependencies
#   -python3
#   -selenium
#   -firefox 68(my browser)
#   -latest geckodriver
#   -basic research skills to learn how to include geckodriver before  
#    running the script.
#    Hint :export PATH=$PATH:/path/to/the/directory/contaning/the/geckodriver
#   -this script was written in linux distro redhat fedora30
######
from selenium import webdriver
from selenium.webdriver.support import ui
from selenium.webdriver.common.keys import Keys

# To open the firefox
fp = webdriver.FirefoxProfile()

# browser preference to download the pdf directly without asking for permission 
fp.set_preference("browser.download.folderList",2)
fp.set_preference("browser.helperApps.neverAsk.saveToDisk", "application/pdf")
fp.set_preference("pdfjs.disabled", True) 


driver=webdriver.Firefox(fp)

# the range from and upto which you have to download the marksheets include 
# the last or last 2 digits from 1 in place of digit below
for i in range(1,digit):
    
    # Open the website
    driver.get("http://the.url.of.the.results.website.in/results")

    #To select the option Btech from the list
    driver.find_element_by_xpath("//*[@id='lstCrs']/option[text()='BTECH']").click()
    
    # To select the textbox for ROLL NO  
    rn = driver.find_element_by_xpath("//*[@id='txtRoll']") 
    
    # To enter the ROLL NO
    # hardcoded for ease
    if i < 10:
        rn.send_keys('ROLL.NO'+str(i)) # For adjusting a zero at the end
    else:
        rn.send_keys('ROLL.NO-a zero at last'+str(i)) 
    
    # Click the show result 
    #driver.find_element_by_xpath("//*[@id='cmdOK']").click()
    #Use accesskey to do th same as above
    driver.find_element_by_tag_name("body").send_keys(Keys.SHIFT+ Keys.ALT + 'M')
    
    # Open the link in a new tab for the next roll number
    driver.execute_script("window.open();")
    
    # switch focus to newly opened tabs
    driver.switch_to.window(driver.window_handles[i])
    # open the url in them
    driver.get('http://the.url.of.the.results.website.in/results')
    

################
################
# Presently I don't have much time left as I also have to extract data 
# from the pdfs' and analyse it so be sure to close all the opened windows of 
# firefox manually or you can reboot XD
# Credits:duckduckgo,stackoverflow,pr0PM and an anonymous friend
#
        
```
