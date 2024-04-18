Image captioning program with CTC + Mask-Predict.

We carried out a machine learning and inference with CTC and Mask-Predict image captioning.

## Dataset

Dataset train2017 of cocodataset was used. 90 % of train2017 was used for train dataset and 10 % was used for validation dataset.

## Improvements from usual Mask-Predict

For using CTCLoss, two improvements are carried out. One is target input of Transforemer Decoder ( captions ) is upsampled to twice the length in the sequence length direction.  One is improvment of inference function, l-th outputs of Transformer Decoder is twice length in the suqeunce length direction, therefore it is not used for input of l+1-th Transformer Decoder target input. So, outputs of l-th Transformer Decoder is decoded with CTC decode method into number sentence and softmax probabilities. With this probablities, l-th decoded output number sentence is masked, and input of l+1-th Transformer Decoder is made.

## Learning curve

loss = loss0 + loss1

Loss0 is non-masked CTCLoss of model outputs and targets. loss1 is MSELoss of predicted length of captions and target lengths.

### Loss0

![ImageCaptioning_CTCMaskPredict_Loos0](https://github.com/toshiouchi/CTCMask/assets/121741811/4cdf5409-759d-47a0-9017-eb2b11f00842)

### Loss1

![ImageCaptioning_CTCMaskPredict_Loos1](https://github.com/toshiouchi/CTCMask/assets/121741811/f937fd27-486f-452e-97e5-32bc1b262e9c)

### Loss

![ImageCaptioning_CTCMaskPredict_Loos](https://github.com/toshiouchi/CTCMask/assets/121741811/18c602ac-7ffd-4d99-bf33-aaafba0d14b9)

### WER

![ImageCaptioning_CTCMaskPredict_WER](https://github.com/toshiouchi/CTCMask/assets/121741811/f9ffde3e-8e8a-4678-8c58-01bf43cf79af)

## Inference results

![adorable-1849992_1920](https://github.com/toshiouchi/CTCMask/assets/121741811/a796a211-7fec-479c-8910-5a5d4478d39d)

&lt;start&gt; a dog holds a mouth up to catch a frisbee in mouth &lt;end&gt;

![africa-1170179_1920](https://github.com/toshiouchi/CTCMask/assets/121741811/7f60f73c-96c8-47ef-8abc-aba40aabbf16)

&lt;start&gt; a herd of giraffe standing in a field together in the background &lt;end&gt;

![airplane-3702676_1920](https://github.com/toshiouchi/CTCMask/assets/121741811/80d2443a-3379-4a3f-ad4e-fb28e4b0a6d7)

&lt;start&gt; a large jetliner flying over the side of a lush green field &lt;end&gt;

![automotive-1846910_1920](https://github.com/toshiouchi/CTCMask/assets/121741811/738d0b10-1a4c-4960-96da-14dc1a7e8ed3)

&lt;start&gt; a car driving down a street with a car on the it &lt;end&gt;

![beach-1837030_1920](https://github.com/toshiouchi/CTCMask/assets/121741811/c5e6c097-0490-46ca-9001-aa9927c013c4)

&lt;start&gt; a man riding a surfboard in the middle of a large wave &lt;end&gt;

![caravan-339564_1920](https://github.com/toshiouchi/CTCMask/assets/121741811/070be651-4a5c-46bb-9912-811dd8320042)

&lt;start&gt; a group of people riding on a horse next to a beach &lt;end&gt;

![cat-4467818_1920](https://github.com/toshiouchi/CTCMask/assets/121741811/520b1de8-117d-4e11-8a64-6f10894d4452)

&lt;start&gt; a cat sitting on the side of a street near a building &lt;end&gt;

![cherry-1468933_1920](https://github.com/toshiouchi/CTCMask/assets/121741811/e062d1bf-6271-4a09-b1fb-654134f59755)

&lt;start&gt; a bowl of fruit and a banana sitting on a table top &lt;end&gt;

![couple-955926_1280](https://github.com/toshiouchi/CTCMask/assets/121741811/8ab9c9d5-f16d-4d4f-98f0-682ec199a839)

&lt;start&gt; a woman in a bikini riding her bike on the beach shore &lt;end&gt;

![dog-7367949_1920](https://github.com/toshiouchi/CTCMask/assets/121741811/fdc7be04-eb90-423d-8bfd-6569203a272b)

&lt;start&gt; a dog in the air with a frisbee in its mouth open &lt;end&gt;

![hit-1407826_1920](https://github.com/toshiouchi/CTCMask/assets/121741811/4c49f4c0-bc84-4ef9-8d44-fd574c148c77)

&lt;start&gt; a baseball player holding a bat while standing on the baseball field &lt;end&gt;

![man-498473_1920](https://github.com/toshiouchi/CTCMask/assets/121741811/9120770e-f090-4867-9e34-dd09a638028f)

&lt;start&gt; a man in a suit on a snow board in the snow &lt;end&gt;

![musician-743973_1920](https://github.com/toshiouchi/CTCMask/assets/121741811/22a02202-05e1-4f55-b406-34d60ea172d7)

&lt;start&gt; a group of people and bathing suits standing on the beach with surfboards &lt;end&gt;

![port-5788261_1920](https://github.com/toshiouchi/CTCMask/assets/121741811/09d984b6-5b1e-4cbc-adca-cd714d22f0be)

&lt;start&gt; a large building with a clock and a clock on it tower &lt;end&gt;

![profile-7579739_1920](https://github.com/toshiouchi/CTCMask/assets/121741811/b93b5b43-37b1-4cfb-a3a0-da457a15c508)

&lt;start&gt; a man riding a skateboard on a ramp on a sunny day &lt;end&gt;

![ural-owl-4808774_1920](https://github.com/toshiouchi/CTCMask/assets/121741811/e30d040a-855b-4255-a1bf-744a8f7c3c75)

&lt;start&gt; a bird perched on a branch with a tree in the background &lt;end&gt;

![wine-bar-2139973_1920](https://github.com/toshiouchi/CTCMask/assets/121741811/c140116a-8fe1-4e25-91ec-0f9d1803a3d4)

&lt;start&gt; a man in a suit holding a doughnut in a right hand &lt;end&gt;

![woman-3432069_1920](https://github.com/toshiouchi/CTCMask/assets/121741811/4d734102-2cb8-4f97-8c9d-848b0af84f26)

&lt;start&gt; a brown horse standing in a field next to a forest &lt;end&gt;

![zebras-1883654_1920](https://github.com/toshiouchi/CTCMask/assets/121741811/45a46afd-4a21-4f04-ace9-8f0e1354616f)

&lt;start&gt; a zebra standing on top of a green field in a grass &lt;end&gt;








