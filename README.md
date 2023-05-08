# Python_Project-2
# RSS Feed with multiple links


import feedparser
import requests

url = [str(i) for i in input().split()]

'''
'https://timesofindia.indiatimes.com/rssfeedstopstories.cms'
'https://timesofindia.indiatimes.com/rssfeeds/296589292.cms'
'https://timesofindia.indiatimes.com/rssfeeds/54829575.cms'
'''

for u in url:

    r = requests.get(u)

    news  = feedparser.parse(r.text)

    for item in news['entries']:
        tit = item['title']
        print(tit.upper())
        print(item['description'])
        print(item['link'])
        print()
