# πΌSmootify

[![youtube](https://img.shields.io/badge/Youtube-Link-red)](https://www.youtube.com/watch?v=pVSYUz6uS68)
[![googledrive](https://img.shields.io/badge/report-Link-lightgrey)](https://drive.google.com/file/d/1VbAGiYxhro913O-q9mINd-VEs23m7WFM/view?usp=sharing)
<br>

<p align="center"><img src="https://user-images.githubusercontent.com/63901494/149273959-bb879fd6-fe99-4a87-be93-6d774b27a026.png"></p>

2022.01 ToBig's Sound Conf. by TobigTonix<br>

μμμ νμΉνλ€, Infinite AI Music Streaming.

**Smootify**λ μμ μμ± κΈ°μ μ νμ©ν΄ λ μμμ μμ°μ€λ½κ² μ°κ²°νμ¬ μ§μ ν λ¬΄ν μ€νΈλ¦¬λ°μ μ΄λ£¨κ³ μ ν©λλ€. 

## Data
MIDI νμμΌλ‘ λμ΄ μλ μμ νμΌλ€μ μ¬μ©νμ¬ νλ‘μ νΈλ₯Ό μ§ννμμ΅λλ€.<br>
Pop μμλ€λ‘ μ΄λ£¨μ΄μ§ Million Song Datasetμ κΈ°λ°ν [Lakh Pianoroll Dataset](https://salu133445.github.io/lakh-pianoroll-dataset/)μ νμ©νμ¬ νμ΅νμμ΅λλ€.<br>

## Model
### Mashup
* Mashup Point νμ λ°©λ²μΌλ‘ **DTW(Dynamic Time Warping)** μ **λΆν¬μ μ μ¬λ**λ₯Ό νμ©νμμ΅λλ€.
* Mashupμ ν  λμ Mix Pointλ₯Ό κ΅¬νλ μκ³ λ¦¬μ¦μ μμ€μ½λλ [μ¬κΈ°](https://github.com/ToBigsSound-1516/MidiMashupper)μμ νμΈνμ€ μ μμ΅λλ€. 

### Music Transition
* **MuseGAN**μ convolutionκ΅¬μ‘°λ₯Ό μ°¨μ© λ° **U-Net** κ΅¬μ‘°λ₯Ό μ¬μ©νμ¬ λ μμκ°μ μ°κ²°κ³ λ¦¬λ₯Ό μμ±νμμ΅λλ€.
* κΈ°μ‘΄μ μμμμ κ°μ΄λ° λΆλΆμ λ§μ€νΉ ν μ΄λ₯Ό μμΈ‘νλ λ°©μμΌλ‘ νμ΅νμμ΅λλ€.<br>
* Smootify Music Transition λͺ¨λΈμ μμ€μ½λλ [μ¬κΈ°](https://github.com/ToBigsSound-1516/transition)μμ νμΈνμ€ μ μμ΅λλ€.

### Result
<img src="https://user-images.githubusercontent.com/63901494/149379001-f77bf906-e04c-4180-b2e8-6c43a43fa509.png" width="600"> 

## Usage
νμ΅ μλλ₯Ό μν΄ GPUμ¬μ©μ΄ κ°λ₯ν νκ²½μμ μ€ννκΈ°λ₯Ό κΆμ₯ν©λλ€.<br>

κ° νλΌλ―Έν°λ³ μ€λͺ λ° λ³΄λ€ μμΈν μ¬μ© λ°©λ²μ [Music Transition λͺ¨λΈ λ ν¬](https://github.com/ToBigsSound-1516/transition)μμ νμΈνμ€ μ μμ΅λλ€. 

### 1. Installation
```
git clone https://github.com/ToBigsSound-1516/transition.git
cd trainsition
pip install -r requirements.txt
```
### 2. Prepare Data
```
python3 prepare_data.py ./{data-path} {0/-1} 
```
`-1`: multiprocessing
### 3. Train
```
python3 main.py --train
```
### 4. Mix Music!
```
python3 main.py --midi_path1 ./{song1} --midi_path2 ./{song2} --start1 {mixing point} --start2 {mixing point}
```

## Web Demo
μ ν¬μ μΉ λ°λͺ¨λ [μ¬κΈ°](https://smootify-tobigs1516.netlify.app/)μμ νμΈνμ€ μ μμ΅λλ€. <br>

μ΄λ―Έμ§λ₯Ό ν΄λ¦­ μ μΉ νμ΄μ§μ κΉνλΈ λ ν¬λ‘ μ΄λν©λλ€. <br>
<a href="https://github.com/ToBigsSound-1516/WebDemo"><img src="https://user-images.githubusercontent.com/63901494/149433773-3e69dbc7-265a-4027-b579-43e25fdc7ed6.png" width="370"> <img src="https://user-images.githubusercontent.com/63901494/149433813-9d349dc8-1445-45f3-947c-87e59cb1bfb6.png" width="370"></a><br>

## Reference
* AutoMashUpper: Automatic Creation of Multi-Song Music Mashups, 2014 (Matthew E. P. Davies, Philippe Hamel, Kazuyoshi Yoshii, Masataka Goto)
* MuseGAN: Multi-track Sequential Generative Adversarial Networks for Symbolic Music Generation and Accompaniment, 2017 (Hao-Wen Dong, Wen-Yi Hsiao, Li-Chia Yang, Yi-Hsuan Yang) 
* U-Net: Convolutional Networks for Biomedical Image Segmentation, 2015 (Olaf Ronneberger, Philipp Fischer, Thomas Brox)
* MIDI-VAE: Modeling Dynamics and Instrumentation of Music with Applications to Style Transfer, 2018 (Gino Brunner, Andres Konrad, Yuyi Wang, Roger Wattenhofer)
* [salu133445/musegan](https://github.com/salu133445/musegan)
* [salu133445/lakh-pianoroll-dataset](https://github.com/salu133445/lakh-pianoroll-dataset)
* [brunnergino/MIDI-VAE](https://github.com/brunnergino/MIDI-VAE)

## Contributors
<table>
  <tr>
    <td align="center"><a href="https://github.com/5hyeonkwon"><img src="https://user-images.githubusercontent.com/63901494/148694025-1617015b-4058-4036-9c55-2a1767466da5.png" width="130" height="130"><br /><sub><b>Ohyeon Kwon</b></sub></t>
    <td align="center"><a href="https://github.com/Taehee-K"><img src="https://user-images.githubusercontent.com/68283760/125950085-509a9fe9-4dac-48dc-a8a2-ded2a4bd9f63.jpg" width="130" height="130"><br /><sub><b>Taehee Kim</b></sub></td>
    <td align="center"><a href="https://github.com/YMGYM"><img src="https://user-images.githubusercontent.com/67720742/125877285-c0b3eac0-27c7-405d-85fb-2c5cf80e5c12.jpg" width="130" height="130"><br /><sub><b>Minjun An</b></sub></td>
    <td align="center"><a href="https://github.com/hbjk0305"><img src="https://user-images.githubusercontent.com/68283760/125949229-81d9fad7-aba3-4754-af14-342ca9e22d7e.jpg"
 width="130" height="130"><br /><sub><b>JinKyoung Hwangbo</b></sub></td>
    <td align="center"><a href="https://github.com/yoonene"><img src="https://user-images.githubusercontent.com/63901494/149610362-5bd414ee-6614-42f1-af63-8f4ab51b0af6.png" width="130" height="130"><br /><sub><b>Yoonene Kim</b></sub></td>
  </tr>
</table>
