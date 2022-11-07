# CaptchaAI.IO Library for .NET Core
---

[Captchaai.io](https://dashboard.captchaai.io/passport/register?inviteCode=kXa8cbNF-b2l) Library.

Register now from [here!](https://dashboard.captchaai.io/passport/register?inviteCode=kXa8cbNF-b2l)

### Installation
via Package Manager:
```
NuGet\Install-Package CaptchaAI -Version 1.0.0-alpha
```
This command is intended to be used within the Package Manager Console in Visual Studio, as it uses the NuGet module's version of Install-Package.

via .NET CLI:
```ssh
dotnet add package CaptchaAI --version 1.0.0-alpha
```

via adding PackageReference:
```xml
<PackageReference Include="CaptchaAI" Version="1.0.0-alpha" />
```
For projects that support PackageReference, copy this XML node into the project file to reference the package.

### Supported Captcha Types
- Image to text
- ReCaptcha V2
- ReCaptcha V3
- HCaptcha
- HCaptcha Classification
- FunCaptcha
- FunCaptcha Classification
- GeeTest
- Datadome Slider
- Anti Kasada
- ANti Akamai BMP

### Usage Examples
---
### Creating a client
```csharp
var client = new CaptchaAIClient("apikey");
```
### Get balance
```csharp
var client = new CaptchaAIClient("apikey");
await client.GetBalance();
```
### Get Packages
```csharp
var client = new CaptchaAIClient("apikey");
await client.GetPackages();
```
#### ReCaptchaV2 Task
```csharp
var client = new CaptchaAIClient("apikey", false);
var task = new ReCaptchaV2Task("recaptcha-site", "recaptcha-site-key");
string id = await client.CreateTask(task);
var response = await client.JoinTaskResult<ReCaptchaV2Response>(id);
```

#### FunCaptcha Task
```csharp
var client = new CaptchaAIClien("apikey", false);
var task = new FunCaptchaTask("funcaptcha-site", "funcaptcha-key", "funcaptcha-js-source");
string id = await client.CreateTask(task);
var response = await client.JoinTaskResult<FunCaptchaTaskResponse>(id);
```

For other examples and api documentation please visit [wiki](https://captchaai.atlassian.net/wiki/spaces/CAPTCHAAI/overview)