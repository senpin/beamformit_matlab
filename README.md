# A MATLAB implementation of CHiME4 baseline Beamformit

**Please let me know if there are any bugs.**

gogyzzz@gmail.com

## References

- "Acoustic beamforming for speaker diarization of meetings", Xavier Anguera, Chuck Wooters and Javier Hernando, IEEE Transactions on Audio, Speech and Language Processing, September 2007, volume 15, number 7, pp.2011-2023.
- [official beamformit github](https://github.com/xanguera/BeamformIt)

## Requirements

| script | requirement |
|---|---|
| beamformit.m | MATLAB supporting audioread (also you can use on OCTAVE by installing signal package) |
| beamformit_step_by_step.mlx | MATLAB supporting mlx format |

## Implementation detail
See beamformit_step_by_step.html (and beamformit_step_by_step.mlx)

The viterbi decoding is different from the original.

## How to run

See beamformit.m 

## Result

|   | my_out_x - orig_out_x | error |
|---|---|---|
|   | ![](sample7_diff.png)  | ![](sample7_diff_zoomin.png)  |
|   | ![](sample8_diff.png)  | ![](sample8_diff_zoomin.png)  |

```sh
## original version

local/chime4_calc_wers.sh exp/tri3b_tr05_multi_noisy beamformit_5mics exp/tri3b_tr05_multi_noisy/graph_tgpr_5k

-------------------
best overall dt05 WER 13.66% (language model weight = 11)
-------------------
dt05_simu WER: 14.34% (Average), 12.82% (BUS), 17.09% (CAFE), 11.90% (PEDESTRIAN), 15.56% (STREET)
-------------------
dt05_real WER: 12.98% (Average), 15.96% (BUS), 12.67% (CAFE), 10.02% (PEDESTRIAN), 13.26% (STREET)
-------------------
et05_simu WER: 21.33% (Average), 15.75% (BUS), 22.97% (CAFE), 22.54% (PEDESTRIAN), 24.06% (STREET)
-------------------
et05_real WER: 21.80% (Average), 30.08% (BUS), 20.62% (CAFE), 19.90% (PEDESTRIAN), 16.62% (STREET)
-------------------

## my version
-------------------
best overall dt05 WER 14.04% (language model weight = 11)
-------------------
dt05_simu WER: 14.62% (Average), 12.95% (BUS), 17.23% (CAFE), 12.42% (PEDESTRIAN), 15.87% (STREET)
-------------------
dt05_real WER: 13.47% (Average), 16.70% (BUS), 13.17% (CAFE), 10.52% (PEDESTRIAN), 13.48% (STREET)
-------------------
et05_simu WER: 22.21% (Average), 16.55% (BUS), 23.96% (CAFE), 23.83% (PEDESTRIAN), 24.51% (STREET)
-------------------
et05_real WER: 22.97% (Average), 30.77% (BUS), 22.26% (CAFE), 21.71% (PEDESTRIAN), 17.13% (STREET)
-------------------
```
