# Welcome to your CDK TypeScript project!

This is a blank project for TypeScript development with CDK.

The `cdk.json` file tells the CDK Toolkit how to execute your app.

## Useful commands

 * `npm run build`   compile typescript to js
 * `npm run watch`   watch for changes and compile
 * `npm run test`    perform the jest unit tests
 * `cdk deploy`      deploy this stack to your default AWS account/region
 * `cdk diff`        compare deployed stack with current state
 * `cdk synth`       emits the synthesized CloudFormation template



This app is a web app to be deployed in AWS environment. 
It uses a sample docker image with php application for example.
You can choose to deploy any image with this approach. Also most of the configs are easy to setup configs.
You can have much more customized setup which could be more in your control.

- CDK (creates an aws infrastructure)
- WebApp ( creates the actual web app code that will run in AWS)

The CDK has to be run first which will create a CloudFormation template and run against the aws environment to create the stacks.
Then the WebApp can be deployed in the same stack.

1. Install Aws CDK

```
npm -g install typescript
npm install -g aws-cdk
```

2. Create a cdk project
```
mkdir my-app-cdk
// if cdk command has error
// Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass : powershell
// be careful which version of cdk is being used: (use 1.x)
cdk init --language typescript
```

3. Run the cdk app
```
cdk synth
```

4. Deploy the stack
```
cdk deploy
```

You can either configure your Aws environment in the cdk code, 
OR, the cdk will pick if from you aws preferences (cli configs) `aws configure`


5. Destroy the stack
```
cdk destroy
```

### How to fix the js output files being generated in same folder?

Normally when you build the project, the typescript transpiler generates the js files in the same folder as the original ts file. 
To change the location of those generated files open your `tsconfig.json` file.
```
  "compilerOptions": {
      "outDir": "dist",
      ...
  }
```


### References
- https://docs.aws.amazon.com/cdk/latest/guide/ecs_example.html

