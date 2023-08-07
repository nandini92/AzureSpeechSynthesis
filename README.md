# AzureSpeechSynthesis
Project to learn using the Azure Speech Synthesis SDK


## Intro

> What is Azure Speech Service? 

The Speech service provides speech to text and text to speech capabilities with a Speech resource. You can transcribe speech to text with high accuracy, produce natural-sounding text to speech voices, translate spoken audio, and use speaker recognition during conversations.

Below are some notes on how to use the Speech service.

## Code Break Down

1. Create an instance of speech configuration with specified subscription key and region.

```javascript
const speechConfig = sdk.SpeechConfig.fromSubscription(
  process.env.SPEECH_KEY,
  process.env.SPEECH_REGION
);
```

2. Represent audio input or output configuration. Audio input can be from a microphone, file, or input stream. Audio output can be to a speaker, audio file output in WAV format, or output stream.

```javascript
var audioFile = "YourAudioFile.wav";
const audioConfig = sdk.AudioConfig.fromAudioFileOutput(audioFile);
```

3. Performs speech synthesis to speaker, file, or other audio output streams, and gets synthesized audio as result. 

```javascript
var synthesizer = new sdk.SpeechSynthesizer(speechConfig, audioConfig);
```

4. Speech Synthesizer can then be used to perform multiple functions including various text-to-speech and speech-to-text functionalities. See methods here https://learn.microsoft.com/en-us/dotnet/api/microsoft.cognitiveservices.speech.speechsynthesizer?view=azure-dotnet