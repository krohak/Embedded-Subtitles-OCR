# Embedded-Subtitles-OCR

For some movies on youtube, you can see subtitles embedded at the bottom of the movies. We want to extract the subtitle from a movie with the corresponding timestamp. We can approach this problem in this way:

1. Regularly capture still image from the movie from time to time.
2. On each captured image, focus on the bottom part of the subtitle section.
3. Develop a machine learning method to learn how to recognize the text.



For the above problems:
1 & 2 - Using Python and FFMPEG, capture an image of the video repeatedly after a fixed duration. Then crop the image using FFMPEG so that only the part where the subtitle is embedded remains.
3 - Use pytesseract (https://pypi.python.org/pypi/pytesseract) / tesseract-ocr (https://github.com/tesseract-ocr/) to extract the text from the image. Example: https://github.com/prabhakar267/ocr-convert-image-to-text


The following may need some considerations:

1. The frequency of image capture is of some importance. It should be high enough such that no subtitles have been missing. But if it is too high, the processing (redundant) overhead will increase.

2. The timestamps for the beginning and ending of each line of subtitle should also be recorded. This is also related to Point 1 above.

3. Some videos can be of different quality; some are of VCD quality while some have high resolution. We may need to consider low quality videos too.

4. We aim to extract Cantonese subtitles. Start with English and see how the technique can be applied to other languages.
