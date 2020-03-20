Link: https://github.com/jordipons/musicnn


musicnn
Pronounced as "musician", musicnn is a set of pre-trained musically motivated convolutional neural networks for music audio tagging. This repository also includes some pre-trained vgg-like baselines.

Check the documentation and our basic / advanced examples to understand how to use musicnn.

Do you have questions? Check the FAQs.

Installation
pip install musicnn

or, to get bigger models and all the documentation (including jupyter notebooks), install from source:

git clone https://github.com/jordipons/musicnn.git

python setup.py install

Predict tags
From within python, you can estimate the topN tags:

from musicnn.tagger import top_tags
top_tags('./audio/joram-moments_of_clarity-08-solipsism-59-88.mp3', model='MTT_musicnn', topN=10)
['techno', 'electronic', 'synth', 'fast', 'beat', 'drums', 'no vocals', 'no vocal', 'dance', 'ambient']

Let's try another song!

top_tags('./audio/TRWJAZW128F42760DD_test.mp3')
['guitar', 'piano', 'fast']

From the command-line, you can also print the topN tags on the screen:

python -m musicnn.tagger file_name.ogg --print
python -m musicnn.tagger file_name.au --model 'MSD_musicnn' --topN 3 --length 3 --overlap 1.5 --print
or save to a file:

python -m musicnn.tagger file_name.wav --save out.tags
python -m musicnn.tagger file_name.mp3 --model 'MTT_musicnn' --topN 10 --length 3 --overlap 1 --print --save out.tags
