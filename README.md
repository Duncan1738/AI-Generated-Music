# AI-Generated-Music
🎵 AI-Generated Music in Google Colab
This project explores AI-generated music using deep learning models like Magenta and Riffusion. The models generate music based on different styles, moods, and input parameters.

📌 Features
🎼 Generate Melodies – Uses Magenta’s Melody RNN to create MIDI sequences.
🎵 AI-Composed Music – Generates full music pieces based on AI patterns.
🎧 Convert MIDI to Audio – Plays the AI-generated music using FluidSynth.
📝 Text-to-Music – Uses Riffusion to generate music from text prompts.
🔊 Listen in Google Colab – Play the generated music directly in the notebook.
🚀 Getting Started
1️⃣ Install Dependencies
Run this in Google Colab:

bash
Copy
Edit
!pip install magenta midi2audio riffusion
!apt-get install fluidsynth
2️⃣ Generate a Melody (Using Magenta)
python
Copy
Edit
from magenta.music import midi_synth
from magenta.models.melody_rnn import melody_rnn_generate

!melody_rnn_generate \
  --bundle_file=/content/melody_rnn.mag \
  --output_dir=/content/generated \
  --num_outputs=1 \
  --num_steps=128 \
  --primer_melody="[60]"
3️⃣ Convert MIDI to Audio
python
Copy
Edit
from midi2audio import FluidSynth
fs = FluidSynth()
fs.midi_to_audio('/content/generated/output.mid', '/content/output.wav')
4️⃣ Generate Music from Text (Using Riffusion)
python
Copy
Edit
from riffusion.pipeline import RiffusionPipeline
pipeline = RiffusionPipeline()
audio = pipeline.run_text_to_audio("relaxing jazz music with saxophone")
audio.save("/content/riffusion_output.wav")
5️⃣ Listen to the AI-Generated Music
python
Copy
Edit
from IPython.display import Audio
Audio('/content/output.wav')
🎶 Example Outputs
Model	Output
Magenta	Generates structured melodies in MIDI format.
Riffusion	Creates music based on descriptive text prompts.
📌 Use Cases
🎼 AI-generated background music for videos or games.
🎹 Music composition assistance for musicians.
🎧 Creative AI exploration in sound design.

