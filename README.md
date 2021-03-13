# PROJECT-Text-search-and-replace
    import pandas as pd 
    import numpy as np
    import re
     
    pip install webvtt-py
    import webvtt
    text = webvtt.read('captions_text.vtt')
    text=str(text)
    text
     
    text = text.replace('\n','')
    pattern=r'\d\d:\d\d{1,8}:\d\d.\d\d\d '
    regex_timestamps = re.compile('%s'%pattern)
    regex_timestamps.findall(text)
     
    newtext = regex_timestamps.sub('',text)
    newtext
     
    newtext = newtext.split()
    for i in range(len(newtext)):
        if len(newtext[i])==4:
            newtext[i]=newtext[i][0]+ '***'
        newtext
     
    cleantext = ' '.join(newtext)
    cleantext
