# pyttsx4
pyttsx3 with Some SAPI driver patch to fix some bugs

# How to Use
1. copy these `.py` files
2. Use as function :
  ```python
  import pyttsx4 as pyttsx3
voice_module = 'pyttsx3'


def speakup(text):
	# talk_aloud_temp = False
	if voice_module == 'pyttsx3':
		global engine
		engine = pyttsx3.init()
		# Set properties _before_ you add things to say
		engine.setProperty('rate', 180)
		# Speed percent (can go over 100)
		engine.setProperty('volume', 0.9)  # Volume 0-1
		en_voice_id = "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Speech\Voices\Tokens\TTS_MS_EN-US_ZIRA_11.0"
		# Use female English voice
		engine.setProperty('voice', en_voice_id)
		
		engine.say(text)
		engine.startLoop(False)
		# engine.iterate() must be called inside externalLoop()
		engine.iterate()
		engine.endLoop()

```

