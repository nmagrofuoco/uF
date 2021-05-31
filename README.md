# uF
An (R)ST-invariant multi-modal recognizer for fast prototyping.

## Description
uF (multi-Features) is an algorithm developed to recognize 2D and 3D gestures sampled by a touch-sensitive surface or an advanced computer vision technique, and characterized by one or several paths (i.e., uni- or multi-paths). The recognizer weights four features to determine the similarity between an (unknown) candidate gesture and a set of templates. All features are invariant to variations along Scale and Translation, whereas the second feature, similar to FTL's local shape distance, is insensitive to variations in Rotation (RST-invariant).

## Get Started
1. Initialize a `uFRecognizer(numPoints, alpha, beta, gamma, delta, articulations)` object where `numPoints` designates the number of points to which gestures are resampled (usually, numPoints=8), alpha, beta, gamma, and delta define the expected weight for each feature (usually, `3, 1.5, 1, 2` for 2D gestures, `1, 4, 0, 0` for 3D gestures, and `0 1 0 0` for rotation-invariant gestures), and `articulations` define the relevant uni-path or multi-path articulations (i.e., an array of arrays of one or three paths, respectively).
2. Add a series examples for each gesture class via the `addTemplate(paths, name)` method where `paths` is an array of arrays of Point objects for each gesture path and name designates the gesture class.
3. Classify a candidate gesture via the `recognize(paths)` method where `paths` designates an unknown array of arrays of Point objects for each gesture path.

## License
The academic publication for uF, and what should be used to cite it, is:

In press.

BSD 3-Clause License

Copyright (c) 2021, Nathan Magrofuoco, Jean Vanderdonckt, and Paolo Roselli
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this
   list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice,
   this list of conditions and the following disclaimer in the documentation
   and/or other materials provided with the distribution.

3. Neither the name of the copyright holder nor the names of its
   contributors may be used to endorse or promote products derived from
   this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
