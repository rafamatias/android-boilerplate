# ANDROID BOILERPLATE

## Proposal 

Creating an Android Boilerplate project with best configuration. This repository is building using a series of articles that I created on Medium

### Articles

- 05-2018 [Gradle: Android Build Variables Done Right](https://medium.com/@rafamatias/gradle-android-build-variables-done-right-d0c0e296ee93)

## Build Types

![Build Types](images/build-types.jpg)

## Build Variables

Define build variables just using Gradle:

[app/gradle.properties](app/gradle.properties)

```
API_URL=""
DATABASE=""
```

[app/build.gradle](app/build.gradle)

```
android{
	...
	buildTypes {
	    debug {
	        applicationIdSuffix ".debug"
	        buildConfigField "String", "API_URL", DEBUG_API_URL
	    }
	    internal {
	        applicationIdSuffix ".test"
	        buildConfigField "String", "API_URL", INTERNAL_API_URL
	    }
	    staging {
	        applicationIdSuffix ".staging"
	        buildConfigField "String", "API_URL", STAGING_API_URL
	    }
	    release {
	        buildConfigField "String", "API_URL", API_URL
	        ....
	    }
	}
}
```


# License
MIT License

Copyright (c) 2017 Rafael Matias

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.