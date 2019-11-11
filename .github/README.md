<p align="center">
  <img src="https://cdn.miki.ai/nuget/miki-logo@0.5x.png"/>
</p>
<p align="center">
    Mikibot/imghoard API implementation in C#
</p>

<p align="center">
  <!-- Nuget package -->
  <a href="https://www.nuget.org/packages/Imghoard.Net">
      <img src="https://img.shields.io/nuget/dt/Imghoard.Net.svg"/>
  </a>

  <!-- Discord dev server -->
  <a href="https://discord.gg/XpG4kwE">
    <img src="https://img.shields.io/discord/259343729586864139.svg?logo=discord"/>
  </a>
  <!-- Add additional badged here -->
</p>

<!-- Build status of MASTER only -->

# .Net Imghoard

## Build status

|Environment | Platform | PlatformN|
|---|---|---|
| env_release | <img src="https://dev.azure.com/mikibot/Miki/_apis/build/status/dotnet-imghoard?branchName=master"/> | <img src="https://dev.azure.com/mikibot/Miki/_apis/build/status/dotnet-imghoard?branchName=master"/>|

## Getting started
Here's how to get started with .Net Imghoard
```cs
//Use Default Settings
ImghoardClient client = new ImghoardClient();
//Pass in config to constructor
ImghoardClient client = new ImghoardClient(new Config() {
  Endpoint = "https://imghoard.example.com"
});

//Get All Images Without Tags
var images = await client.GetImagesAsync();
//Get All Images Of Specfic Tag
var images = await client.GetImagesAsync("animal");
//Get All Images Of Specfic Tag on a specific page (0-index based)
var images = await client.GetImagesAsync(1, "animal");
//Get All Images Of Specific Tag Excluding Tag
var images = await client.GetImagesAsync("animal", "-cat");
//Get A specific image by it's Id
var image = await client.GetImageAsync(1169529585188999168);

//Posts A new Image
var imageurl = await client.PostImage(imageByteSpan, "supercool", "image", "with", "amazing", "tags");
```
