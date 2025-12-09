📰 AI News Video Generator – Automated End-to-End Pipeline

Task 1 Submission | AI/ML Internship Project

This project implements a fully automated pipeline that transforms a news article into a polished vertical documentary/news-style video using a combination of Natural Language Processing, Text-to-Speech, Image Processing, and Video Editing techniques.

The final output is a 1080×1920 vertical MP4 video suitable for YouTube Shorts, Instagram Reels, Facebook Stories, and TikTok.

----------------------------------------------------------------------------------------------------------------------------------------------------------------
📌 Key Features

🔍 News scraping for trending articles

🧠 AI-generated narration using OpenAI

🗣️ Voice-over generation using Google TTS

🎨 Synthetic cinematic backgrounds using PIL (no API cost)

📝 Caption rendering without ImageMagick

🎬 Video assembly using MoviePy

📤 Exports video & uploads to Google Drive automatically

💸 Runs entirely FREE — no paid APIs required

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
⚙️ Technologies & Libraries Used
AI & Language Generation

OpenAI ChatCompletion API
Used to generate structured 180-word documentary/news-style narration based on the scraped article summary.

Audio Generation

Google Text-to-Speech (gTTS)
Generates clean English narration audio (.mp3) directly from the script.

Image Generation

Pillow (PIL)
Creates cinematic gradient backgrounds + renders caption PNGs (replacing ImageMagick).

Video Creation

MoviePy
Used to assemble:

background frames

caption overlays

audio narration

slow zoom cinematic transitions

Utilities

Python libraries: json, os, requests, tqdm, textwrap

Google Colab for runtime environment

Google Drive for output storage



----------------------------------------------------------------------------------------------------------------------------------------

🧠 End-to-End Workflow
1️⃣ Step 1 — News Scraping

Trending news articles were fetched using a Python scraping pipeline.

Each article was stored with:

title

summary

published

source

url

Results exported to:
/content/trending_news.json

2️⃣ Step 2 — Narration Generation (OpenAI)

For each article summary:

A structured AI prompt generates:

A 180-word documentary-style narration

Professional tone

Clear storytelling structure

Output saved to:
/content/generated_scripts.json

3️⃣ Step 3 — Voice Generation (gTTS)

Narration text passed to Google TTS

Produces high-quality MP3 narration

Output stored as:
/content/assets/narration.mp3

4️⃣ Step 4 — Background Image Generation

To avoid paid image APIs (Pixabay, OpenAI Images, Runway, etc.):

Generated three synthetic cinematic gradient images using Pillow

These backgrounds emulate:

documentary tones

news ambience

visual smoothness

No external API calls required.

5️⃣ Step 5 — Caption Rendering WITHOUT ImageMagick

MoviePy normally uses ImageMagick for text rendering.
Since Colab does not support ImageMagick by default:

We replaced TextClip with PIL-rendered caption PNGs

Captions automatically:

wrap text

center-align

render on dark translucent rounded rectangles

This ensures:
✔ No dependency issues
✔ 100% compatibility in Colab
✔ Clean, readable subtitles

6️⃣ Step 6 — Final Video Assembly

Using MoviePy:

Each background image becomes a clip segment

Clips receive Ken Burns zoom-in animation

Caption PNG is overlaid for each segment

All segments concatenated

Final audio synced perfectly

Output rendered in 1080×1920 vertical format

Output file:
/content/final_moviepy_video_no_imagemagick_v2.mp4

7️⃣ Export to Google Drive

With:

from google.colab import drive
drive.mount('/content/drive')
!cp "/content/final_moviepy_video_no_imagemagick_v2.mp4" "/content/drive/MyDrive/"


The final video is uploaded directly for evaluation.

--------------------------------------------------------------------------------------------------------------------------

🎯 Skills Demonstrated

Prompt Engineering

Python scripting & automation

AI-based text and audio generation

Video editing with MoviePy

PIL image rendering

Debugging & optimization

Workflow design in Google Colab

Handling missing API dependencies (ImageMagick removal)

End-to-end system thinking


-------------------------------------------------------------------------------------
🚀 Possible Extensions
f needed, the project can be extended to:

Add background music

Use real AI images from API keys (Pixabay, Runway, OpenAI)

Create multi-scene videos

Implement batch generation for multiple articles

Use a better TTS like ElevenLabs

Add animated lower-thirds or ticker bars

--------------------------------------------------------------------------------------------

🙏 Acknowledgements

Thank you for reviewing this submission.
This project demonstrates a complete AI media generation pipeline developed entirely in Python, fully functional, and cost-optimized.
