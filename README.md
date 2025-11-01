# FLUX.1-Kontext-Dev: Free Image Editing via Hugging Face

Transform images with AI-powered natural language instructions using FLUX.1-Kontext-Dev's free Hugging Face Gradio client. This repository provides a simple Python interface for powerful, instruction-based image editing.

## What is FLUX.1-Kontext-Dev?

FLUX.1-Kontext-Dev is a cutting-edge 12-billion parameter text-to-image transformer from Black Forest Labs. It specializes in precise, instruction-driven image modifications while maintaining exceptional consistency in character identity and visual style.

### Key Capabilities

- **Natural Language Editing**: Modify images using simple text instructions
- **Identity Preservation**: Maintains subject characteristics and style integrity across edits
- **Iterative Refinement**: Apply sequential edits with minimal quality degradation
- **Open Research**: Released with open weights under a non-commercial license

## Quick Start

### Prerequisites

Ensure Python is installed, then install required dependencies:

```bash
pip install gradio_client pillow matplotlib requests
```

### Installation

Clone the repository and navigate to the project directory:

```bash
git clone https://github.com/SakibAhmedShuva/FLUX.1-Kontext-Dev-Free-Usage-with-Hugging-Face.git
cd FLUX.1-Kontext-Dev-Free-Usage-with-Hugging-Face
```

### Usage

1. **Open the Notebook**: Launch `kontext_hf.ipynb` in Jupyter Notebook or JupyterLab

2. **Configure Your Settings**: Locate and modify the configuration block:

```python
# Optional: Add your Hugging Face token for improved stability
HF_TOKEN = None  # Set to "hf_your_token_here" if available

# Generate edited image
result, seed = generate_with_flux(
    image_path=r"path/to/your/image.png",  # Path to input image
    prompt="your editing instruction here",  # Describe desired changes
    guidance=2.5,    # Prompt adherence (higher = stricter)
    steps=30,        # Generation steps (more = better quality)
    hf_token=HF_TOKEN
)

print(f"Result: {result}")
print(f"Seed: {seed}")
```

**Parameters Explained:**
- `image_path`: Absolute path to your source image
- `prompt`: Natural language instructions for image modification
- `guidance`: Controls how closely the output follows your prompt (range: 1-5, recommended: 2-3.5)
- `steps`: Number of generation steps (higher values increase quality but take longer)
- `hf_token`: Optional Hugging Face token for priority access

3. **Execute**: Run all cells in the notebook. The edited image will be displayed and saved as `flux_result_{seed}.png` in the project root.

## Example Prompts

- "Change the background to a sunset beach scene"
- "Make the person wear sunglasses"
- "Convert to black and white photography"
- "Add a red scarf around the neck"

## Output

Generated images are automatically saved with their seed value for reproducibility:
```
flux_result_123456789.png
```

## License

- **Code**: MIT License - free for commercial and personal use
- **Model**: FLUX.1 [dev] Non-Commercial License - research and non-commercial use only

⚠️ **Important**: Review the [FLUX.1 [dev] license terms](https://huggingface.co/black-forest-labs/FLUX.1-dev/blob/main/LICENSE.md) before commercial deployment.

## Resources

- [Model on Hugging Face](https://huggingface.co/spaces/black-forest-labs/FLUX.1-Kontext-dev)
- [Black Forest Labs](https://blackforestlabs.ai/)
- [FLUX.1 Documentation](https://github.com/black-forest-labs/flux)

## Troubleshooting

**Connection Issues**: If you encounter API errors, try adding a Hugging Face token for authenticated access.

**Quality Concerns**: Increase the `steps` parameter (try 40-50) or adjust `guidance` for better prompt adherence.

**Path Errors**: Ensure you're using absolute paths and proper path separators for your operating system.

---

**Questions or issues?** Open an issue on GitHub or consult the Hugging Face Space documentation.
