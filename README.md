# nixx14
Face recognition
In Face Verification, we are given two images and we have to determine if they are of the same person. The simplest way to do this is to compare the two images pixel-by-pixel. If the distance between the raw images are less than a chosen threshold, it may be the same person!


Of course, this algorithm performs really poorly, since the pixel values change dramatically due to variations in lighting, orientation of the person's face, even minor changes in head position, and so on.
we see that rather than using the raw image, you can learn an encoding, f(img)f(img).
By using an encoding for each image, an element-wise comparison produces a more accurate judgement as to whether two pictures are of the same person.

The FaceNet model takes a lot of data and a long time to train. So following common practice in applied deep learning, let's load weights that someone else has already trained. The network architecture follows the Inception model from Szegedy et al..I have provided an inception network implementation. You can look in the file inception_blocks_v2.py

The key things you need to know are:

This network uses 96x96 dimensional RGB images as its input. Specifically, inputs a face image (or batch of mm face images) as a tensor of shape (m,nC,nH,nW)=(m,3,96,96)(m,nC,nH,nW)=(m,3,96,96)
It outputs a matrix of shape (m,128)(m,128) that encodes each input face image into a 128-dimensional vector
