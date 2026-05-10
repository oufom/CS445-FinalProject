# Eulerian and Phase-Based Video Motion Magnification

CS 445 Final Project -- Andrew Steppan, Ozi Ufomba, Satvik Movva

## Organization

All code is contained in a single Jupyter notebook: `Code.ipynb`

The notebook is organized sequentially as follows:

- **Cell 0**: Imports and setup
- **Cell 1**: Laplacian pyramid decomposition and reconstruction utilities (Wu et al.)
- **Cells 2-5**: Exploratory cells developed during initial implementation -- Wu et al. ideal temporal filter, Butterworth filter, and early phase amplification experiments on a test video (guitar7.gif). These are not part of the final pipeline but are retained to show development progression.
- **Cell 6**: Complex steerable pyramid decomposition and reconstruction (Wadhwa et al.)
- **Cell 7**: Exploratory cell for testing pyramid decomposition on a test video
- **Cell 8**: `get_phasesamps` -- extracts per-band phase and amplitude from a pyramid
- **Cell 9**: Exploratory phase amplification cell developed during Wadhwa pipeline testing
- **Cell 10**: Quantitative evaluation functions (PSNR, SNR, MAD)
- **Cell 11**: Wu et al. unified pipeline (`process_video_wu_et_al`)
- **Cell 12**: Wadhwa et al. unified pipeline (`process_video_wadhwa_et_al`)
- **Cell 13**: Comparison harness (`compare_methods_on_video`)
- **Cell 14**: Baby breathing amplification test
- **Cell 15**: Face color amplification test
- **Cell 16**: Crane motion amplification test
- **Cell 17**: Save results to disk (`results/all_results.json`)
- **Cell 18**: Load results and generate comparison figures


Source videos should be placed in a `source_videos/` directory. Output videos and results are written to `results/`.

## Requirements

```
python >= 3.9
numpy
scipy
opencv-python
matplotlib
```

Install with: `pip install numpy scipy opencv-python matplotlib`

## Running

1. Place source videos (`baby.wmv`, `face.wmv`, `crane.avi`) in `source_videos/`
2. Open `Code.ipynb` in Jupyter or VS Code
3. Run cells 0, 1, 6, 8, 10, 11, 12, 13 in order to initialize all functions
4. Run any of cells 14-16 individually to process a specific video
5. Run cell 17 to save results, then cell 18 to generate figures

Each test cell calls `compare_methods_on_video` with the appropriate parameters and saves outputs to `results/`. Videos can be run independently of each other once the function cells are initialized.

## Data

Source videos are available at: people.csail.mit.edu/mrub/evm and people.csail.mit.edu/nwadhwa/phase-video