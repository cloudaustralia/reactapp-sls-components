# A/NZ Solutions Architecture Candidate Test

## Overview

This test requires you to configure a very simple web app.

The web app consists of two components:

  - A static webpage, integrated with React.js
  - A callback function, which returns some simple data.

You need to upload the static webpage somewhere web accessible. There's a clearly marked value in the source of the webpage that needs to be changed to the endpoint of the callback. Once this is done, your static page will call the callback, and you'll see the output.

## Detail

The files you'll need to upload to make the static site work are:

  - `index.html`
  - `event_caller.js`

The code you'll need to host somewhere so that it can execute is:

  - `callbackcode.py`

It's up to you to figure where to run that code and how to expose it over the web.

The callback function is some Python code. It can't be executed in the browser, so need to be hosted somewhere that it can execute in response to a web request.

Everything should be uploaded to the Sydney AWS region if possible.

You should follow best practices for secure and performant web pages: use of HTTPS, a CDN, and so on.

Once you have configured everything, send back the URL of your static site, and we will check it for you.

**Example of webpage with embedded callback**

![example embedded callback](example-embedded-callback.png)


## Serverless Framework

### Requirements
- [NodeJS (6.14.4)](https://nodejs.org/en/)
- [Serverless Framework (1.65.0)](https://www.serverless.com/framework/docs/providers/aws/guide/installation/)
    ```bash
      $ npm install -g serverless
    ```
- [Anaconda](https://docs.anaconda.com/anaconda/install/)

    ```bash
      $ conda env create -f environment.yml
      $ conda activate reactapp-sls
    ```
  
### Install node dependencies
  ```bash
    $ npm install && npm run build
  ```

### Deploy Serverless App Components

Deploy Lambda and API Gateway
  ```bash
    $ sls deploy --debug --aws-s3-accelerate
  ```




  
