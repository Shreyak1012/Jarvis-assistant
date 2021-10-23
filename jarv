import pyttsx3
import datetime
import speech_recognition as sr
engine=pyttsx3.init()


def speak(audio):
    engine.say(audio)
    engine.runAndWait()


def time():
    time=datetime.datetime.now().strftime('%I:%M:%S')
    speak('the current time is')
    speak(time)

def date():
    year=int(datetime.datetime.now().year)
    month=int(datetime.datetime.now().month)
    date=int(datetime.datetime.now().day)
    speak('today is')
    speak(date)
    speak(month)
    speak(year)

def wishme():
    speak('hey')
   
    time()
   
    date()
    hour=datetime.datetime.now().hour
    if hour >=6 and hour<12:
        speak('good morning')
    elif hour >=12 and hour<18:
        speak('good afternoon')
    elif hour >=18 and hour<21:
        speak('good evening') 
    else:
        speak('good night')    
    speak('how can i help you')

def takecommand():
    r=sr.Recognizer()
    with sr.Microphone() as source:
        print('listening...')
        r.pause_threshold=1
       
        audio=r.listen(source,phrase_time_limit=5)

    try:
        print('recognising...')
        query=r.recognize_google(audio,language='en-in')
        print(query)

    except Exception as e:
        print('e')
        speak('say it again please')
        return 'none'
    return query


if __name__=='__main__':
    wishme()
    while True:
        query=takecommand().lower()

        if 'time' in query:
            time()
            
        elif 'date' in query:
            date()

        elif 'offline' in query:
            quit()
            
