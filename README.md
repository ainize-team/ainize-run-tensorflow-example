# ainize-run-example

## Test __Run on Ainize__

### Resnet model on Tersorflow-serving

Try it out with a "Resnet model" TensorFlow serving application:

Run on [![Run on Ainize](assets/ainize-logo.png)](http://viewer.ainize.ai:8080/?url=https://github.com/laeyoung/ainize-run-example/blob/master/swagger/tf-resnet-openapi_v0.1.1.yaml)


## How to run example project

### Deploy resnet API service using [tensorflow-serving-resnet/Dockerfile](tensorflow-serving-resnet/Dockerfile)

```sh-session
# 1.Set docker hub id and ainize dev key
$ DOCKER_HUB_ID=your-docker-hub-id
$ AINIZE_DEV_KEY=your-ainize-dev_key

# 2.Build docker image
$ docker build -t tensorflow-serving-resnet tensorflow-serving-resnet/

# 3.Change image tag
$ docker tag tensorflow-serving-resnet ${DOCKER_HUB_ID}/tensorflow-serving-resnet

# 4.Push docker image to your docker hub registry
$ docker push ${DOCKER_HUB_ID}/tensorflow-serving-resnet

# 5.Depoly on Ainize
$ ainize deploy -d ${DOCKER_HUB_ID}/tensorflow-serving-resnet -k ${AINIZE_DEV_KEY} -n tensorflow-serving-resnet --port=8501
```


