Input/output audio data discussed in paper [Real time spectrogram inversion on mobile phone](https://arxiv.org/abs/2203.00756).


# [Main demo link](https://google.github.io/tacotron/publications/specinvert/index.html) with input and output audio used for experiments of this paper.


# Demo colab with TFLite model inference.

In the demo [colab](https://github.com/google-research/google-research/blob/master/specinvert/vctk/demo/demo.ipynb) we have end to end TFLite vocoder model inference, which reads input audio, converts it to magnitude spectrogram, then inverts magnitude spectrogram back to audio using three approaches (here you can test your own input audio):
* Neural vocoder based on MelGAN with 1 hop lookahead;
* Causal neural vocoder based on MelGAN with no lookahead;
* Streaming GL vocoder.

# Folders with audio used in [Main demo link](https://google.github.io/tacotron/publications/specinvert/index.html).
### Vocoder evaluation on VCTK data.
VCTK data [license](https://datashare.ed.ac.uk/bitstream/handle/10283/3443/license_text?sequence=3&isAllowed=y)
|  Audio files      | Description  |
| ---------------- | --------------------- |
|[Input](vctk/input) | Input data containing both clean and noisy audio clips from VCTK data.     |
|[Stream MelGAN causal (sMelGAN0)](vctk/causal) | Outputs generated by *causal* streaming neural vocoder.  |
|[Stream MelGAN_lookahead 1 (sMelGAN1)](vctk/lookahead_1) | Outputs generated by *lookahead_1* streaming neural vocoder with one hop lookahead.  |
|[Non stream MelGAN lookahead 12 (nMelGAN)](vctk/lookahead_12) | Outputs generated by *lookahead_12* streaming neural vocoder with 12 hops lookahead.  |
|[Non stream GL I70 (nGL)](vctk/non_stream_gl_I70) | Outputs generated by *non_stream_gl_I70* non streaming Griffin Lim with 70 iterations.  |
|[Stream GL with S4I4C2 (sGL1)](vctk/stream_gl_S4I4C2) | Outputs generated by *stream_gl_S4I4C2* streaming aware Griffin Lim with 4 iterations and sliding window size 4. |

We preserved audio clip names from VCTK dataset.

### Parrotron evaluation on atypical speech (Deaf) with different vocoders.
|  Audio files      | Description  |
| ---------------- | --------------------- |
|[Input](atypical_speech/input) | Input audio data.     |
|[Stream MelGAN lookahead 1 (sMelGAN1)](atypical_speech/lookahead_1) | Outputs generated by Parrotron + *lookahead_1* streaming neural vocoder with one hop lookahead.  |
|[Non_stream_gl_I70 (nGL)](atypical_speech/non_stream_gl_I70) | Outputs generated by Parrotron + *non_stream_gl_I70* non streaming Griffin Lim with 70 iterations.  |
|[Stream GL with S4I4C2 (sGL1)](atypical_speech/stream_gl_S4I4C2) | Outputs generated by Parrotron + *stream_gl_S4I4C2* streaming aware Griffin Lim with 4 iterations and sliding window size 4. |
