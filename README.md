# ainize-run-tensorflow-example

## Test __Run on Ainize__

### Resnet model on Tersorflow-serving

Try it out with a "Resnet model" TensorFlow serving application:

[![Run on Ainize](https://ainize.ai/static/images/run_on_ainize_button.png)](https://ainize.web.app/redirect?git_repo=github.com/ainize-team/ainize-run-tensorflow-example)

## How to run example project

### Deploy resnet API service using [tensorflow-serving-resnet/Dockerfile](tensorflow-serving-resnet/Dockerfile)

1.Build docker image
```
$ docker build -t ${DOCKER_HUB_ID}/tensorflow-serving-resnet .
```

2.Push docker image to your docker hub registry
```
$ docker push ${DOCKER_HUB_ID}/tensorflow-serving-resnet
```

3.Depoly on <a href="https://ainize-run-web.herokuapp.com/">Ainize</a>

* <a href="https://gist.github.com/yrevar/942d3a0ac09ec9e5eb3a">Checkout ImageNet 1000 class</a>
