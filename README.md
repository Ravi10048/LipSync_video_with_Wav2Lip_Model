# LipSync_video_with_Wav2Lip_Model


 # Easy-Wav2Lip

## Overview
Aim to Create a LipSync Video with help of Easy-Wav2lip
Easy-Wav2Lip is a powerful tool designed to simplify the process of lip-syncing videos by leveraging the capabilities of Wav2Lip and GAN-based upscaling. This tool is specifically designed to run seamlessly within a Google Colab environment.

## Easy-Wav2Lip improves Wav2Lip video lipsyncing making it:

## Easier:
* Simple setup and execution - locally and via colab.
     * no messing around manually downloading and installing prerequesits
     * Google Colab has only 2 cells to execute
     * Windows users only need one file to install, update and run.
* Well documented options below.
     * No more wondering what anything does!

## Faster:
For my 9 second 720p 60fps test clip via Colab T4:
| Original Wav2Lip | Easy-Wav2Lip |
|:-------|:-----|
| Execution time: 6m 53s | Execution time: 56s |

That's not a typo! My clip goes from almost 7 minutes to under 1 minute!

The tracking data is saved between generations of the same video, saving even more time:
| Easy-Wav2Lip on the same video again |
|:-----|
| Execution time: 25s |

## Better looking:

Easy-Wav2Lip fixes visual bugs on the lips:

[![Comparison gif](https://github.com/anothermartz/Easy-Wav2Lip/releases/download/Prerequesits/wav2lipcomparison.gif)](https://github.com/anothermartz/Easy-Wav2Lip/releases/download/Prerequesits/wav2lipcomparison.gif)

3 Options for Quality:
* Fast: Wav2Lip
* Improved: Wav2Lip with a feathered mask around the mouth to restore the original resolution for the rest of the face
* Enhanced: Wav2Lip + mask + GFPGAN upscaling done on the face

[![Comparison gif](https://github.com/anothermartz/Easy-Wav2Lip/releases/download/Prerequesits/JPComparison.gif)](https://github.com/anothermartz/Easy-Wav2Lip/releases/download/Prerequesits/JPComparison.gif)




## Getting Started

### For the easiest and most compatible way to use this tool, use the Google Colab version so copy colab code:

### Google Colab:

### Step 1: Setup Easy-Wav2Lip
Run the provided code in the first cell of your Colab notebook to ensure a smooth setup process. This code performs the following tasks:

- Checks if Easy-Wav2Lip is already installed and installs it if necessary.
- Verifies GPU availability and prompts to mount Google Drive if your files are stored there.
- Clones the Easy-Wav2Lip repository, installs prerequisites, and sets up the necessary directories.

### Step 2: Lip-Sync Your Video
Follow these steps to lip-sync your video:

1. **Specify File Paths:**
   - Set the file paths for your video and audio files.

2. **Choose Lip-Syncing Quality:**
   - Select the quality of lip-syncing from options like "Fast," "Improved," "Enhanced," or "Experimental."

3. **Set Output Resolution:**
   - Specify the output resolution, choosing from options like "half resolution," "full resolution," or a custom "480."

4. **Use Previous Tracking Data (Optional):**
   - Speed up the processing of multiple videos by using tracking data from a previous session. Enable or disable as needed.

5. **Advanced Tweaking:**
   - Fine-tune advanced parameters to customize your lip-syncing experience, including padding, mask size, feathering, and more.

### Step 3: Run Lip-Sync
Upon executing the script, Easy-Wav2Lip performs the following tasks:

- Writes your configuration to a `config.ini` file.
- Runs the lip-syncing process using Wav2Lip and, if selected, GAN-based upscaling.
- Displays a preview of the lip-synced video if requested.

## Advanced Tweaking

Customize your lip-syncing experience further by adjusting the following advanced parameters:

- **Padding Values:**
  - Adjust padding for video processing in the Up, Down, Left, and Right directions.

- **Mask Parameters:**
  - Set the mask size, feathering around the mask, enable mouth tracking, and enable debug mode for the mask.

## Best practices:
* The best results come from lining up the speech to the actions and expressions of the speaker before you send it through wav2lip!

Video files:
* Must have a face in all frames or Wav2Lip will fail
* Crop or mask out faces you don't want to lipsync or it'll choose randomly.
* Use h264 .mp4 - other file types may be supported but this is what it outputs as
* Images are currently untested.
* Use a small file in every way (try <720p, <30 seconds, 30fps <b></b> etc. - Bigger files may work but are usually the reason it fails)
* For your first try, use a really tiny clip just to get used to the process, only once you're familiar should you try bigger files to see if they work.

Audio files:
* Save as .wav and the same length as your input video.
* NOTE: I've noticed that about 80ms gets cut from the processed video/audio and I'm not sure how to fix this, so make sure you have a little extra than what you actually need!
* You can just encode it into your video file and leave vocal_path blank, but this will add a couple of seconds to the processing time as it splits the audio from the video
* <b>OR</b>
* Select your audio file separately
* I'm not certain what filetypes are supported, at least .wav and .mp3 work.

## Troubleshooting
If you encounter any issues during setup or the lip-syncing process, refer to the troubleshooting section in the code for potential solutions.

Feel free to modify the README to include additional information or instructions for users.



