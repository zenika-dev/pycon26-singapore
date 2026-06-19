# PyCon26 Singapore Presentation Resources

## Stop training, start prompting: The future of dynamic video surveillance

For years, object detection in computer vision has been trapped within the rigid, expensive bottleneck of "closed-set" models, detecting only the specific objects they were explicitly trained on. When applied to video surveillance, this necessitates a costly and lengthy cycle of data collection, labelling, and retraining every time a new operational threat or business requirement emerges.

This session introduces a paradigm shift: Open-Vocabulary Video Intelligence. Leveraging the latest YOLOE-26 models, we move beyond fixed categories into a unified semantic space where the camera "understands" language. Attendees will see how to transform static surveillance into a dynamic, promptable engine that can detect "anything" using simple text or visual references using models "out of the box".

---

## Running the Demo Notebook

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/zenika-dev/pycon26-singapore/blob/main/PyCon26-demo.ipynb)

### Prerequisites

Before running the notebook, ensure the following are in place:

1. **Google Account** — required to access Google Colab and Google Drive.
2. **GPU Runtime** — the notebook requires a CUDA-capable GPU. In Colab, go to **Runtime > Change runtime type** and select a GPU accelerator (e.g. T4 or L4).
3. **Media files on Google Drive** — place the demo media files you wish to run the demo on and update the following paths in the notebook accordingly:
   - `yellow-suitcase-14.mp4` — used in Demo 1
   - `street-fight.mp4` — used in Demo 2
   - `cam1.m4v`, `cam4.m4v` — used in Demo 3
   - `elderly_lady.png` — visual prompt reference image for Demo 3

### Steps

1. Click the **Open in Colab** badge above (or open [PyCon26-demo.ipynb](PyCon26-demo.ipynb) directly).
2. In Colab, go to **Runtime > Change runtime type** and select a **GPU** hardware accelerator.
3. Run the **Setup** section cells in order:
   - The GPU check cell will confirm your accelerator is active.
   - The install cell will install `ultralytics`, `opencv-python-headless`, and `ffmpeg-python`.
   - The Google Drive mount cell will prompt you to authorise access — this is required to load the media files.
4. Run the **Define functions** and **Load YOLOE-26 model** cells to initialise inference.
5. Run each demo section (Demo 1, 2, 3) sequentially. Each demo will:
   - Run YOLOE-26 inference on the source video.
   - Save an annotated output video.
   - Display the result inline in the notebook.

### Demos

| Demo | Prompt type | Description |
|------|-------------|-------------|
| 1 | Text (semantic) | Detect a `"yellow suitcase"` in surveillance footage |
| 2 | Text (complex concept) | Detect `"persons fighting"` — a behavioral interaction |
| 3 | Visual prompt | Search for a specific individual across two camera feeds using a reference image |
