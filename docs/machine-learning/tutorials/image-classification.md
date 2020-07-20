---
title: '자습서: TensorFlow의 ML.NET 이미지 분류 모델'
description: 기존 TensorFlow 모델에서 새로운 ML.NET 이미지 분류 모델로 정보를 전이하는 방법을 알아봅니다. TensorFlow 모델은 이미지를 천 개 범주로 분류하도록 학습되었습니다. ML.NET 모델은 전이 학습을 사용하여 이미지를 좀 더 광범위한 범주로 분류합니다.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: a4c671816dce1fe2abdf77f81da0f27236136536
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2020
ms.locfileid: "86282114"
---
# <a name="tutorial-generate-an-mlnet-image-classification-model-from-a-pre-trained-tensorflow-model"></a><span data-ttu-id="58d29-105">자습서: 미리 학습된 TensorFlow 모델에서 ML.NET 이미지 분류 모델 생성</span><span class="sxs-lookup"><span data-stu-id="58d29-105">Tutorial: Generate an ML.NET image classification model from a pre-trained TensorFlow model</span></span>

<span data-ttu-id="58d29-106">기존 TensorFlow 모델에서 새로운 ML.NET 이미지 분류 모델로 정보를 전이하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-106">Learn how to transfer the knowledge from an existing TensorFlow model into a new ML.NET image classification model.</span></span>

<span data-ttu-id="58d29-107">TensorFlow 모델은 이미지를 천 개 범주로 분류하도록 학습되었습니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-107">The TensorFlow model was trained to classify images into a thousand categories.</span></span> <span data-ttu-id="58d29-108">ML.NET 모델은 파이프라인에서 TensorFlow 모델의 일부를 사용하여 이미지를 3개 범주로 분류하는 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-108">The ML.NET model makes use of part of the TensorFlow model in its pipeline to train a model to classify images into 3 categories.</span></span>

