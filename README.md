# ainize-run-tensorflow-example

[![Run on Ainize](https://ainize.ai/static/images/run_on_ainize_button.svg)](https://ainize.web.app/redirect?git_repo=https://github.com/ainize-team/ainize-run-tensorflow-example)

## Usage

RUN resnet API server using Docker

- Build docker image

```bash
$ docker build -t tensorflow-serving-resnet .
```

- Run docker container in your local environment.

```bash
$ docker run -p 8501:8501 -it tensorflow-serving-resnet
```

- Check state of local server

```bash
$ curl http://localhost:8501/v1/models/resnet
```

- Request [example image](samples/cat.jpg) to local server

```bash

$ base64_example() {
cat <<EOF
{
    "instances": [
        {
            "b64": "$(base64 samples/cat.jpg)"
        }
    ]
}
EOF
}

$ curl -X POST http://localhost:8501/v1/models/resnet:predict \
 -H 'Content-Type: application/json' -d "$(base64_example)"
```

---

## Reference

- <a href="https://gist.github.com/yrevar/942d3a0ac09ec9e5eb3a">Checkout ImageNet 1000 class</a>
