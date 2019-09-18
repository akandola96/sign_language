
Project to recognise and translate sign language in real time

## Getting Started

```
$ git clone https://github.com/Anon9559/sign_language
```

Make a virtual environment

```
$ cd sign_language
$ python3 -m venv env
$ . env/bin/activate
```

Install the requirements

```
(env) $ pip install -r requirements.txt
```

Running

```
(env) $ cd src
(env) $ python app.py
```

## MNIST Data

 > The dataset format is patterned to match closely with the classic MNIST. Each training and test case represents a label (0-25) as a one-to-one map for each alphabetic letter A-Z (and no cases for 9=J or 25=Z because of gesture motions). The training data (27,455 cases) and test data (7172 cases) are approximately half the size of the standard MNIST but otherwise similar with a header row of label, pixel1,pixel2....pixel784 which represent a single 28x28 pixel image with grayscale values between 0-255. The original hand gesture image data represented multiple users repeating the gesture against different backgrounds. The Sign Language MNIST data came from greatly extending the small number (1704) of the color images included as not cropped around the hand region of interest. To create new data, an image pipeline was used based on ImageMagick and included cropping to hands-only, gray-scaling, resizing, and then creating at least 50+ variations to enlarge the quantity. The modification and expansion strategy was filters ('Mitchell', 'Robidoux', 'Catrom', 'Spline', 'Hermite'), along with 5% random pixelation, +/- 15% brightness/contrast, and finally 3 degrees rotation. Because of the tiny size of the images, these modifications effectively alter the resolution and class separation in interesting, controllable ways.

To use the data it first needs to be unzipped

```
$ cd data
$ unzip sign_mnist_test.zip
$ unzip sign_mnist_train.zip
```

## Testing

Tests are found under `src/tests` 

Running Tests:

```
 $ cd src
 $ python -m unittest
```

#### Note

Some tests produce windows in order to display images, the status of the test should be determined based on the test description.


# TODO:

 - [ ] Refactor ftps as decorator
 - [ ] Get Haar classifier working
 - [ ] Reevaluate CNN architecture
 - [ ] Arj to enable CUDA/GPU on PC and retrain model using 128x128 image size
