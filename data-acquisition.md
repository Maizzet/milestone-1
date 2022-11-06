This code does a single query which downloads the first 100 jpg images from the given object category. The 10 categories I picked for the kitchen area are in the queryStrings list. This query was ran once for each item, and this was done by manually changing the q parameter in the query and the destination file path that each image type was going to be stored in. This was also done using Google Colab as the environment with all images stored on Google Drive.

```python 
from google.colab import drive
drive.mount('/content/drive')

pip install Google-Images-Search

from google_images_search import GoogleImagesSearch

api_key='AIzaSyDRKagpfediFdcXgSRGjxnDgaNM8jWsy74'
projectcx='1474b83678ac34acb'

gis = GoogleImagesSearch(api_key, projectcx)

queryStrings = ['sink','oven','refrigerator','cabinet','microwave','chair', 'dishwasher','rangehood','table','countertop']

_search_params = {
    'q': 'countertop',
    'num':100,
    'fileType': 'jpg'
}

gis.search(search_params=_search_params, path_to_dir='/content/drive/My Drive/Colab Notebooks/CS482Project/Images/Countertop')
```