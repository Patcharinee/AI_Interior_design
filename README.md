# 🪄: AI Interior Design

This Colab notebook demonstrates how AI can help redesign and visualize your room based on an inspiration image and a simple text description. You can describe a design style and upload a reference inspiration image, and the AI will transform your room while preserving its layout and structure.

### Google colab notebook link:
https://colab.research.google.com/github/Patcharinee/AI_Interior_design/blob/main/AI_Interior_design.ipynb

<img width="1536" height="704" alt="AI_interior_design_example" src="https://github.com/user-attachments/assets/3b3ee95b-fe98-48ca-9ba5-1098f3a09026" />

## What It Can Do

✅ Transform your room into different styles using AI  
✅ Preserve the original layout using structure-detection  
✅ Use a **reference image** to guide the design  
✅ Generate photorealistic concepts — fast!

---

## Under the Hood — How it works

This project combines several powerful AI tools in a creative pipeline:

### Stable Diffusion + Custom Model

We use a fine-tuned version of **Stable Diffusion** called **[InteriorDesignSuperMix](https://civitai.com/models/85691/interiordesignsupermix)** — a model specialized for generating high-quality, photorealistic interior scenes.  
It helps ensure the output fits real-world room aesthetics.

### ControlNet + MLSD (Mobile-optimized Line Segment Detection)

To **preserve the room layout** (walls, edges, furniture positions), we use **ControlNet** with **MLSD (Mobile-optimized Line Segment Detection)**:

- **MLSD** analyzes the input photo and extracts clean straight line maps (white straight lines on a black background)
- These lines act like a "blueprint" that guides the AI, so it doesn’t distort the room structure when redesigning

### IP-Adapter (Image Prompt Adapter)

Besides text prompts, the tool uses a **style reference image** via **IP-Adapter**. This allows the AI to "look at" another reference room image and apply a similar aesthetic to your room photo.

For example: Want your bedroom to look similar to a Scandinavian living room that you like? Just upload an image of one!

---

## Project Structure

- `AI_Interior_design.ipynb`: The main Colab notebook
- `/AI_Interior_design_data/`: Example room and style images
- `/Checkpoints/`: Model checkpoints downloaded during runtime

---

## How to Use

1. Open the notebook in Google Colab  
   [Open Notebook](https://colab.research.google.com/github/Patcharinee/AI_Interior_design/blob/main/AI_Interior_design.ipynb)

2. Upload:
   - A photo of your room as "original_image" and change the file path accordingly (original_image = load_image("YOUR FILE PATH HERE"))
   - A reference image of your preferred design style as "style_image" and change the file path accordingly (style_image = load_image("YOUR FILE PATH HERE"))

3. Type a description of the style you want in "text_prompt" 
   e.g., `"a cozy Scandinavian bedroom"`

4. Run the notebook cells step-by-step

5. Download your newly designed room!

---

## 🔧 Technologies Used

| Tool | Purpose |
|------|---------|
| Stable Diffusion | Image generation |
| InteriorDesignSuperMix | Fine-tuned SD model for interior design |
| ControlNet (MLSD) | Preserves structural layout using line maps |
| IP-Adapter | Enables image-based style transfer |
| CLIP Vision | Image embedding and comparison |
| Transformers & Diffusers | Open-source AI model libraries |
| PyTorch | Core deep learning framework |

---

## Limitations

- Results are AI-generated and **conceptual** – great for inspiration, but not exact measurements
- Works best with clear, bright photos of rooms
- Some styles or inputs may result in less realistic results (trial & error helps!)

---

## Acknowledgements

- [ControlNet and original room image sample by lllyasviel](https://github.com/lllyasviel/ControlNet)
- [InteriorDesignSuperMix on CivitAI](https://civitai.com/models/85691/interiordesignsupermix)
- [IP-Adapter by h94](https://github.com/tencent-ailab/IP-Adapter)
- [Inspiration style images from Pinterest](https://www.pinterest.com/)

---
