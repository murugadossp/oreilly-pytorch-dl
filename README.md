![oreilly-logo](images/oreilly.png)

# Introduction to Deep Learning with PyTorch


This repository contains code for the [O'Reilly Live Online Training for Introduction to Deep Learning with PyTorch
](https://www.oreilly.com/live-events/introduction-to-deep-learning-with-pytorch/0636920086096)

This training provides the theory, practical concepts, and comprehensive introduction to machine learning and deep learning with PyTorch. By making your way through several real-world case studies including object recognition and text classification, this session is an excellent crash course in deep learning with PyTorch.

We will use tools including large pre-trained models and model training dashboards to set up reproducible deep learning experiments and build machine learning models optimized for performance. There will be several code examples throughout the training to help solidify the theoretical concepts that will be introduced.

### Notebooks

[First steps with Deep Learning with MNIST](notebooks/1_mnist.ipynb)

All data can be downloaded [here](https://drive.google.com/file/d/1jofGOHQ4PwZ50kpGuDqBeVXwDNcjPE6B/view?usp=sharing). Note it is about 6GB so it may take a bit.

[RNNs and CNNs](notebooks/2_rnn_and_cnn.ipynb)

[Working with pre-trained models](notebooks/3_pretained_models.ipynb)

[Production Optimization](notebooks/4_deployment_and_optimization.ipynb)

### Flask App

`app.py` is a Flask app that uses a VGG16 model to classify the art style of an uploaded image. The app currently supports 10 different art styles:

- Abstract Expressionism
- Art Nouveau (Modern)
- Baroque
- Expressionism
- Impressionism
- Northern Renaissance
- Post-Impressionism
- Realism
- Romanticism
- Symbolism

Start the Flask app:
`python app.py`

This should start the Flask app and make it available at `http://localhost:5000`.

#### How to Use the App

To classify an image, you can use a cURL request in the following format:


```curl -X POST -F 'image=@/path/to/your/image.jpg' http://localhost:5000/predict```

Replace `/path/to/your/image.jpg` with the path to your own image. The response will be in JSON format and will contain the predicted art style and associated confidence scores, as shown below:

```
e.g.
curl -X POST -F \
  'image=@images/Venus_and_Adonis_by_Peter_Paul_Rubens.jpg' \
  http://localhost:5000/predict

[
	["Northern_Renaissance",0.13392961025238037],
	["Realism",0.12794768810272217],
	["Romanticism",0.12592236697673798],
	["Post_Impressionism",0.11863630264997482],
	["Baroque",0.11325731128454208],
	["Symbolism",0.1120268702507019],
	["Expressionism",0.08971412479877472],
	["Impressionism",0.086906298995018],
	["Art_Nouveau_Modern",0.05910796299576759],
	["Abstract_Expressionism",0.03255145251750946]]
```

If there is an error with the request, such as no image being provided, the response will contain an error message instead:

```
{
	"error": "No image provided"
}
```


## Instructor

**Sinan Ozdemir** is the Founder and CTO of LoopGenius where he uses State of the art AI to help people create and run their businesses. Sinan is a former lecturer of Data Science at Johns Hopkins University and the author of multiple textbooks on data science and machine learning. Additionally, he is the founder of the recently acquired Kylie.ai, an enterprise-grade conversational AI platform with RPA capabilities. He holds a master’s degree in Pure Mathematics from Johns Hopkins University and is based in San Francisco, CA.

