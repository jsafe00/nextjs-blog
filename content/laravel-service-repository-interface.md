---
slug: laravel-service-repository-interface
title: Implement CRUD with Laravel Service-Repository Pattern with Interface
description: 
date: 12-April-2022
---

This is a continuation of my previous post: https://dev.to/jsf00/implement-crud-with-laravel-service-repository-pattern-1dkl

You might want to check my previous post about php interface before proceeding. https://josafebalili.vercel.app/php-interface/

Let's create a repository interface for the post. Let's call it PostRepositoryInterface.php. As you can see, this repository class implemented our PostRepository that we created .

https://photos.app.goo.gl/jEVhZ882N6mgSfpk7

![](https://lh3.googleusercontent.com/zkH-Nmcfi8NouM9EzywVFx4swyE-\_dqMJ9X4Ob4rzhyBHwYfjviZ7KtwHd9x5rQowjVoEwPlrLctVBUGAvxBtq2k4qO86XQCirqQrLE8ZPNp-irHgyPn1oqRZ_imWQ02j_JtEGKJVqY=w2400)

Now, we need to create RepositoryServiceProvider and bind PostRepositoryInterface.

![](https://lh3.googleusercontent.com/aav8edK3c9ON0xUmKBvly4F_kRNWEKDbP5Vj_P31oUx9-elXVAVOD6lDDqvQ8RahggnzcnNGt9nUBda8jVGGFQs_s5FslzVXDApSH_XvNO6xyQlwFy58lhgAcaaWTNSV1hZ_FFQl3Uc=w2400)﻿﻿

![](https://lh3.googleusercontent.com/ZAeaDD2pzMkgDs8F8cO0M31W_jGsF1lMMElWNbZEmGRmIIrcbUaWnU5Y1-RbVtFhIYJHueoozSkMnk5HqtPqEbGi1bWYH2mkIPeT0Dj8sxu6yDXIAHtSqMN7aXrSyScsJ8eghPW_Kno=w2400)

Then register it to the AppServiceProvider.

![](https://lh3.googleusercontent.com/KLFh3zT5BZWjgGO0-JGfSrdD8LFPmhJg3cWweGLOC7o_chAYHHpK3Q66LD9mVmPWhhQHi_rieAvs1XqB_ZA55TBHUC14wC-NqHff_yzOoOBCm3zvu33XHkuUU_qzZN68VDi_yQJeuiw=w2400)

https://github.com/jsafe00/laravel-service-repository/tree/with-interface



Check the Eloquent Interface implementation at https://josafebalili.vercel.app/laravel-service-repository-eloquent-interface