<span data-ttu-id="58d29-109">[이미지 분류](https://en.wikipedia.org/wiki/Outline_of_object_recognition) 모델을 처음부터 학습시키려면 수백만 개의 매개 변수, 많은 레이블 지정 학습 데이터 및 많은 양의 컴퓨팅 리소스(수백 시간의 GPU 시간)를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-109">Training an [Image Classification](https://en.wikipedia.org/wiki/Outline_of_object_recognition) model from scratch requires setting millions of parameters, a ton of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="58d29-110">사용자 지정 모델을 처음부터 학습시키는 것만큼 효과적이지는 않지만, 전이 학습을 사용하면 수천 개 이미지 및 수백만 개 레이블 지정 이미지를 사용하여 이 프로세스를 간소화하고 사용자 지정 모델을 매우 빠르게 빌드할 수 있습니다(GPU가 없는 머신에서는 1시간 안에 가능).</span><span class="sxs-lookup"><span data-stu-id="58d29-110">While not as effective as training a custom model from scratch, transfer learning allows you to shortcut this process by working with thousands of images vs. millions of labeled images and build a customized model fairly quickly (within an hour on a machine without a GPU).</span></span> <span data-ttu-id="58d29-111">이 자습서에서는 해당 프로세스를 좀 더 축소하여 12개의 학습 이미지만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-111">This tutorial scales that process down even further, using only a dozen training images.</span></span>

<span data-ttu-id="58d29-112">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-112">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="58d29-113">문제 이해</span><span class="sxs-lookup"><span data-stu-id="58d29-113">Understand the problem</span></span>
> * <span data-ttu-id="58d29-114">미리 학습된 TensorFlow 모델을 ML.NET 파이프라인에 통합</span><span class="sxs-lookup"><span data-stu-id="58d29-114">Incorporate the pre-trained TensorFlow model into the ML.NET pipeline</span></span>
> * <span data-ttu-id="58d29-115">ML.NET 모델 학습 및 평가</span><span class="sxs-lookup"><span data-stu-id="58d29-115">Train and evaluate the ML.NET model</span></span>
> * <span data-ttu-id="58d29-116">테스트 이미지 분류</span><span class="sxs-lookup"><span data-stu-id="58d29-116">Classify a test image</span></span>

<span data-ttu-id="58d29-117">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-117">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span> <span data-ttu-id="58d29-118">기본적으로 이 자습서의 .NET 프로젝트 구성은 .NET Core 2.2를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-118">Note that by default, the .NET project configuration for this tutorial targets .NET core 2.2.</span></span>

## <a name="what-is-transfer-learning"></a><span data-ttu-id="58d29-119">전이 학습이란?</span><span class="sxs-lookup"><span data-stu-id="58d29-119">What is transfer learning?</span></span>

<span data-ttu-id="58d29-120">전이 학습은 한 가지 문제를 해결한 후 관련이 있지만 다른 문제에 적용하면서 얻은 정보를 사용하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-120">Transfer learning is the process of using knowledge gained while solving one problem and applying it to a different but related problem.</span></span>

<span data-ttu-id="58d29-121">이 자습서에서는 이미지를 천 개의 범주로 분류하도록 학습된 TensorFlow 모델의 일부를 3개 범주로 이미지를 분류하는 ML.NET 모델에서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-121">For this tutorial, you use part of a TensorFlow model - trained to classify images into a thousand categories - in an ML.NET model that classifies images into 3 categories.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="58d29-122">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="58d29-122">Prerequisites</span></span>

* <span data-ttu-id="58d29-123">“.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 이상 또는 Visual Studio 2017 버전 15.6 이상.</span><span class="sxs-lookup"><span data-stu-id="58d29-123">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or later or Visual Studio 2017 version 15.6 or later with the ".NET Core cross-platform development" workload installed.</span></span>
* [<span data-ttu-id="58d29-124">자습서 자산 디렉터리 .ZIP 파일</span><span class="sxs-lookup"><span data-stu-id="58d29-124">The tutorial assets directory .ZIP file</span></span>](https://github.com/dotnet/samples/blob/master/machine-learning/tutorials/TransferLearningTF/image-classifier-assets.zip)
* [<span data-ttu-id="58d29-125">InceptionV1 기계 학습 모델</span><span class="sxs-lookup"><span data-stu-id="58d29-125">The InceptionV1 machine learning model</span></span>](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-right-machine-learning-task"></a><span data-ttu-id="58d29-126">적절한 기계 학습 작업 선택</span><span class="sxs-lookup"><span data-stu-id="58d29-126">Select the right machine learning task</span></span>

### <a name="deep-learning"></a><span data-ttu-id="58d29-127">딥러닝</span><span class="sxs-lookup"><span data-stu-id="58d29-127">Deep learning</span></span>

<span data-ttu-id="58d29-128">[딥 러닝](https://en.wikipedia.org/wiki/Deep_learning)은 Computer Vision 및 음성 인식 같은 혁신적인 영역인 기계 학습의 하위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-128">[Deep learning](https://en.wikipedia.org/wiki/Deep_learning) is a subset of Machine Learning, which is revolutionizing areas like Computer Vision and Speech Recognition.</span></span>

<span data-ttu-id="58d29-129">딥 러닝 모델은 여러 학습 계층이 포함된 대규모 [레이블 지정 데이터](https://en.wikipedia.org/wiki/Labeled_data) 및 [신경망](https://en.wikipedia.org/wiki/Artificial_neural_network) 세트를 사용하여 학습됩니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-129">Deep learning models are trained by using large sets of [labeled data](https://en.wikipedia.org/wiki/Labeled_data) and [neural networks](https://en.wikipedia.org/wiki/Artificial_neural_network) that contain multiple learning layers.</span></span> <span data-ttu-id="58d29-130">딥 러닝</span><span class="sxs-lookup"><span data-stu-id="58d29-130">Deep learning:</span></span>

* <span data-ttu-id="58d29-131">Computer Vision 같은 일부 작업에서 더 효과적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-131">Performs better on some tasks like Computer Vision.</span></span>
* <span data-ttu-id="58d29-132">상당한 양의 학습 데이터가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-132">Requires huge amounts of training data.</span></span>

<span data-ttu-id="58d29-133">이미지 분류는 다음과 같은 범주로 이미지를 자동으로 분류할 수 있는 일반적인 기계 학습 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-133">Image Classification is a common Machine Learning task that allows us to automatically classify images into categories such as:</span></span>

* <span data-ttu-id="58d29-134">이미지에서 사람 얼굴을 인식하는지 여부.</span><span class="sxs-lookup"><span data-stu-id="58d29-134">Detecting a human face in an image or not.</span></span>
* <span data-ttu-id="58d29-135">고양이 및 개 인식.</span><span class="sxs-lookup"><span data-stu-id="58d29-135">Detecting cats vs. dogs.</span></span>

 <span data-ttu-id="58d29-136">또는 다음 이미지와 같이 이미지가 음식, 장난감 또는 어플라이언스인지 확인:</span><span class="sxs-lookup"><span data-stu-id="58d29-136">Or as in the following images, determining if an image is a(n)  food, toy, or appliance:</span></span>

<span data-ttu-id="58d29-137">![피자 이미지](./media/image-classification/220px-Pepperoni_pizza.jpg)
![테디 베어 이미지](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![토스터 이미지](./media/image-classification/193px-Broodrooster.jpg)</span><span class="sxs-lookup"><span data-stu-id="58d29-137">![pizza image](./media/image-classification/220px-Pepperoni_pizza.jpg)
![teddy bear image](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![toaster image](./media/image-classification/193px-Broodrooster.jpg)</span></span>

>[!Note]
> <span data-ttu-id="58d29-138">앞의 이미지는 Wikimedia Commons에 속하고 다음 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-138">The preceding images belong to Wikimedia Commons and are attributed as follows:</span></span>
>
> * <span data-ttu-id="58d29-139">“220px-Pepperoni_pizza.jpg” 공용 도메인, <https://commons.wikimedia.org/w/index.php?curid=79505>,</span><span class="sxs-lookup"><span data-stu-id="58d29-139">"220px-Pepperoni_pizza.jpg" Public Domain, <https://commons.wikimedia.org/w/index.php?curid=79505>,</span></span>
> * <span data-ttu-id="58d29-140">“119px-Nalle_-_a_small_brown_teddy_bear.jpg” 작성자: [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - 직접 사진 촬영, CC BY-SA 2.0, <https://commons.wikimedia.org/w/index.php?curid=48166>.</span><span class="sxs-lookup"><span data-stu-id="58d29-140">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" By [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Self-photographed, CC BY-SA 2.0, <https://commons.wikimedia.org/w/index.php?curid=48166>.</span></span>
> * <span data-ttu-id="58d29-141">“193px-Broodrooster.jpg” 작성자: [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - 직접 작업, CC BY-SA 3.0, <https://commons.wikimedia.org/w/index.php?curid=27403></span><span class="sxs-lookup"><span data-stu-id="58d29-141">"193px-Broodrooster.jpg" By [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Own work, CC BY-SA 3.0, <https://commons.wikimedia.org/w/index.php?curid=27403></span></span>

<span data-ttu-id="58d29-142">`Inception model`은 이미지를 천 개의 범주로 분류하도록 학습되지만, 이 자습서에서는 더 작은 범주 세트 및 해당 범주로만 이미지를 분류해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-142">The `Inception model` is trained to classify images into a thousand categories, but for this tutorial, you need to classify images in a smaller category set, and only those categories.</span></span> <span data-ttu-id="58d29-143">`transfer learning`의 `transfer` 부분을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-143">Enter the `transfer` part of `transfer learning`.</span></span> <span data-ttu-id="58d29-144">이미지를 인식하고 사용자 지정 이미지 분류자의 제한된 새 범주로 분류하는 `Inception model`의 기능을 전이할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-144">You can transfer the `Inception model`'s ability to recognize and classify images to the new limited categories of your custom image classifier.</span></span>

* <span data-ttu-id="58d29-145">음식</span><span class="sxs-lookup"><span data-stu-id="58d29-145">Food</span></span>
* <span data-ttu-id="58d29-146">장난감</span><span class="sxs-lookup"><span data-stu-id="58d29-146">Toy</span></span>
* <span data-ttu-id="58d29-147">어플라이언스</span><span class="sxs-lookup"><span data-stu-id="58d29-147">Appliance</span></span>

<span data-ttu-id="58d29-148">이 자습서에서는 `ImageNet` 데이터 세트에 대해 학습된 인기 있는 이미지 인식 모델인 TensorFlow [개시 모델](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) 심층 학습 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-148">This tutorial uses the TensorFlow [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) deep learning model, a popular image recognition model trained on the `ImageNet` dataset.</span></span> <span data-ttu-id="58d29-149">TensorFlow 모델은 전체 이미지를 “Umbrella”, “Jersey” 및 “Dishwasher” 등의 천 개 클래스로 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-149">The TensorFlow model classifies entire images into a thousand classes, such as “Umbrella”, “Jersey”, and “Dishwasher”.</span></span>

<span data-ttu-id="58d29-150">`Inception model`은 수천 개의 이미지를 기반으로 미리 학습되었으므로 이미지 식별에 필요한 [이미지 기능](https://en.wikipedia.org/wiki/Feature_(computer_vision))을 내부적으로 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-150">Because the `Inception model` has already been pre trained on thousands of different images, internally it contains the [image features](https://en.wikipedia.org/wiki/Feature_(computer_vision)) needed for image identification.</span></span> <span data-ttu-id="58d29-151">모델에서 이러한 내부 이미지 기능을 활용하여 훨씬 더 적은 수의 클래스를 새 모델에 학습시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-151">We can make use of these internal image features in the model to train a new model with far fewer classes.</span></span>

<span data-ttu-id="58d29-152">다음 다이어그램과 같이 .NET Core 또는 .NET Framework 애플리케이션에서 ML.NET NuGet 패키지에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-152">As shown in the following diagram, you add a reference to the ML.NET NuGet packages in your .NET Core or .NET Framework applications.</span></span> <span data-ttu-id="58d29-153">기본적으로 ML.NET은 기존 학습된 `TensorFlow` 모델 파일을 로드하는 코드를 작성하는 데 사용할 수 있는 네이티브 `TensorFlow` 라이브러리를 포함하고 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-153">Under the covers, ML.NET includes and references the native `TensorFlow` library that allows you to write code that loads an existing trained `TensorFlow` model file.</span></span>

![TensorFlow 변환 ML.NET 아키텍처 다이어그램](./media/image-classification/tensorflow-mlnet.png)

### <a name="multiclass-classification"></a><span data-ttu-id="58d29-155">다중 클래스 분류</span><span class="sxs-lookup"><span data-stu-id="58d29-155">Multiclass classification</span></span>

<span data-ttu-id="58d29-156">TensorFlow 개시 모델을 사용하여 기존 기계 학습 알고리즘에 대한 입력으로 적합한 기능을 추출한 후에 ML.NET [다중 클래스 분류자](../resources/tasks.md#multiclass-classification)를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-156">After using the TensorFlow inception model to extract features suitable as input for a classical machine learning algorithm, we add an ML.NET [multi-class classifier](../resources/tasks.md#multiclass-classification).</span></span>

<span data-ttu-id="58d29-157">이 경우에 사용되는 특정 트레이너는 [다항 로지스틱 회귀 알고리즘](https://en.wikipedia.org/wiki/Multinomial_logistic_regression)입니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-157">The specific trainer used in this case is the [multinomial logistic regression algorithm](https://en.wikipedia.org/wiki/Multinomial_logistic_regression).</span></span>

<span data-ttu-id="58d29-158">이 트레이너가 구현하는 알고리즘은 이미지 데이터에 심층 학습 모델이 작동하는 경우에 해당하는 많은 기능을 사용할 때 발생하는 문제에 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-158">The algorithm implemented by this trainer performs well on problems with a large number of features, which is the case for a deep learning model operating on image data.</span></span>

### <a name="data"></a><span data-ttu-id="58d29-159">데이터</span><span class="sxs-lookup"><span data-stu-id="58d29-159">Data</span></span>

<span data-ttu-id="58d29-160">두 개의 데이터 소스인 `.tsv` 파일 및 이미지 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-160">There are two data sources: the `.tsv` file, and the image files.</span></span>  <span data-ttu-id="58d29-161">`tags.tsv` 파일에는 두 개의 열이 있습니다. 첫 번째 열은 `ImagePath`로 정의되고 두 번째 열은 이미지에 해당하는 `Label`입니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-161">The `tags.tsv` file contains two columns: the first one is defined as `ImagePath` and the second one is the `Label` corresponding to the image.</span></span> <span data-ttu-id="58d29-162">다음 예제 파일에는 머리글 행이 없고 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-162">The following example file doesn't have a header row, and looks like this:</span></span>

<!-- markdownlint-disable MD010 -->
```tsv
broccoli.jpg    food
pizza.jpg   food
pizza2.jpg  food
teddy2.jpg  toy
teddy3.jpg  toy
teddy4.jpg  toy
toaster.jpg appliance
toaster2.png    appliance
```
<!-- markdownlint-enable MD010 -->

<span data-ttu-id="58d29-163">학습 및 테스트 이미지는 zip 파일로 다운로드할 수 있는 자산 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-163">The training and testing images are located in the assets folders that you'll download in a zip file.</span></span> <span data-ttu-id="58d29-164">이 이미지는 Wikimedia Commons에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-164">These images belong to Wikimedia Commons.</span></span>
> <span data-ttu-id="58d29-165">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), 무료 미디어 리포지토리.*</span><span class="sxs-lookup"><span data-stu-id="58d29-165">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), the free media repository.*</span></span> <span data-ttu-id="58d29-166">2018년 10월 17일 10시 48분 검색된 위치: <https://commons.wikimedia.org/wiki/Pizza>
> <https://commons.wikimedia.org/wiki/Toaster>
> <https://commons.wikimedia.org/wiki/Teddy_bear></span><span class="sxs-lookup"><span data-stu-id="58d29-166">Retrieved 10:48, October 17, 2018 from: <https://commons.wikimedia.org/wiki/Pizza>
> <https://commons.wikimedia.org/wiki/Toaster>
<https://commons.wikimedia.org/wiki/Teddy_bear></span></span>

## <a name="setup"></a><span data-ttu-id="58d29-167">설정</span><span class="sxs-lookup"><span data-stu-id="58d29-167">Setup</span></span>

### <a name="create-a-project"></a><span data-ttu-id="58d29-168">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="58d29-168">Create a project</span></span>

1. <span data-ttu-id="58d29-169">"TransferLearningTF"라는 **.NET Core 콘솔 애플리케이션**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-169">Create a **.NET Core Console Application** called "TransferLearningTF".</span></span>

1. <span data-ttu-id="58d29-170">**Microsoft.ML NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-170">Install the **Microsoft.ML NuGet Package**:</span></span>

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    * <span data-ttu-id="58d29-171">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-171">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    * <span data-ttu-id="58d29-172">패키지 소스로 “nuget.org”를 선택하고, [찾아보기] 탭을 선택하고, **Microsoft.ML**을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-172">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span>
    * <span data-ttu-id="58d29-173">**설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-173">Select the **Install** button.</span></span>
    * <span data-ttu-id="58d29-174">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-174">Select the **OK** button on the **Preview Changes** dialog.</span></span>
    * <span data-ttu-id="58d29-175">나열된 패키지 라이선스 조건에 동의하면 **라이선스 수락** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-175">Select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>
    * <span data-ttu-id="58d29-176">**Microsoft.ML.ImageAnalytics**, **SciSharp.TensorFlow.Redist** 및 **Microsoft.ML.TensorFlow**에 이러한 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-176">Repeat these steps for **Microsoft.ML.ImageAnalytics**, **SciSharp.TensorFlow.Redist** and **Microsoft.ML.TensorFlow**.</span></span>

### <a name="download-assets"></a><span data-ttu-id="58d29-177">자산 다운로드</span><span class="sxs-lookup"><span data-stu-id="58d29-177">Download assets</span></span>

1. <span data-ttu-id="58d29-178">[프로젝트 자산 디렉터리 zip 파일](https://github.com/dotnet/samples/blob/master/machine-learning/tutorials/TransferLearningTF/image-classifier-assets.zip)을 다운로드하고 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-178">Download [The project assets directory zip file](https://github.com/dotnet/samples/blob/master/machine-learning/tutorials/TransferLearningTF/image-classifier-assets.zip), and unzip.</span></span>

1. <span data-ttu-id="58d29-179">`assets` 디렉터리를 *TransferLearningTF* 프로젝트 디렉터리에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-179">Copy the `assets` directory into your *TransferLearningTF* project directory.</span></span> <span data-ttu-id="58d29-180">이 디렉터리 및 해당 하위 디렉터리에는 이 자습서에 필요한 데이터 및 지원 파일이 포함되어 있습니다(다음 단계에서 다운로드 및 추가하는 Inception 모델 제외).</span><span class="sxs-lookup"><span data-stu-id="58d29-180">This directory and its subdirectories contain the data and support files (except for the Inception model, which you'll download and add in the next step) needed for this tutorial.</span></span>

1. <span data-ttu-id="58d29-181">[Inception 모델](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)을 다운로드하고 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-181">Download the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), and unzip.</span></span>

1. <span data-ttu-id="58d29-182">방금 *TransferLearningTF* 프로젝트 `assets/inception` 디렉터리에 압축을 푼 `inception5h` 디렉터리의 콘텐츠를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-182">Copy the contents of the `inception5h` directory just unzipped into your *TransferLearningTF* project `assets/inception` directory.</span></span> <span data-ttu-id="58d29-183">이 디렉터리에는 다음 이미지와 같이 이 자습서에 필요한 모델 및 추가 지원 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-183">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![Inception 디렉터리 콘텐츠](./media/image-classification/inception-files.png)

1. <span data-ttu-id="58d29-185">솔루션 탐색기에서 자산 디렉터리 및 하위 디렉터리의 각 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-185">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="58d29-186">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-186">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="58d29-187">클래스 만들기 및 경로 정의</span><span class="sxs-lookup"><span data-stu-id="58d29-187">Create classes and define paths</span></span>

1. <span data-ttu-id="58d29-188">*Program.cs* 파일 맨 위에 다음 추가 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-188">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](./snippets/image-classification/csharp/Program.cs#AddUsings)]

1. <span data-ttu-id="58d29-189">`Main` 메서드 바로 위의 줄에 다음 코드를 추가하여 해당 자산 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-189">Add the following code to the line right above the `Main` method to specify the asset paths:</span></span>

    [!code-csharp[DeclareGlobalVariables](./snippets/image-classification/csharp/Program.cs#DeclareGlobalVariables)]

1. <span data-ttu-id="58d29-190">입력 데이터 및 예측에 대한 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-190">Create classes for your input data, and predictions.</span></span>

    [!code-csharp[DeclareImageData](./snippets/image-classification/csharp/Program.cs#DeclareImageData)]

    <span data-ttu-id="58d29-191">`ImageData`는 입력 이미지 데이터 클래스이며 다음 <xref:System.String> 필드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-191">`ImageData` is the input image data class and has the following <xref:System.String> fields:</span></span>

    * <span data-ttu-id="58d29-192">`ImagePath`에는 이미지 파일 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-192">`ImagePath` contains the image file name.</span></span>
    * <span data-ttu-id="58d29-193">`Label`에는 이미지 레이블의 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-193">`Label` contains a value for the image label.</span></span>

1. <span data-ttu-id="58d29-194">`ImagePrediction`의 새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-194">Add a new class to your project for `ImagePrediction`:</span></span>

    [!code-csharp[DeclareImagePrediction](./snippets/image-classification/csharp/Program.cs#DeclareImagePrediction)]

    <span data-ttu-id="58d29-195">`ImagePrediction`은 이미지 예측 클래스이며 다음 필드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-195">`ImagePrediction` is the image prediction class and has the following fields:</span></span>

    * <span data-ttu-id="58d29-196">`Score`에는 지정된 이미지 분류를 위한 신뢰율이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-196">`Score` contains the confidence percentage for a given image classification.</span></span>
    * <span data-ttu-id="58d29-197">`PredictedLabelValue`에는 예측된 이미지 분류 레이블의 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-197">`PredictedLabelValue` contains a value for the predicted image classification label.</span></span>

    <span data-ttu-id="58d29-198">`ImagePrediction`은 모델이 학습된 후 예측에 사용되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-198">`ImagePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="58d29-199">이 클래스에는 이미지 경로의 `string`(`ImagePath`)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-199">It has a `string` (`ImagePath`) for the image path.</span></span> <span data-ttu-id="58d29-200">`Label`은 모델을 다시 사용하고 학습시키는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-200">The `Label` is used to reuse and train the model.</span></span> <span data-ttu-id="58d29-201">`PredictedLabelValue`은 예측 및 평가 중에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-201">The `PredictedLabelValue` is used during prediction and evaluation.</span></span> <span data-ttu-id="58d29-202">평가를 위해 학습 데이터가 있는 입력, 예측 값 및 모델이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-202">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="58d29-203">Main에서 변수 초기화</span><span class="sxs-lookup"><span data-stu-id="58d29-203">Initialize variables in Main</span></span>

1. <span data-ttu-id="58d29-204">`MLContext`의 새 인스턴스를 사용하여 `mlContext` 변수를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-204">Initialize the `mlContext` variable with a new instance of `MLContext`.</span></span>  <span data-ttu-id="58d29-205">`Main` 메서드에서 `Console.WriteLine("Hello World!")` 줄을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-205">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

    [!code-csharp[CreateMLContext](./snippets/image-classification/csharp/Program.cs#CreateMLContext)]

    <span data-ttu-id="58d29-206">[MLContext 클래스](xref:Microsoft.ML.MLContext)는 모든 ML.NET 작업의 시작점이며, `mlContext`를 초기화하면 모델 생성 워크플로 개체 간에 공유할 수 있는 새 ML.NET 환경이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-206">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="58d29-207">개념적으로 Entity Framework의 `DBContext`와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-207">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="create-a-struct-for-inception-model-parameters"></a><span data-ttu-id="58d29-208">개시 모델 매개 변수에 대한 구조체 만들기</span><span class="sxs-lookup"><span data-stu-id="58d29-208">Create a struct for Inception model parameters</span></span>

1. <span data-ttu-id="58d29-209">개시 모델에는 전달해야 하는 여러 가지 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-209">The Inception model has several parameters you need to pass in.</span></span> <span data-ttu-id="58d29-210">`Main()` 메서드 바로 뒤에서 다음 코드를 사용하여 매개 변수 값을 친숙한 이름에 매핑하는 구조체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-210">Create a struct to map the parameter values to friendly names with the following code, just after the `Main()` method:</span></span>

    [!code-csharp[InceptionSettings](./snippets/image-classification/csharp/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a><span data-ttu-id="58d29-211">표시 유틸리티 메서드 만들기</span><span class="sxs-lookup"><span data-stu-id="58d29-211">Create a display utility method</span></span>

<span data-ttu-id="58d29-212">이미지 데이터와 관련 예측을 여러 번 표시하므로 표시 유틸리티 메서드를 만들어 이미지 및 예측 결과 표시를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-212">Since you'll display the image data and the related predictions more than once, create a display utility method to handle displaying the image and prediction results.</span></span>

1. <span data-ttu-id="58d29-213">다음 코드를 사용하여 `InceptionSettings` 구조체 바로 뒤에 `DisplayResults()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-213">Create the `DisplayResults()` method, just after the `InceptionSettings` struct, using the following code:</span></span>

    ```csharp
    private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
    {

    }
    ```

1. <span data-ttu-id="58d29-214">다음과 같이 `DisplayResults` 메서드의 본문을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-214">Fill in the body of the `DisplayResults` method:</span></span>

    [!code-csharp[DisplayPredictions](./snippets/image-classification/csharp/Program.cs#DisplayPredictions)]

### <a name="create-a-tsv-file-utility-method"></a><span data-ttu-id="58d29-215">.tsv 파일 유틸리티 메서드 만들기</span><span class="sxs-lookup"><span data-stu-id="58d29-215">Create a .tsv file utility method</span></span>

1. <span data-ttu-id="58d29-216">다음 코드를 사용하여 `DisplayResults()` 메서드 바로 뒤에 `ReadFromTsv()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-216">Create the `ReadFromTsv()` method, just after the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
    {

    }
    ```

1. <span data-ttu-id="58d29-217">다음과 같이 `ReadFromTsv` 메서드의 본문을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-217">Fill in the body of the `ReadFromTsv` method:</span></span>

    [!code-csharp[ReadFromTsv](./snippets/image-classification/csharp/Program.cs#ReadFromTsv)]

    <span data-ttu-id="58d29-218">이 코드는 `tags.tsv` 파일을 구문 분석하여 `ImagePath` 속성의 이미지 파일 이름에 파일 경로를 추가하고 로드한 다음, `Label`을 `ImageData` 개체로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-218">The code parses through the `tags.tsv` file to add the file path to the image file name for the `ImagePath` property and load it and the `Label` into an `ImageData` object.</span></span>

### <a name="create-a-method-to-make-a-prediction"></a><span data-ttu-id="58d29-219">예측을 수행하는 메서드 만들기</span><span class="sxs-lookup"><span data-stu-id="58d29-219">Create a method to make a prediction</span></span>

1. <span data-ttu-id="58d29-220">다음 코드를 사용하여 `DisplayResults()` 메서드 바로 앞에 `ClassifySingleImage()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-220">Create the `ClassifySingleImage()` method, just before the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. <span data-ttu-id="58d29-221">단일 `ImagePath`의 정규화된 경로 및 이미지 파일 이름을 포함하는 `ImageData` 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-221">Create an `ImageData` object that contains the fully qualified path and image file name for the single `ImagePath`.</span></span> <span data-ttu-id="58d29-222">`ClassifySingleImage()` 메서드의 다음 줄로 아래 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-222">Add the following code as the next  lines in the `ClassifySingleImage()` method:</span></span>

    [!code-csharp[LoadImageData](./snippets/image-classification/csharp/Program.cs#LoadImageData)]

1. <span data-ttu-id="58d29-223">`ClassifySingleImage` 메서드에서 다음 코드를 그 다음 줄로 추가하여 단일 예측을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-223">Make a single prediction, by adding the following code as the next line in the `ClassifySingleImage` method:</span></span>

    [!code-csharp[PredictSingle](./snippets/image-classification/csharp/Program.cs#PredictSingle)]

    <span data-ttu-id="58d29-224">예측을 가져오려면 [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-224">To get the prediction, use the [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) method.</span></span> <span data-ttu-id="58d29-225">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602)은 데이터의 단일 인스턴스에 대한 예측을 수행할 수 있는 편리한 API입니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-225">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="58d29-226">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)은 스레드로부터 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-226">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="58d29-227">단일 스레드 또는 프로토타입 환경에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-227">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="58d29-228">프로덕션 환경에서 성능 및 스레드 보안을 개선하려면 `PredictionEnginePool` 서비스를 사용합니다. 이 서비스는 애플리케이션 전체에서 사용할 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) 개체의 [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-228">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="58d29-229">[ASP.NET Core Web API에서 `PredictionEnginePool`을 사용하는 방법](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application)에 대한 이 가이드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58d29-229">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

    > [!NOTE]
    > <span data-ttu-id="58d29-230">`PredictionEnginePool` 서비스 확장은 현재 미리 보기 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-230">`PredictionEnginePool` service extension is currently in preview.</span></span>

1. <span data-ttu-id="58d29-231">예측 결과를 `ClassifySingleImage()` 메서드의 다음 코드 줄로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-231">Display the prediction result as the next line of code in the `ClassifySingleImage()` method:</span></span>

   [!code-csharp[DisplayPrediction](./snippets/image-classification/csharp/Program.cs#DisplayPrediction)]

## <a name="construct-the-mlnet-model-pipeline"></a><span data-ttu-id="58d29-232">ML.NET 모델 파이프라인 생성</span><span class="sxs-lookup"><span data-stu-id="58d29-232">Construct the ML.NET model pipeline</span></span>

<span data-ttu-id="58d29-233">ML.NET 모델 파이프라인은 추정기의 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-233">An ML.NET model pipeline is a chain of estimators.</span></span> <span data-ttu-id="58d29-234">파이프라인 생성 중에는 실행이 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-234">Note that no execution happens during pipeline construction.</span></span> <span data-ttu-id="58d29-235">추정기 개체가 만들어졌지만 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-235">The estimator objects are created but not executed.</span></span>

1. <span data-ttu-id="58d29-236">모델을 생성하는 메서드 추가</span><span class="sxs-lookup"><span data-stu-id="58d29-236">Add a method to generate the model</span></span>

    <span data-ttu-id="58d29-237">이 메서드는 자습서의 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-237">This method is the heart of the tutorial.</span></span> <span data-ttu-id="58d29-238">모델에 대한 파이프라인을 만들고 파이프라인을 학습하여 ML.NET 모델을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-238">It creates a pipeline for the model, and trains the pipeline to produce the ML.NET model.</span></span> <span data-ttu-id="58d29-239">또한 확인되지 않은 이전 테스트 데이터를 기준으로 모델을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-239">It also evaluates the model against some previously unseen test data.</span></span>

    <span data-ttu-id="58d29-240">다음 코드를 사용하여 `InceptionSettings` 구조체 바로 뒤 및 `DisplayResults()` 메서드 바로 앞에 `GenerateModel()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-240">Create the `GenerateModel()` method, just after the `InceptionSettings` struct and just before the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static ITransformer GenerateModel(MLContext mlContext)
    {

    }
    ```

1. <span data-ttu-id="58d29-241">추정기를 추가하여 이미지 데이터에서 픽셀을 로드하고, 크기를 조정하고, 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-241">Add the estimators to load, resize and extract the pixels from the image data:</span></span>

    [!code-csharp[ImageTransforms](./snippets/image-classification/csharp/Program.cs#ImageTransforms)]

    <span data-ttu-id="58d29-242">이미지 데이터를 TensorFlow 모델에 필요한 형식으로 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-242">The image data needs to be processed into the format that the TensorFlow model expects.</span></span> <span data-ttu-id="58d29-243">이 경우, 이미지는 메모리에 로드되고 일관된 크기로 조정되며 픽셀이 숫자 벡터로 추출됩니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-243">In this case, the images are loaded into memory, resized to a consistent size, and the pixels are extracted into a numeric vector.</span></span>

1. <span data-ttu-id="58d29-244">추정기를 추가하여 TensorFlow 모델을 로드하고 점수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-244">Add the estimator to load the TensorFlow model, and score it:</span></span>

    [!code-csharp[ScoreTensorFlowModel](./snippets/image-classification/csharp/Program.cs#ScoreTensorFlowModel)]

    <span data-ttu-id="58d29-245">파이프라인의 이 단계는 TensorFlow 모델을 메모리로 로드한 다음, TensorFlow 모델 네트워크를 통해 픽셀 값의 벡터를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-245">This stage in the pipeline loads the TensorFlow model into memory, then processes the vector of pixel values through the TensorFlow model network.</span></span> <span data-ttu-id="58d29-246">심층 학습 모델에 입력을 적용하고 모델을 사용하여 출력을 생성하는 것을 **점수 매기기**라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-246">Applying inputs to a deep learning model, and generating an output using the model, is referred to as **Scoring**.</span></span> <span data-ttu-id="58d29-247">모델을 전체적으로 사용하는 경우 점수를 매기기 위해 유추 또는 예측을 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-247">When using the model in its entirety, scoring makes an inference, or prediction.</span></span>

    <span data-ttu-id="58d29-248">이 경우에는 유추를 수행하는 계층인 마지막 계층을 제외한 모든 TensorFlow 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-248">In this case, you use all of the TensorFlow model except the last layer, which is the layer that makes the inference.</span></span> <span data-ttu-id="58d29-249">마지막에서 두 번째 계층의 출력은 `softmax_2_preactivation`이 레이블로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-249">The output of the penultimate layer is labeled `softmax_2_preactivation`.</span></span> <span data-ttu-id="58d29-250">이 계층의 출력은 사실상 원래 입력 이미지의 특징을 나타내는 기능 벡터입니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-250">The output of this layer is effectively a vector of features that characterize the original input images.</span></span>

    <span data-ttu-id="58d29-251">TensorFlow 모델에서 생성된 이 기능 벡터는 ML.NET 학습 알고리즘에 대한 입력으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-251">This feature vector generated by the TensorFlow model will be used as input to an ML.NET training algorithm.</span></span>

1. <span data-ttu-id="58d29-252">학습 데이터의 문자열 레이블을 정수 키 값에 매핑하는 추정기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-252">Add the estimator to map the string labels in the training data to integer key values:</span></span>

    [!code-csharp[MapValueToKey](./snippets/image-classification/csharp/Program.cs#MapValueToKey)]

    <span data-ttu-id="58d29-253">다음에 추가된 ML.NET 트레이너에서는 해당 레이블이 임의 문자열이 아닌 `key` 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-253">The ML.NET trainer that is appended next requires its labels to be in `key` format rather than arbitrary strings.</span></span> <span data-ttu-id="58d29-254">키는 문자열 값에 일대일로 매핑되는 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-254">A key is a number that has a one to one mapping to a string value.</span></span>

1. <span data-ttu-id="58d29-255">다음과 같이 ML.NET 학습 알고리즘을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-255">Add the ML.NET training algorithm:</span></span>

    [!code-csharp[AddTrainer](./snippets/image-classification/csharp/Program.cs#AddTrainer)]

1. <span data-ttu-id="58d29-256">예측 키 값을 문자열에 다시 매핑하는 추정기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-256">Add the estimator to map the predicted key value back into a string:</span></span>

    [!code-csharp[MapKeyToValue](./snippets/image-classification/csharp/Program.cs#MapKeyToValue)]

## <a name="train-the-model"></a><span data-ttu-id="58d29-257">모델 학습</span><span class="sxs-lookup"><span data-stu-id="58d29-257">Train the model</span></span>

1. <span data-ttu-id="58d29-258">[LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile(Microsoft.ML.DataOperationsCatalog,System.String,Microsoft.ML.Data.TextLoader.Options)) 래퍼를 사용하여 학습 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-258">Load the training data using the [LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile(Microsoft.ML.DataOperationsCatalog,System.String,Microsoft.ML.Data.TextLoader.Options)) wrapper.</span></span> <span data-ttu-id="58d29-259">`GenerateModel()` 메서드에 아래 코드를 다음 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-259">Add the following code as the next line in the `GenerateModel()` method:</span></span>

    [!code-csharp[LoadData](./snippets/image-classification/csharp/Program.cs#LoadData "Load the data")]

    <span data-ttu-id="58d29-260">ML.NET의 데이터는 [IDataView 클래스](xref:Microsoft.ML.IDataView)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-260">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="58d29-261">`IDataView`는 표 형식 데이터(숫자 및 텍스트)를 유연하고 효율적으로 설명하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-261">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="58d29-262">데이터를 텍스트 파일 또는 실시간(예: SQL 데이터베이스 또는 로그 파일)에서 `IDataView` 개체로 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-262">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

1. <span data-ttu-id="58d29-263">위에 로드된 데이터로 모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-263">Train the model with the data loaded above:</span></span>

    [!code-csharp[TrainModel](./snippets/image-classification/csharp/Program.cs#TrainModel)]

    <span data-ttu-id="58d29-264">`Fit()` 메서드는 학습 데이터 세트를 파이프라인에 적용하여 모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-264">The `Fit()` method trains your model by applying the training dataset to the pipeline.</span></span>

## <a name="evaluate-the-accuracy-of-the-model"></a><span data-ttu-id="58d29-265">모델의 정확도 평가</span><span class="sxs-lookup"><span data-stu-id="58d29-265">Evaluate the accuracy of the model</span></span>

1. <span data-ttu-id="58d29-266">`GenerateModel` 메서드의 다음 줄에 다음 코드를 추가하여 테스트 데이터를 로드하고 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-266">Load and transform the test data, by adding the following code to the next line of the `GenerateModel` method:</span></span>

    [!code-csharp[LoadAndTransformTestData](./snippets/image-classification/csharp/Program.cs#LoadAndTransformTestData "Load and transform test data")]

    <span data-ttu-id="58d29-267">모델을 평가하는 데 사용할 수 있는 몇 가지 샘플 이미지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-267">There are a few sample images that you can use to evaluate the model.</span></span> <span data-ttu-id="58d29-268">학습 데이터와 마찬가지로, 이러한 이미지도 모델에서 변환할 수 있도록 `IDataView`로 로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-268">Like the training data, these need to be loaded into an `IDataView`, so that they can be transformed by the model.</span></span>

1. <span data-ttu-id="58d29-269">`GenerateModel()` 메서드에 다음 코드를 추가하여 모델을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-269">Add the following code to the `GenerateModel()` method to evaluate the model:</span></span>

    [!code-csharp[Evaluate](./snippets/image-classification/csharp/Program.cs#Evaluate)]

    <span data-ttu-id="58d29-270">예측 세트가 있으면 [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) 메서드가 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-270">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method:</span></span>

    * <span data-ttu-id="58d29-271">모델을 평가합니다(예측 값을 테스트 데이터 세트 `labels`와 비교).</span><span class="sxs-lookup"><span data-stu-id="58d29-271">Assesses the model (compares the predicted values with the test dataset `labels`).</span></span>
    * <span data-ttu-id="58d29-272">모델 성능 메트릭을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-272">Returns the model performance metrics.</span></span>

1. <span data-ttu-id="58d29-273">모델 정확도 메트릭 표시</span><span class="sxs-lookup"><span data-stu-id="58d29-273">Display the model accuracy metrics</span></span>

    <span data-ttu-id="58d29-274">다음 코드를 사용하여 메트릭을 표시하고, 결과를 공유한 다음, 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-274">Use the following code to display the metrics, share the results, and then act on them:</span></span>

    [!code-csharp[DisplayMetrics](./snippets/image-classification/csharp/Program.cs#DisplayMetrics)]

    <span data-ttu-id="58d29-275">이미지 분류를 위해 다음 메트릭이 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-275">The following metrics are evaluated for image classification:</span></span>

    * <span data-ttu-id="58d29-276">`Log-loss` - [로그 손실](../resources/glossary.md#log-loss)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58d29-276">`Log-loss` - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="58d29-277">로그 손실을 가능한 한 0에 가깝게 합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-277">You want Log-loss to be as close to zero as possible.</span></span>
    * <span data-ttu-id="58d29-278">`Per class Log-loss`.</span><span class="sxs-lookup"><span data-stu-id="58d29-278">`Per class Log-loss`.</span></span> <span data-ttu-id="58d29-279">클래스별 로그 손실을 가능한 한 0에 가깝게 합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-279">You want per class Log-loss to be as close to zero as possible.</span></span>

1. <span data-ttu-id="58d29-280">다음 코드를 추가하여 학습된 모델을 다음 줄로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-280">Add the following code to return the trained model as the next line:</span></span>

    [!code-csharp[SaveModel](./snippets/image-classification/csharp/Program.cs#ReturnModel)]

## <a name="run-the-application"></a><span data-ttu-id="58d29-281">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-281">Run the application!</span></span>

1. <span data-ttu-id="58d29-282">MLContext 클래스를 만든 후 `Main` 메서드에서 `GenerateModel` 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-282">Add the call to `GenerateModel` in the `Main` method after the creation of the MLContext class:</span></span>

    [!code-csharp[CallGenerateModel](./snippets/image-classification/csharp/Program.cs#CallGenerateModel)]

1. <span data-ttu-id="58d29-283">`ClassifySingleImage()` 메서드 호출을 `Main` 메서드의 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-283">Add the call to the `ClassifySingleImage()` method as the next line of code in the `Main` method:</span></span>

    [!code-csharp[CallClassifySingleImage](./snippets/image-classification/csharp/Program.cs#CallClassifySingleImage)]

1. <span data-ttu-id="58d29-284">콘솔 앱을 실행합니다(Ctrl+F5).</span><span class="sxs-lookup"><span data-stu-id="58d29-284">Run your console app (Ctrl + F5).</span></span> <span data-ttu-id="58d29-285">다음 출력과 같은 결과가 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-285">Your results should be similar to the following output.</span></span>  <span data-ttu-id="58d29-286">경고 또는 처리 메시지가 표시될 수 있지만, 이해하기 쉽도록 이러한 메시지는 다음 결과에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-286">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

    ```console
    =============== Training classification model ===============
    Image: broccoli2.jpg predicted as: food with score: 0.8955513
    Image: pizza3.jpg predicted as: food with score: 0.9667718
    Image: teddy6.jpg predicted as: toy with score: 0.9797683
    =============== Classification metrics ===============
    LogLoss is: 0.0653774699265059
    PerClassLogLoss is: 0.110315812569315 , 0.0204391272836966 , 0
    =============== Making single image classification ===============
    Image: toaster3.jpg predicted as: appliance with score: 0.9646884
    ```

<span data-ttu-id="58d29-287">지금까지</span><span class="sxs-lookup"><span data-stu-id="58d29-287">Congratulations!</span></span> <span data-ttu-id="58d29-288">이제 ML.NET에서 `TensorFlow` 모델에 전이 학습을 적용하여 이미지 분류를 위한 기계 학습 모델을 성공적으로 빌드했습니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-288">You've now successfully built a machine learning model for image classification by applying transfer learning to a `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="58d29-289">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-289">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span>

<span data-ttu-id="58d29-290">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="58d29-290">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="58d29-291">문제 이해</span><span class="sxs-lookup"><span data-stu-id="58d29-291">Understand the problem</span></span>
> * <span data-ttu-id="58d29-292">미리 학습된 TensorFlow 모델을 ML.NET 파이프라인에 통합</span><span class="sxs-lookup"><span data-stu-id="58d29-292">Incorporate the pre-trained TensorFlow model into the ML.NET pipeline</span></span>
> * <span data-ttu-id="58d29-293">ML.NET 모델 학습 및 평가</span><span class="sxs-lookup"><span data-stu-id="58d29-293">Train and evaluate the ML.NET model</span></span>
> * <span data-ttu-id="58d29-294">테스트 이미지 분류</span><span class="sxs-lookup"><span data-stu-id="58d29-294">Classify a test image</span></span>

<span data-ttu-id="58d29-295">기계 학습 샘플 GitHub 리포지토리를 확인하여 확장된 이미지 분류 샘플을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="58d29-295">Check out the Machine Learning samples GitHub repository to explore an expanded image classification sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="58d29-296">dotnet/machinelearning-samples GitHub 리포지토리</span><span class="sxs-lookup"><span data-stu-id="58d29-296">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/)
