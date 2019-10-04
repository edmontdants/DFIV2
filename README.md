# DFIV2




Massive number of videos are available online today and their big data occupied by continuous and redundant image frames is a challenge for both the infrastructure (internet streaming bandwidth and storage) and people who watch videos. Identifying and removing continuous frames from videos would be a solution. To save bandwidth and storage, it can be used as a new video codec that compresses videos potentially better in terms of quality than the existing ones. To save time to watch videos, it can be used to cluster image frames as “scenes” retrieving information about at which frame each “scene” starts and ends. While many social medias hire content reviewers to remove offensive videos, it will be more efficient for them to pick an image frame from each “scene” for quick content review than sampling image frames at a constant interval. Video frame interpolation had been done by optical flow, but approach based on Convolutional Neural Network (CNN) is becoming popular. These days, several interpolation methodologies using convolutional neural networks have been proposed seeking for better quality of interpolation. In this project, we will explore and evaluate 3 approaches using CNN; CNN without GAN or Flow, CNN with GAN (Generative Adversarial Network), and CNN with Flow and a new loss function.

In mathematical terms interpolation means constructing new data points between the discrete set of known data points. In terms of video frame interpolation this would mean generating intermediate frames for a video sequence. This kind of video frame interpolation is useful for several application like generation of animated videos, smooth low motion video generation, video compression where this method would allow for transmission of a smaller video file and later generate original video at destination using frame interpolation. Practical applications require generation of high-quality video frames at a high rate achieving this requires high computation power. Several approaches have been tried to produce high quality interpolated frames without compromising video quality. However, the challenge is real and video frame interpolation remains one of the most challenging tasks in computer vision. Even if interpolating at the middle of 2 frames is possible, it might not be enough. In many cases, it is more convenient and intuitive to up sample by, for example, 10 times (synthesize 9 frames between 2 frames). Up sampling rate of power of 2 (2, 4, 8, 16, etc) can be possible by repeating interpolation at the middle, but it is computationally inefficient.

Approach based on GAN with CNN Frames were created from ’ApplyEyeMakeup’ videos from UCF101 dataset (v_ApplyEyeMakeup_g08_c01, 02, 03, 04, 05). Triplet Dataset is created from the frames where each sample contains I0 in left and I0.5 in out and I1 in right. Generator uses left and right frames to generate the middle frame I0.5’. Unit architecture was used for both generator and discriminator and most of the processing is done at lower image resolutions, and then the results are up sampled and combined with high resolution streams. The generated image is an intermediate plausible frame; hence we have used supervised loss, in addition to the generative adversarial network loss. The discriminator learns to classify between fake and real frames and the generator learns to fool the discriminator by generating frames.