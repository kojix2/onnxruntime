# ONNX Runtime

:fire: [ONNX Runtime](https://github.com/Microsoft/onnxruntime) - the high performance scoring engine for ML models - for Ruby

## Installation

First, [install ONNX Runtime](#onnx-runtime-installation).

Add this line to your application’s Gemfile:

```ruby
gem 'onnxruntime'
```

## Getting Started

Load a model and make predictions

```ruby
model = OnnxRuntime::Model.new("model.onnx")
model.predict(x: [1, 2, 3])
```

Get inputs

```ruby
model.inputs
```

Get outputs

```ruby
model.outputs
```

Load a model from a string

```ruby
byte_str = File.binread("model.onnx")
model = OnnxRuntime::Model.new(byte_str)
```

Get specific outputs

```ruby
model.predict({x: [1, 2, 3]}, output_names: ["label"])
```

## Inference Session API

You can also use the Inference Session API, which follows the [Python API](https://microsoft.github.io/onnxruntime/api_summary.html).

```ruby
session = OnnxRuntime::InferenceSession.new("model.onnx")
session.run(nil, {x: [1, 2, 3]})
```

## ONNX Runtime Installation

ONNX Runtime provides [prebuilt libraries](https://github.com/microsoft/onnxruntime/releases).

### Mac

```sh
wget https://github.com/microsoft/onnxruntime/releases/download/v0.5.0/onnxruntime-osx-x64-0.5.0.tgz
tar xf onnxruntime-osx-x64-0.5.0.tgz
cd onnxruntime-osx-x64-0.5.0
cp lib/libonnxruntime.0.5.0.dylib /usr/local/lib/libonnxruntime.dylib
```

### Linux

```sh
wget https://github.com/microsoft/onnxruntime/releases/download/v0.5.0/onnxruntime-linux-x64-0.5.0.tgz
tar xf onnxruntime-linux-x64-0.5.0.tgz
cd onnxruntime-linux-x64-0.5.0.tgz
cp lib/libonnxruntime.0.5.0.so /usr/local/lib/libonnxruntime.so
```

### Windows

Download [ONNX Runtime](https://github.com/microsoft/onnxruntime/releases/download/v0.5.0/onnxruntime-win-x64-0.5.0.zip). Unzip and move `lib/onnxruntime.dll` to `C:\Windows\System32\onnxruntime.dll`.

## History

View the [changelog](https://github.com/ankane/onnxruntime/blob/master/CHANGELOG.md)

## Contributing

Everyone is encouraged to help improve this project. Here are a few ways you can help:

- [Report bugs](https://github.com/ankane/onnxruntime/issues)
- Fix bugs and [submit pull requests](https://github.com/ankane/onnxruntime/pulls)
- Write, clarify, or fix documentation
- Suggest or add new features
