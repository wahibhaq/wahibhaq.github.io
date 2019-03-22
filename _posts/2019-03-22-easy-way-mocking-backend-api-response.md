---
layout: post
title: An easy way to mock an API response using Retrofit, OkHttp, and Interceptor
tags: [android, kotlin, network, mocking, okhttp, interceptor, backend]  
share-img: https://images.unsplash.com/photo-1531403009284-440f080d1e12
published: true
---


Many times, Android developers need to start implementing features even when the backend is not ready yet. An easier way is to ask the backend developer to create the API service and just send fake content for the sake of it. The underlying notion is that we are not backend developers and it is not our responsibility to provide the endpoint.

They say 'fake it till you make it'. In this article, we'll explore the option which involves using Interceptors offered by OkHttp to mock an API response. It'll allow you to test your Retrofit REST service interface without changing anything on the code.

If it sounds interesting, you can read the original article on [medium](https://medium.com/ki-labs-engineering/an-easy-way-to-mock-an-api-response-using-retrofit-okhttp-and-interceptor-7968e1f0d050)!
