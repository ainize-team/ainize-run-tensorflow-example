# Set Arguments (ex. resnet)
ARG model=resnet

# Base Docker image
FROM tensorflow/serving:latest

# Info
LABEL maintainer "laeyoung@comcom.ai"

# Set model name (ex. resnet)
ENV MODEL_NAME=resnet \
    MODEL_URL=https://storage.googleapis.com/download.tensorflow.org/models/official/20181001_resnet/savedmodels/resnet_v2_fp32_savedmodel_NHWC_jpg.tar.gz \
    MODEL_FILE_DIR_NAME=resnet_v2_fp32_savedmodel_NHWC_jpg


# Setup model in /models directory
ADD $MODEL_URL /tmp/$MODEL_NAME
RUN tar -xvf /tmp/$MODEL_NAME -C /models \
  && mv /models/$MODEL_FILE_DIR_NAME /models/$MODEL_NAME \
  && rm /tmp/$MODEL_NAME
