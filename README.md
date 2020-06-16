# Deno Lambda Custom Runtime

This project provides an example AWS SAM template that creates a lambda layer which can be reused as a custom runtime to execute Deno lambdas. It defines a lambda function that hooks into the deno runtime and can be built and tested locally.

## Build
To prevent transpiling from TypeScript the makefile will use deno to bundle the script and it's dependencies and include them in the build directory along with the original script.

```
sam build
```

## Deploy
Run the deploy with the guided option of you're not sure of the S3 bucket or stack name.
```
sam deploy --guided --capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM
```

## Invoke
To test the lambda invoke it and look for the dinosaur in the command line.
```
sam local invoke
```

For more detailed examples please head over to the [hayd/deno-lambda](https://github.com/hayd/deno-lambda) project. This project was kind enough to compile Deno from source, to work with lambda, and provide a detailed bootstrap file.