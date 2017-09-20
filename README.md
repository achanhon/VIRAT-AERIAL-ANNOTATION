# Annotation of a subset of VIRAT AERIAL dataset

VIRAT dataset http://www.viratdata.org/ is a DARPA dataset containing mainly ground static videos and corresponding ground truth.

VIRAT also contains an AERIAL dataset (set of video acquired by a plane).
No ground truth is provided for these data.

This is why, I have annotated a small subset of these aerial data for person detection and tracking.
This ground truth (or metadata) is released for research purpose only.
(Contact ONERA for commercial purpose)

**THE METADATA IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE METADATA OR THE USE OR OTHER DEALINGS IN THE METADATA.**

## File format
Files are organised as a set of folders each folder corresponds to a subset of one video.
Some video may lead to multiple folder (with at least 1 image space between the corresponding subsequences).
Each folder contains :
- a file nbtrack.txt containing the number of tracks in the subsequence
- a file size.txt containing the size (in frame) of the subsequence
- a set of files one for each track

Track file format is
- first line contains the number of the image in which the track start
- 2nd line contains the number of images during which the track is alive
- then the file contains 4*size lines: each 4 lines corresponds to a rectangle in x,y,w,h coordinate (so line 3 is x of the rect in the image where the track starts, line 4 is y, line 5 is w, line 6 is h, line 7 is x in the frame following the starting one and etc.)

## Synchronizing the ground truth with original data
Link between the original video and the selected subsequence has been lost.

We provide the first image of each subsequence (unfortunately with some pre processing like croping black pixel and compressing in .jpg).
This gives a theoretic way to synchronize the subsequence with the original data.

However, feel free to request the (pre processed) subsequences at "adrien.chan"+'_'+"hon"+'_'+"tong@onera.fr" (it is the 8 dash not the 6 one).
I will try to answer **all** requests.
It will only depend on my available time and the possibility to transfert the 1.5Go of the data.

## Limitation
There are 3 kinds of limitations of this ground truth (in addition of probably having a small amount of mistakes).

- There is no clear policy concerning the image borders and occultation (sometime track is still alive whereas 80% of the person are occulted - sometime track ends just before the person is beeing occulted).
- Scale of the object are considered constant during a subsequence.
- Annotations have been done manually but with the assistance of computer vision tool.



