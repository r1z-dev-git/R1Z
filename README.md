<!-- <p align="center">
  <img width="100" src="/readme-assets/logo-circle.png" alt="r1z logo">
</p> -->

![r1z SDK Preview](https://i.imgur.com/QYftu1j.png)
![r1z SDK Preview](https://i.imgur.com/QYftu1j.png)

<h4 align="center">
  <a href="https://pypi.org/project/r1z/">
    <img alt="Last 1 month downloads for the Python SDK" loading="lazy" width="200" height="20" decoding="async" data-nimg="1"
    style="color:transparent;width:auto;height:100%" src="https://img.shields.io/pypi/dm/r1z?label=PyPI%20Downloads">
  </a>
  <a href="https://www.npmjs.com/package/r1z">
    <img alt="Last 1 month downloads for the JavaScript SDK" loading="lazy" width="200" height="20" decoding="async" data-nimg="1"
    style="color:transparent;width:auto;height:100%" src="https://img.shields.io/npm/dm/r1z?label=NPM%20Downloads">
  </a>
</h4>

<!---
<img width="100%" src="/readme-assets/preview.png" alt="Cover image">
--->
## What is R1Z?
[r1z](https://www.r1z.dev/) is an open-source infrastructure that allows you to run AI-generated code in secure isolated sandboxes in the cloud. To start and control sandboxes, use our [JavaScript SDK](https://www.npmjs.com/package/@r1z/code-interpreter) or [Python SDK](https://pypi.org/project/r1z_code_interpreter).

> [!NOTE]
> This repository contains the core r1z SDK that's used in our main [r1z Code Interpreter SDK](https://github.com/r1z-dev-git/super-robot).

## Run your first Sandbox

### 1. Install SDK

JavaScript / TypeScript
```
npm i @r1z/code-interpreter
```

Python
```
pip install r1z-code-interpreter
```

### 2. Get your r1z API key
1. Sign up to r1z [here](https://dash-r1z.dev/).
2. Get your API key [here](https://dash-r1z.dev/).
3. Set environment variable with your API key
```
r1z_API_KEY=r1z_***
```     

### 3. Execute code with code interpreter inside Sandbox

JavaScript / TypeScript
```ts
import { Sandbox } from '@r1z/code-interpreter'

const sandbox = await Sandbox.create()
await sandbox.runCode('x = 1')

const execution = await sandbox.runCode('x+=1; x')
console.log(execution.text)  // outputs 2
```

Python
```py
from r1z_code_interpreter import Sandbox

with Sandbox() as sandbox:
    sandbox.run_code("x = 1")
    execution = sandbox.run_code("x+=1; x")
    print(execution.text)  # outputs 2
```


## Self-hosting

The infrastructure is deployed using Terraform. 

Supported cloud providers:
- 🟢 GCP
- 🚧 AWS
- [ ] Azure
- [ ] General linux machine
