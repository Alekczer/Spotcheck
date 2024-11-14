import bs4 as bs # pulling data out of HTML and XML files.
import urllib.request # opening and reading URLs
import re # pattern matching
import time

dance = urllib.request.urlopen("https://owaprod-pub.wesleyan.edu/reg/!wesmaps_page.html?stuid=&facid=NONE&crse=003438&term=1251").read()
s_dance = bs.BeautifulSoup(dance)
dance_text = str([i.text for i in s_dance])
danceindex = dance_text.find("Available:") +10
#danceindex
dance_seats = dance_text[danceindex:(danceindex+2)]

current_dance_seats = " 0"
current_monkey_seats = " 0"
#current_dance_seats = " 1" #TESTTT

monkey = urllib.request.urlopen("https://owaprod-pub.wesleyan.edu/reg/!wesmaps_page.html?stuid=&facid=NONE&crse=017370&term=1251").read()
s_monkey = bs.BeautifulSoup(monkey)
monkey_text = str([i.text for i in s_monkey])
monkeyindex = monkey_text.find("Available:") +10
monkey_seats = monkey_text[monkeyindex:(monkeyindex+2)]
monkey_seats

from smtplib import SMTP
import datetime
import smtplib, ssl


port = 465  # For SSL
smtp_server = "smtp.gmail.com"
sender_email = "alekcz2003@gmail.com"  # Enter your address
receiver_email = "alekcz2003@gmail.com"  # Enter receiver address
password = "mscb ictj iekk tjwp"
message = """SEAT OPEN"""

context = ssl.create_default_context()

#While Loop
while 1<2:
  #Intro to Dance Class
  dance = urllib.request.urlopen("https://owaprod-pub.wesleyan.edu/reg/!wesmaps_page.html?stuid=&facid=NONE&crse=003438&term=1251").read()
  s_dance = bs.BeautifulSoup(dance)
  dance_text = str([i.text for i in s_dance])
  danceindex = dance_text.find("Available:") +10
  dance_seats = dance_text[danceindex:(danceindex+2)]
  if dance_seats != current_dance_seats:
    with smtplib.SMTP_SSL(smtp_server, port, context=context) as server:
      server.login(sender_email, password)
      server.sendmail(sender_email, receiver_email, message)
    current_dance_seats = dance_seats
    print("Spot Found!")
    #Monkey Class
  monkey = urllib.request.urlopen("https://owaprod-pub.wesleyan.edu/reg/!wesmaps_page.html?stuid=&facid=NONE&crse=017370&term=1251").read()
  s_monkey = bs.BeautifulSoup(monkey)
  monkey_text = str([i.text for i in s_monkey])
  monkeyindex = monkey_text.find("Available:") +10
  monkey_seats = monkey_text[monkeyindex:(monkeyindex+2)]
  if monkey_seats != current_monkey_seats:
    with smtplib.SMTP_SSL(smtp_server, port, context=context) as server:
      server.login(sender_email, password)
      server.sendmail(sender_email, receiver_email, message)
    current_dance_seats = dance_seats
    print("Spot Found!")

  time.sleep(60) #Wait 1 minute before checking again
