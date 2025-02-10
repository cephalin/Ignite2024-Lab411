# CPU-optimized inference container

This inference image is a simple python API on top of the [CPU-optimized Phi-3 mini model](https://huggingface.co/microsoft/Phi-3-mini-4k-instruct-onnx) on Hugging Face.

## Get the pre-built image
You can pull the image directly from the Microsoft Container Registery at [mcr.microsoft.com/appsvc/docs/sidecars/sample-experiment:phi3-python-1.0](mcr.microsoft.com/appsvc/docs/sidecars/sample-experiment:phi3-python-1.0). It can be readily deployed to a sidecar container in App Service.

## Build it yourself

To build the image, you need the Hugging Face model before running docker build. You can download it locally by running the following commands in the *phi-3-sidecar* directory.

```
pip install -U "huggingface_hub[cli]"
huggingface-cli download microsoft/Phi-3-mini-4k-instruct-onnx --local-dir ./Phi-3-mini-4k-instruct-onnx
```

The Dockerfile copies a CPU optimized version of the model into the image.