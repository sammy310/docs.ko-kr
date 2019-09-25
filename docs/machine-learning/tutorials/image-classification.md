---
title: '자습서: TensorFlow 이미지 분류자 재학습 - 전이 학습'
description: 전이 학습 및 ML.NET을 사용하여 이미지 분류 TensorFlow 모델을 재학습하는 방법을 알아봅니다. 원래 모델은 개별 이미지를 분류하도록 학습되었습니다. 재학습 후에는 새 모델이 이미지를 광범위한 범주로 구성합니다.
ms.date: 07/09/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: e069abe44b77b1dc31b78ecec1971ccc73f2e012
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054075"
---
# <a name="tutorial-retrain-a-tensorflow-image-classifier-with-transfer-learning-and-mlnet"></a><span data-ttu-id="b320d-105">자습서: 전이 학습 및 ML.NET을 사용하여 TensorFlow 이미지 분류자 재학습</span><span class="sxs-lookup"><span data-stu-id="b320d-105">Tutorial: Retrain a TensorFlow image classifier with transfer learning and ML.NET</span></span>

<span data-ttu-id="b320d-106">전이 학습 및 ML.NET을 사용하여 이미지 분류 TensorFlow 모델을 재학습하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-106">Learn how to retrain an image classification TensorFlow model with transfer learning and ML.NET.</span></span> <span data-ttu-id="b320d-107">원래 모델은 개별 이미지를 분류하도록 학습되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-107">The original model was trained to classify individual images.</span></span> <span data-ttu-id="b320d-108">재학습 후에는 새 모델이 이미지를 광범위한 범주로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-108">After retraining, the new model organizes the images into broad categories.</span></span> 

<span data-ttu-id="b320d-109">[이미지 분류](https://en.wikipedia.org/wiki/Outline_of_object_recognition) 모델을 처음부터 학습시키려면 수백만 개의 매개 변수, 많은 레이블 지정 학습 데이터 및 많은 양의 컴퓨팅 리소스(수백 시간의 GPU 시간)를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-109">Training an [Image Classification](https://en.wikipedia.org/wiki/Outline_of_object_recognition) model from scratch requires setting millions of parameters, a ton of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="b320d-110">사용자 지정 모델을 처음부터 학습시키는 것만큼 효과적이지는 않지만, 전이 학습을 사용하면 수천 개 이미지 및 수백만 개 레이블 지정 이미지를 사용하여 이 프로세스를 간소화하고 사용자 지정 모델을 매우 빠르게 빌드할 수 있습니다(GPU가 없는 머신에서는 1시간 안에 가능).</span><span class="sxs-lookup"><span data-stu-id="b320d-110">While not as effective as training a custom model from scratch, transfer learning allows you to shortcut this process by working with thousands of images vs. millions of labeled images and build a customized model fairly quickly (within an hour on a machine without a GPU).</span></span>

<span data-ttu-id="b320d-111">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="b320d-112">문제 이해</span><span class="sxs-lookup"><span data-stu-id="b320d-112">Understand the problem</span></span>
> * <span data-ttu-id="b320d-113">미리 학습된 모델 다시 사용 및 조정</span><span class="sxs-lookup"><span data-stu-id="b320d-113">Reuse and tune the pre-trained model</span></span>
> * <span data-ttu-id="b320d-114">이미지 분류</span><span class="sxs-lookup"><span data-stu-id="b320d-114">Classify Images</span></span>

## <a name="what-is-transfer-learning"></a><span data-ttu-id="b320d-115">전이 학습이란?</span><span class="sxs-lookup"><span data-stu-id="b320d-115">What is transfer learning?</span></span>

<span data-ttu-id="b320d-116">유사한 문제를 해결하도록 미리 학습된 모델을 다시 사용하고 문제를 해결할 수 있도록 해당 모델 계층의 전부 또는 일부를 다시 학습시킬 수 있다면 어떻게 될까요?</span><span class="sxs-lookup"><span data-stu-id="b320d-116">What if you could reuse a model that's already been pre trained to solve a similar problem and retrain either all or some of the layers of that model to make it solve your problem?</span></span> <span data-ttu-id="b320d-117">이미 학습된 모델의 일부를 다시 사용하여 새 모델을 빌드하는 기술을 [전이 학습](https://en.wikipedia.org/wiki/Transfer_learning)이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-117">This technique of reusing part of an already trained model to build a new model is known as [transfer learning](https://en.wikipedia.org/wiki/Transfer_learning).</span></span>

## <a name="image-classification-sample-overview"></a><span data-ttu-id="b320d-118">이미지 분류 샘플 개요</span><span class="sxs-lookup"><span data-stu-id="b320d-118">Image classification sample overview</span></span>

<span data-ttu-id="b320d-119">이 샘플은 미리 학습된 모델을 다시 사용하여 적은 양의 학습 데이터가 포함된 이미지를 분류하는 방식으로 ML.NET을 사용하여 이미지를 분류하는 콘솔 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-119">The sample is a console application that uses ML.NET to build an image classifier by reusing a pre-trained model to classify images with a small amount of training data.</span></span>

<span data-ttu-id="b320d-120">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-120">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span> <span data-ttu-id="b320d-121">기본적으로 이 자습서의 .NET 프로젝트 구성은 .NET Core 2.2를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-121">Note that by default, the .NET project configuration for this tutorial targets .NET core 2.2.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b320d-122">전제 조건</span><span class="sxs-lookup"><span data-stu-id="b320d-122">Prerequisites</span></span>

* <span data-ttu-id="b320d-123">“.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017).</span><span class="sxs-lookup"><span data-stu-id="b320d-123">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span> 

* <span data-ttu-id="b320d-124">Microsoft.ML 1.0.0 Nuget 패키지</span><span class="sxs-lookup"><span data-stu-id="b320d-124">Microsoft.ML 1.0.0 Nuget package</span></span>
* <span data-ttu-id="b320d-125">Microsoft.ML.ImageAnalytics 1.0.0 Nuget 패키지</span><span class="sxs-lookup"><span data-stu-id="b320d-125">Microsoft.ML.ImageAnalytics 1.0.0 Nuget package</span></span>
* <span data-ttu-id="b320d-126">Microsoft.ML.TensorFlow 0.12.0 Nuget 패키지</span><span class="sxs-lookup"><span data-stu-id="b320d-126">Microsoft.ML.TensorFlow 0.12.0 Nuget package</span></span>

* [<span data-ttu-id="b320d-127">자습서 자산 디렉터리 .ZIP 파일</span><span class="sxs-lookup"><span data-stu-id="b320d-127">The tutorial assets directory .ZIP file</span></span>](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)

* [<span data-ttu-id="b320d-128">InceptionV1 기계 학습 모델</span><span class="sxs-lookup"><span data-stu-id="b320d-128">The InceptionV1 machine learning model</span></span>](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="b320d-129">적절한 기계 학습 작업 선택</span><span class="sxs-lookup"><span data-stu-id="b320d-129">Select the appropriate machine learning task</span></span>

<span data-ttu-id="b320d-130">[딥 러닝](https://en.wikipedia.org/wiki/Deep_learning)은 Computer Vision 및 음성 인식 같은 혁신적인 영역인 기계 학습의 하위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-130">[Deep learning](https://en.wikipedia.org/wiki/Deep_learning) is a subset of Machine Learning, which is revolutionizing areas like Computer Vision and Speech Recognition.</span></span>

<span data-ttu-id="b320d-131">딥 러닝 모델은 여러 학습 계층이 포함된 대규모 [레이블 지정 데이터](https://en.wikipedia.org/wiki/Labeled_data) 및 [신경망](https://en.wikipedia.org/wiki/Artificial_neural_network) 세트를 사용하여 학습됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-131">Deep learning models are trained by using large sets of [labeled data](https://en.wikipedia.org/wiki/Labeled_data) and [neural networks](https://en.wikipedia.org/wiki/Artificial_neural_network) that contain multiple learning layers.</span></span> <span data-ttu-id="b320d-132">딥 러닝</span><span class="sxs-lookup"><span data-stu-id="b320d-132">Deep learning:</span></span>

* <span data-ttu-id="b320d-133">Computer Vision 같은 일부 작업에서 더 효과적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-133">Performs better on some tasks like Computer Vision.</span></span>

* <span data-ttu-id="b320d-134">엄청난 데이터양에서도 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-134">Performs well on huge data amounts.</span></span>

<span data-ttu-id="b320d-135">이미지 분류는 다음과 같은 여러 범주로 이미지를 자동으로 분류할 수 있는 일반적인 기계 학습 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-135">Image Classification is a common Machine Learning task that allows us to automatically classify images into multiple categories such as:</span></span>

* <span data-ttu-id="b320d-136">이미지에서 사람 얼굴을 인식하는지 여부.</span><span class="sxs-lookup"><span data-stu-id="b320d-136">Detecting a human face in an image or not.</span></span>
* <span data-ttu-id="b320d-137">고양이 및 개 인식.</span><span class="sxs-lookup"><span data-stu-id="b320d-137">Detecting Cats vs. dogs.</span></span>

 <span data-ttu-id="b320d-138">또는 다음 이미지와 같이 이미지가 음식, 장난감 또는 어플라이언스인지 확인:</span><span class="sxs-lookup"><span data-stu-id="b320d-138">Or as in the following images determining if an image is a(n)  food, toy, or appliance:</span></span>

<span data-ttu-id="b320d-139">![피자 이미지](./media/image-classification/220px-Pepperoni_pizza.jpg)
![테디 베어 이미지](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![토스터 이미지](./media/image-classification/193px-Broodrooster.jpg)</span><span class="sxs-lookup"><span data-stu-id="b320d-139">![pizza image](./media/image-classification/220px-Pepperoni_pizza.jpg)
![teddy bear image](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![toaster image](./media/image-classification/193px-Broodrooster.jpg)</span></span>

>[!Note]
> <span data-ttu-id="b320d-140">앞의 이미지는 Wikimedia Commons에 속하고 다음 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-140">The preceding images belong to Wikimedia Commons and are attributed as follows:</span></span>
>
> * <span data-ttu-id="b320d-141">“220px-Pepperoni_pizza.jpg” 공용 도메인, https://commons.wikimedia.org/w/index.php?curid=79505,</span><span class="sxs-lookup"><span data-stu-id="b320d-141">"220px-Pepperoni_pizza.jpg" Public Domain, https://commons.wikimedia.org/w/index.php?curid=79505,</span></span>
> * <span data-ttu-id="b320d-142">“119px-Nalle_-_a_small_brown_teddy_bear.jpg” 작성자: [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - 직접 사진 촬영, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span><span class="sxs-lookup"><span data-stu-id="b320d-142">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" By [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Self-photographed, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span></span>
> * <span data-ttu-id="b320d-143">“193px-Broodrooster.jpg” 작성자: [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - 직접 작업, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span><span class="sxs-lookup"><span data-stu-id="b320d-143">"193px-Broodrooster.jpg" By [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Own work, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span></span>

<span data-ttu-id="b320d-144">전이 학습에는 모든 계층 다시 학습 및 끝에서 두 번째 계층과 같은 몇 가지 전략이 포함됩니다.  </span><span class="sxs-lookup"><span data-stu-id="b320d-144">Transfer learning includes a few strategies, such as *retrain all layers* and *penultimate layer*.</span></span> <span data-ttu-id="b320d-145">이 자습서에서는 끝에서 두 번째 계층 전략을 사용하는 방법을 설명하고 보여 줍니다. </span><span class="sxs-lookup"><span data-stu-id="b320d-145">This tutorial will explain and show how to use the *penultimate layer strategy*.</span></span> <span data-ttu-id="b320d-146">끝에서 두 번째 계층 전략에서는 특정 문제를 해결하기 위해 미리 학습된 모델을 다시 사용합니다. </span><span class="sxs-lookup"><span data-stu-id="b320d-146">The *penultimate layer strategy* reuses a model that's already been pre-trained to solve a specific problem.</span></span> <span data-ttu-id="b320d-147">그런 다음, 새 문제를 해결할 수 있도록 해당 모델의 마지막 계층을 다시 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-147">The strategy then retrains the final layer of that model to make it solve a new problem.</span></span> <span data-ttu-id="b320d-148">미리 학습된 모델을 새 모델의 일부로 다시 사용하면 상당한 시간과 리소스가 절약됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-148">Reusing the pre-trained model as part of your new model will save significant time and resources.</span></span>

<span data-ttu-id="b320d-149">이 이미지 분류 모델의 경우 TensorFlow 모델에서 전체 이미지를 “우산”, “저지” 및 “식기 세척기” 같은 수천 개의 클래스로 분류하려고 시도하는 `ImageNet` 데이터 세트를 기반으로 학습된 널리 사용되는 이미지 인식 모델인 [Inception 모델](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)을 다시 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-149">Your image classification model reuses the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), a popular image recognition model trained on the `ImageNet` dataset where the TensorFlow model tries to classify entire images into a thousand classes, like “Umbrella”, “Jersey”, and “Dishwasher”.</span></span>

<span data-ttu-id="b320d-150">`Inception v1 model`은 [심층 나선형 신경망](https://en.wikipedia.org/wiki/Convolutional_neural_network)으로 분류될 수 있고, 일부 도메인의 인간 수행능력과 일치하거나 이를 초과하는 합리적인 성과를 어려운 시각적 인식 작업에서 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-150">The `Inception v1 model` can be classified as a [deep convolutional neural network](https://en.wikipedia.org/wiki/Convolutional_neural_network) and can achieve reasonable performance on hard visual recognition tasks, matching or exceeding human performance in some domains.</span></span> <span data-ttu-id="b320d-151">모델/알고리즘은 여러 연구원에 의해 개발되었고 다음 원본 논문을 기반으로 합니다. [“Rethinking the Inception Architecture for Computer Vision” by Szegedy, et. al.](https://arxiv.org/abs/1512.00567)(Computer Vision에 대한 Inception 아키텍처 재고려, 작성자: Szegedy 외)</span><span class="sxs-lookup"><span data-stu-id="b320d-151">The model/algorithm was developed by multiple researchers and based on the original paper: ["Rethinking the Inception Architecture for Computer Vision” by Szegedy, et. al.](https://arxiv.org/abs/1512.00567)</span></span>

<span data-ttu-id="b320d-152">`Inception model`은 수천 개의 이미지를 기반으로 미리 학습되었으므로 이미지 식별에 필요한 [이미지 기능](https://en.wikipedia.org/wiki/Feature_(computer_vision))을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-152">Because the `Inception model` has already been pre trained on thousands of different images, it contains the [image features](https://en.wikipedia.org/wiki/Feature_(computer_vision)) needed for image identification.</span></span> <span data-ttu-id="b320d-153">하위 이미지 기능 계층은 간단한 기능(예: 가장자리)을 인식하고 상위 계층은 더 복잡한 기능(예: 셰이프)을 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-153">The lower image feature layers recognize simple features (such as edges) and the higher layers recognize more complex features (such as shapes).</span></span> <span data-ttu-id="b320d-154">이미지 분류 방법을 이미 이해하는 미리 학습된 모델로 시작하므로 마지막 계층은 훨씬 더 작은 데이터 세트를 기반으로 학습됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-154">The final layer is trained against a much smaller set of data because you're starting with a pre trained model that already understands how to classify images.</span></span> <span data-ttu-id="b320d-155">모델을 사용하여 세 개 이상의 범주를 분류할 수 있으므로 이 예제는 [다중 클래스 분류자](../resources/tasks.md#multiclass-classification)의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-155">As your model allows you to classify more than two categories, this is an example of a [multi-class classifier](../resources/tasks.md#multiclass-classification).</span></span> 

<span data-ttu-id="b320d-156">`TensorFlow`는 심층 신경망(및 일반 숫자 계산)을 학습할 수 있는 널리 사용되는 딥 러닝 및 기계 학습 도구 키트로서, ML.NET에서 `transformer`로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-156">`TensorFlow` is a popular deep learning and machine learning toolkit that enables training deep neural networks (and general numeric computations), and is implemented as a `transformer` in ML.NET.</span></span> <span data-ttu-id="b320d-157">이 자습서에서는 이 도구 키트를 사용하여 `Inception model`을 다시 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-157">For this tutorial, it's used to reuse the `Inception model`.</span></span>

<span data-ttu-id="b320d-158">다음 다이어그램과 같이 .NET Core 또는 .NET Framework 애플리케이션에서 ML.NET NuGet 패키지에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-158">As shown in the following diagram, you add a reference to the ML.NET NuGet packages in your .NET Core or .NET Framework applications.</span></span> <span data-ttu-id="b320d-159">기본적으로 ML.NET은 점수를 매기기 위해 기존 학습된 `TensorFlow` 모델 파일을 로드하는 코드를 작성하는 데 사용할 수 있는 네이티브 `TensorFlow` 라이브러리를 포함하고 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-159">Under the covers, ML.NET includes and references the native `TensorFlow` library that allows you to write code that loads an existing trained `TensorFlow` model file for scoring.</span></span>  

![TensorFlow 변환 ML.NET 아키텍처 다이어그램](./media/image-classification/tensorflow-mlnet.png)

<span data-ttu-id="b320d-161">`Inception model`은 이미지를 천 개의 범주로 분류하도록 학습되지만, 더 작은 범주 세트 및 해당 범주로만 이미지를 분류해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-161">The `Inception model` is trained to classify images into a thousand categories, but you need to classify images in a smaller category set, and only those categories.</span></span> <span data-ttu-id="b320d-162">`transfer learning`의 `transfer` 부분을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-162">Enter the `transfer` part of `transfer learning`.</span></span> <span data-ttu-id="b320d-163">이미지를 인식하고 사용자 지정 이미지 분류자의 제한된 새 범주로 분류하는 `Inception model`의 기능을 전이할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-163">You can transfer the `Inception model`'s ability to recognize and classify images to the new limited categories of your custom image classifier.</span></span>  

 <span data-ttu-id="b320d-164">다음 세 가지 범주 세트를 사용하여 해당 모델의 마지막 계층을 다시 학습시키려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-164">You're going to retrain the final layer of that model using a set of three categories:</span></span>

* <span data-ttu-id="b320d-165">음식</span><span class="sxs-lookup"><span data-stu-id="b320d-165">Food</span></span>
* <span data-ttu-id="b320d-166">장난감</span><span class="sxs-lookup"><span data-stu-id="b320d-166">Toy</span></span>
* <span data-ttu-id="b320d-167">어플라이언스</span><span class="sxs-lookup"><span data-stu-id="b320d-167">Appliance</span></span>

<span data-ttu-id="b320d-168">계층은 [다항 로지스틱 회귀 분석 알고리즘](https://en.wikipedia.org/wiki/Multinomial_logistic_regression)을 사용하여 최대한 빨리 올바른 범주를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-168">Your layer uses a [multinomial logistic regression algorithm](https://en.wikipedia.org/wiki/Multinomial_logistic_regression) to find the correct category as quickly as possible.</span></span> <span data-ttu-id="b320d-169">이 알고리즘은 올바른 범주에 하나의 값을 제공하고 다른 범주에 0 값을 제공하여 응답을 결정하기 위해 확률을 사용하여 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-169">This algorithm classifies using probabilities to determine the answer, giving a one value to the correct category and a zero value to the others.</span></span>  

### <a name="dataset"></a><span data-ttu-id="b320d-170">데이터 세트</span><span class="sxs-lookup"><span data-stu-id="b320d-170">DataSet</span></span>

<span data-ttu-id="b320d-171">두 개의 데이터 소스인 `.tsv` 파일 및 이미지 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-171">There are two data sources: the `.tsv` file, and the image files.</span></span>  <span data-ttu-id="b320d-172">`tags.tsv` 파일에는 두 개의 열이 있습니다. 첫 번째 열은 `ImagePath`로 정의되고 두 번째 열은 이미지에 해당하는 `Label`입니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-172">The `tags.tsv` file contains two columns: the first one is defined as `ImagePath` and the second one is the `Label` corresponding to the image.</span></span> <span data-ttu-id="b320d-173">다음 예제 파일에는 머리글 행이 없고 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-173">The following example file doesn't have a header row, and looks like this:</span></span>

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

<span data-ttu-id="b320d-174">학습 및 테스트 이미지는 zip 파일로 다운로드할 수 있는 자산 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-174">The training and testing images are located in the assets folders that you'll download in a zip file.</span></span> <span data-ttu-id="b320d-175">이 이미지는 Wikimedia Commons에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-175">These images belong to Wikimedia Commons.</span></span>
> <span data-ttu-id="b320d-176">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), 무료 미디어 리포지토리.*</span><span class="sxs-lookup"><span data-stu-id="b320d-176">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), the free media repository.*</span></span> <span data-ttu-id="b320d-177">2018년 10월 17일 10시 48분 검색된 위치:</span><span class="sxs-lookup"><span data-stu-id="b320d-177">Retrieved 10:48, October 17, 2018 from:</span></span>  
> https://commons.wikimedia.org/wiki/Pizza  
> https://commons.wikimedia.org/wiki/Toaster  
> https://commons.wikimedia.org/wiki/Teddy_bear  

## <a name="create-a-console-application"></a><span data-ttu-id="b320d-178">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="b320d-178">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="b320d-179">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="b320d-179">Create a project</span></span>

1. <span data-ttu-id="b320d-180">"TransferLearningTF"라는 **.NET Core 콘솔 애플리케이션**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-180">Create a **.NET Core Console Application** called "TransferLearningTF".</span></span>

2. <span data-ttu-id="b320d-181">**Microsoft.ML NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-181">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="b320d-182">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-182">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="b320d-183">패키지 소스로 “nuget.org”를 선택하고, [찾아보기] 탭을 선택하고, **Microsoft.ML**을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-183">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span> <span data-ttu-id="b320d-184">**버전** 드롭다운을 클릭하고, 목록에서 **1.0.0** 패키지를 선택하고, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-184">Click on the **Version** drop-down, select the **1.0.0** package in the list, and select the **Install** button.</span></span> <span data-ttu-id="b320d-185">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-185">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="b320d-186">**Microsoft.ML.ImageAnalytics v1.0.0** 및 **Microsoft.ML.TensorFlow v0.12.0**에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-186">Repeat these steps for **Microsoft.ML.ImageAnalytics v1.0.0** and **Microsoft.ML.TensorFlow v0.12.0**.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="b320d-187">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="b320d-187">Prepare your data</span></span>

1. <span data-ttu-id="b320d-188">[프로젝트 자산 디렉터리 zip 파일](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)을 다운로드하고 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-188">Download [The project assets directory zip file](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip), and unzip.</span></span>

2. <span data-ttu-id="b320d-189">`assets` 디렉터리를 *TransferLearningTF* 프로젝트 디렉터리에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-189">Copy the `assets` directory into your *TransferLearningTF* project directory.</span></span> <span data-ttu-id="b320d-190">이 디렉터리 및 해당 하위 디렉터리에는 이 자습서에 필요한 데이터 및 지원 파일이 포함되어 있습니다(다음 단계에서 다운로드 및 추가하는 Inception 모델 제외).</span><span class="sxs-lookup"><span data-stu-id="b320d-190">This directory and its subdirectories contain the data and support files (except for the Inception model, which you'll download and add in the next step) needed for this tutorial.</span></span>

3. <span data-ttu-id="b320d-191">[Inception 모델](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)을 다운로드하고 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-191">Download the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), and unzip.</span></span>

4. <span data-ttu-id="b320d-192">방금 *TransferLearningTF* 프로젝트 `assets\inputs-train\inception` 디렉터리에 압축을 푼 `inception5h` 디렉터리의 콘텐츠를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-192">Copy the contents of the `inception5h` directory just unzipped into your *TransferLearningTF* project `assets\inputs-train\inception` directory.</span></span> <span data-ttu-id="b320d-193">이 디렉터리에는 다음 이미지와 같이 이 자습서에 필요한 모델 및 추가 지원 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-193">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![Inception 디렉터리 콘텐츠](./media/image-classification/inception-files.png)

5. <span data-ttu-id="b320d-195">솔루션 탐색기에서 자산 디렉터리 및 하위 디렉터리의 각 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-195">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="b320d-196">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-196">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="b320d-197">클래스 만들기 및 경로 정의</span><span class="sxs-lookup"><span data-stu-id="b320d-197">Create classes and define paths</span></span>

<span data-ttu-id="b320d-198">*Program.cs* 파일 맨 위에 다음 추가 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-198">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

<span data-ttu-id="b320d-199">다양한 자산의 경로를 저장할 전역 필드와 `LabelTokey`, `ImageReal` 및 `PredictedLabelValue`에 대한 전역 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-199">Create global fields to hold the paths to the various assets, and global variables for the `LabelTokey`,`ImageReal`, and  `PredictedLabelValue`:</span></span>

* <span data-ttu-id="b320d-200">`_assetsPath`에는 자산 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-200">`_assetsPath` has the path to the assets.</span></span>
* <span data-ttu-id="b320d-201">`_trainTagsTsv`에는 학습 이미지 데이터 태그 tsv 파일의 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-201">`_trainTagsTsv` has the path to the training image data tags tsv file.</span></span>
* <span data-ttu-id="b320d-202">`_predictTagsTsv`에는 예측 이미지 데이터 태그 tsv 파일의 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-202">`_predictTagsTsv` has the path to the prediction image data tags tsv file.</span></span>
* <span data-ttu-id="b320d-203">`_trainImagesFolder`에는 모델을 학습시키는 데 사용되는 이미지의 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-203">`_trainImagesFolder` has the path to the images used to train the model.</span></span>
* <span data-ttu-id="b320d-204">`_predictImagesFolder`에는 학습된 모델별로 분류할 이미지의 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-204">`_predictImagesFolder` has the path to the images to be classified by the trained model.</span></span>
* <span data-ttu-id="b320d-205">`_inceptionPb`에는 모델을 다시 학습시키는 데 다시 사용되는 미리 학습된 Inception 모델의 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-205">`_inceptionPb` has the path to the pre-trained Inception model to be reused to retrain your model.</span></span>
* <span data-ttu-id="b320d-206">`_inputImageClassifierZip`에는 학습된 모델이 로드되는 소스 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-206">`_inputImageClassifierZip` has the path where the trained model is loaded from.</span></span>
* <span data-ttu-id="b320d-207">`_outputImageClassifierZip`에는 학습된 모델이 저장되는 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-207">`_outputImageClassifierZip` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="b320d-208">`LabelTokey`는 키에 매핑된 `Label` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-208">`LabelTokey` is the `Label` value mapped to a key.</span></span>
* <span data-ttu-id="b320d-209">`ImageReal`은 예측된 이미지 값을 포함하는 열입니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-209">`ImageReal`  is the column containing the predicted image value.</span></span>
* <span data-ttu-id="b320d-210">`PredictedLabelValue`는 예측된 레이블 값을 포함하는 열입니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-210">`PredictedLabelValue` is the column containing the predicted label value.</span></span>

<span data-ttu-id="b320d-211">`Main` 메서드 바로 위의 줄에 다음 코드를 추가하여 해당 경로와 다른 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-211">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="b320d-212">입력 데이터 및 예측에 대한 일부 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-212">Create some classes for your input data, and predictions.</span></span> <span data-ttu-id="b320d-213">새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-213">Add a new class to your project:</span></span>

1. <span data-ttu-id="b320d-214">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-214">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="b320d-215">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *ImageData.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-215">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImageData.cs*.</span></span> <span data-ttu-id="b320d-216">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-216">Then, select the **Add** button.</span></span>

    <span data-ttu-id="b320d-217">*ImageData.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-217">The *ImageData.cs* file opens in the code editor.</span></span> <span data-ttu-id="b320d-218">다음 `using` 문을 *ImageData.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-218">Add the following `using` statement to the top of *ImageData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#AddUsings)]

<span data-ttu-id="b320d-219">기존 클래스 정의를 제거하고 `ImageData` 클래스에 대한 다음 코드를 *ImageData.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-219">Remove the existing class definition and add the following code for the `ImageData` class to the *ImageData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#DeclareTypes)]

<span data-ttu-id="b320d-220">`ImageData`는 입력 이미지 데이터 클래스이며 다음 <xref:System.String> 필드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-220">`ImageData` is the input image data class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="b320d-221">`ImagePath`에는 이미지 파일 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-221">`ImagePath` contains the image file name.</span></span>
* <span data-ttu-id="b320d-222">`Label`에는 이미지 레이블의 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-222">`Label` contains a value for the image label.</span></span>

<span data-ttu-id="b320d-223">`ImagePrediction`의 새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-223">Add a new class to your project for `ImagePrediction`:</span></span>

1. <span data-ttu-id="b320d-224">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-224">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="b320d-225">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *ImagePrediction.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-225">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImagePrediction.cs*.</span></span> <span data-ttu-id="b320d-226">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-226">Then, select the **Add** button.</span></span>

    <span data-ttu-id="b320d-227">*ImagePrediction.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-227">The *ImagePrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="b320d-228">*ImagePrediction.cs* 맨 위에서 `System.Collections.Generic` 및 `System.Text` `using` 문을 모두 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-228">Remove both the `System.Collections.Generic` and the `System.Text` `using` statements at the top of *ImagePrediction.cs*:</span></span>

<span data-ttu-id="b320d-229">기존 클래스 정의를 제거하고 `ImagePrediction` 클래스가 포함된 다음 코드를 *ImagePrediction.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-229">Remove the existing class definition and add the following code, which has the `ImagePrediction` class, to the *ImagePrediction.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/ImagePrediction.cs#DeclareTypes)]

<span data-ttu-id="b320d-230">`ImagePrediction`은 이미지 예측 클래스이며 다음 필드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-230">`ImagePrediction` is the image prediction class and has the following fields:</span></span>

* <span data-ttu-id="b320d-231">`Score`에는 지정된 이미지 분류를 위한 신뢰율이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-231">`Score` contains the confidence percentage for a given image classification.</span></span>
* <span data-ttu-id="b320d-232">`PredictedLabelValue`에는 예측된 이미지 분류 레이블의 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-232">`PredictedLabelValue` contains a value for the predicted image classification label.</span></span>

<span data-ttu-id="b320d-233">`ImagePrediction`은 모델이 학습된 후 예측에 사용되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-233">`ImagePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="b320d-234">이 클래스에는 이미지 경로의 `string`(`ImagePath`)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-234">It has a `string` (`ImagePath`) for the image path.</span></span> <span data-ttu-id="b320d-235">`Label`은 모델을 다시 사용하고 다시 학습시키는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-235">The `Label` is used to reuse and retrain the model.</span></span> <span data-ttu-id="b320d-236">`PredictedLabelValue`은 예측 및 평가 중에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-236">The `PredictedLabelValue` is used during prediction and evaluation.</span></span> <span data-ttu-id="b320d-237">평가를 위해 학습 데이터가 있는 입력, 예측 값 및 모델이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-237">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="b320d-238">[MLContext 클래스](xref:Microsoft.ML.MLContext)는 모든 ML.NET 작업의 시작점이며, `mlContext`를 초기화하면 모델 생성 워크플로 개체 간에 공유할 수 있는 새 ML.NET 환경이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-238">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="b320d-239">개념적으로 Entity Framework의 `DBContext`와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-239">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="b320d-240">Main에서 변수 초기화</span><span class="sxs-lookup"><span data-stu-id="b320d-240">Initialize variables in Main</span></span>

<span data-ttu-id="b320d-241">`MLContext`의 새 인스턴스를 사용하여 `mlContext` 변수를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-241">Initialize the `mlContext` variable with a new instance of `MLContext`.</span></span>  <span data-ttu-id="b320d-242">`Main` 메서드에서 `Console.WriteLine("Hello World!")` 줄을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-242">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

### <a name="create-a-struct-for-default-parameters"></a><span data-ttu-id="b320d-243">기본 매개 변수의 구조체 만들기</span><span class="sxs-lookup"><span data-stu-id="b320d-243">Create a struct for default parameters</span></span>

<span data-ttu-id="b320d-244">Inception 모델에는 전달해야 하는 여러 가지 기본 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-244">The Inception model has several default parameters you need to pass in.</span></span> <span data-ttu-id="b320d-245">`Main()` 메서드 바로 뒤에서 다음 코드를 사용하여 기본 매개 변수 값을 친숙한 이름에 매핑하는 구조체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-245">Create a struct to map the default parameter values to friendly names with the following code, just after the `Main()` method:</span></span>

[!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a><span data-ttu-id="b320d-246">표시 유틸리티 메서드 만들기</span><span class="sxs-lookup"><span data-stu-id="b320d-246">Create a display utility method</span></span>

<span data-ttu-id="b320d-247">이미지 데이터와 관련 예측을 여러 번 표시하므로 표시 유틸리티 메서드를 만들어 이미지 및 예측 결과 표시를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-247">Since you'll display the image data and the related predictions more than once, create a display utility method to handle displaying the image and prediction results.</span></span>

<span data-ttu-id="b320d-248">`DisplayResults()` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-248">The `DisplayResults()` method executes the following tasks:</span></span>

* <span data-ttu-id="b320d-249">예측 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-249">Displays the predicted results.</span></span>

<span data-ttu-id="b320d-250">다음 코드를 사용하여 `InceptionSettings` 구조체 바로 뒤에 `DisplayResults()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-250">Create the `DisplayResults()` method, just after the `InceptionSettings` struct, using the following code:</span></span>

```csharp
private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
{

}
```

<span data-ttu-id="b320d-251">`Transform()` 메서드는 예측 필드와 함께 `ImagePrediction`에서 `ImagePath`를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-251">The `Transform()` method populated `ImagePath` in `ImagePrediction` along with the predicted fields.</span></span> <span data-ttu-id="b320d-252">ML.NET 프로세스를 진행하면서 각 구성 요소가 열을 추가하므로 결과를 쉽게 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-252">As the ML.NET process progresses, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

<span data-ttu-id="b320d-253">두 이미지 분류 메서드에서 `DisplayResults()` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-253">You'll call the `DisplayResults()` method in the two image classification methods.</span></span>

### <a name="create-a-tsv-file-utility-method"></a><span data-ttu-id="b320d-254">.tsv 파일 유틸리티 메서드 만들기</span><span class="sxs-lookup"><span data-stu-id="b320d-254">Create a .tsv file utility method</span></span>

<span data-ttu-id="b320d-255">`ReadFromTsv()` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-255">The `ReadFromTsv()` method executes the following tasks:</span></span>

* <span data-ttu-id="b320d-256">이미지 데이터 `tags.tsv` 파일을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-256">Reads the image data `tags.tsv` file.</span></span>
* <span data-ttu-id="b320d-257">이미지 파일 이름에 파일 경로를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-257">Adds the file path to the image file name.</span></span>
* <span data-ttu-id="b320d-258">파일 데이터를 IEnumerable`ImageData` 개체로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-258">Loads the file data into an IEnumerable`ImageData` object.</span></span>

<span data-ttu-id="b320d-259">다음 코드를 사용하여 `PairAndDisplayResults()` 메서드 바로 뒤에 `ReadFromTsv()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-259">Create the `ReadFromTsv()` method, just after the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
{

}
```

<span data-ttu-id="b320d-260">다음 코드는 `tags.tsv` 파일을 구문 분석하여 `ImagePath` 속성의 이미지 파일 이름에 파일 경로를 추가하고 로드한 다음, `Label`을 `ImageData` 개체로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-260">The following code parses through the `tags.tsv` file to add the file path to the image file name for the `ImagePath` property and load it and the `Label` into an `ImageData` object.</span></span> <span data-ttu-id="b320d-261">`ReadFromTsv()` 메서드의 첫 번째 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-261">Add it as the first line of the `ReadFromTsv()` method.</span></span>  <span data-ttu-id="b320d-262">예측 결과를 표시하려면 정규화된 파일 경로가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-262">You need the fully qualified file path to display the prediction results.</span></span>

[!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]
<span data-ttu-id="b320d-263">ML.NET에는 세 가지 주요 개념이 있습니다. [데이터](../resources/glossary.md#data), [변환기](../resources/glossary.md#transformer) 및 [평가자](../resources/glossary.md#estimator).</span><span class="sxs-lookup"><span data-stu-id="b320d-263">There are three major concepts in ML.NET: [Data](../resources/glossary.md#data), [Transformers](../resources/glossary.md#transformer), and [Estimators](../resources/glossary.md#estimator).</span></span>

## <a name="reuse-and-tune-pre-trained-model"></a><span data-ttu-id="b320d-264">미리 학습된 모델 다시 사용 및 조정</span><span class="sxs-lookup"><span data-stu-id="b320d-264">Reuse and tune pre-trained model</span></span>

<span data-ttu-id="b320d-265">`ReuseAndTuneInceptionModel()` 메서드에 다음 호출을 `Main()` 메서드의 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-265">Add the following call to the `ReuseAndTuneInceptionModel()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallReuseAndTuneInceptionModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReuseAndTuneInceptionModel)]

<span data-ttu-id="b320d-266">`ReuseAndTuneInceptionModel()` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-266">The `ReuseAndTuneInceptionModel()` method executes the following tasks:</span></span>

* <span data-ttu-id="b320d-267">데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-267">Loads the data</span></span>
* <span data-ttu-id="b320d-268">데이터를 추출하고 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-268">Extracts and transforms the data.</span></span>
* <span data-ttu-id="b320d-269">TensorFlow 모델에 점수를 매깁니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-269">Scores the TensorFlow model.</span></span>
* <span data-ttu-id="b320d-270">모델을 조정(다시 학습)합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-270">Tunes (retrains) the model.</span></span>
* <span data-ttu-id="b320d-271">모델 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-271">Displays model results.</span></span>
* <span data-ttu-id="b320d-272">모델을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-272">Evaluates the model.</span></span>
* <span data-ttu-id="b320d-273">모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-273">Returns the model.</span></span>

<span data-ttu-id="b320d-274">다음 코드를 사용하여 `InceptionSettings` 구조체 바로 뒤 및 `DisplayResults()` 메서드 바로 앞에 `ReuseAndTuneInceptionModel()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-274">Create the `ReuseAndTuneInceptionModel()` method, just after the `InceptionSettings` struct and just before the `DisplayResults()` method, using the following code:</span></span>

```csharp
public static ITransformer ReuseAndTuneInceptionModel(MLContext mlContext, string dataLocation, string imagesFolder, string inputModelLocation, string outputModelLocation)
{

}
```

### <a name="load-the-data"></a><span data-ttu-id="b320d-275">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="b320d-275">Load the data</span></span>

<span data-ttu-id="b320d-276">ML.NET의 데이터는 [IDataView 클래스](xref:Microsoft.ML.IDataView)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-276">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="b320d-277">`IDataView`는 표 형식 데이터(숫자 및 텍스트)를 유연하고 효율적으로 설명하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-277">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="b320d-278">데이터를 텍스트 파일 또는 실시간(예: SQL 데이터베이스 또는 로그 파일)에서 `IDataView` 개체로 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-278">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="b320d-279">`MLContext.Data.LoadFromTextFile` 래퍼를 사용하여 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-279">Load the data using the `MLContext.Data.LoadFromTextFile` wrapper.</span></span> <span data-ttu-id="b320d-280">`ReuseAndTuneInceptionModel()` 메서드에 아래 코드를 다음 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-280">Add the following code as the next line in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

### <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="b320d-281">기능 추출 및 데이터 변환</span><span class="sxs-lookup"><span data-stu-id="b320d-281">Extract Features and transform the data</span></span>

<span data-ttu-id="b320d-282">데이터 전처리 및 정리는 데이터 세트가 기계 학습에 효과적으로 사용되기 전에 수행되는 중요한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-282">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span>  <span data-ttu-id="b320d-283">이러한 모델링 작업 없이 데이터를 사용하면 잘못된 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-283">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="b320d-284">기계 학습 알고리즘은 [기능화된](../resources/glossary.md#feature) 데이터를 인식하며, 심층 신경망을 처리할 때 네트워크에 필요한 형식에 맞게 이미지를 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-284">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, and when dealing with deep neural networks you must adapt the images to the format expected by the network.</span></span> <span data-ttu-id="b320d-285">해당 형식은 [숫자 벡터](../resources/glossary.md#numerical-feature-vector)입니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-285">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="b320d-286">학습 및 평가 후에 **레이블** 열 값을 사용하여 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-286">After training and evaluation, predict with the **Label** column values.</span></span> <span data-ttu-id="b320d-287">미리 학습된 모델을 사용하므로 [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) 메서드를 사용하여 새 모델에 필드를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-287">As you're using a pre-trained model, map fields to the new model with the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method.</span></span> <span data-ttu-id="b320d-288">이 메서드는 `Label`을 숫자 키 형식(`LabelTokey`) 열로 변환하고 새 데이터 세트 열로 추가합니다.  강사를 추가할 때 이 열의 이름을 `estimator`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-288">This method transforms the `Label` into a numeric key type (`LabelTokey`) column and add it as new dataset column:  Name this `estimator` as you'll also add the trainer to it.</span></span> <span data-ttu-id="b320d-289">다음 코드 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-289">Add the next line of code:</span></span>

[!code-csharp[MapValueToKey1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey1)]

<span data-ttu-id="b320d-290">이미지 처리 평가자는 기능 추출에 미리 학습된 [DNN(심층 신경망)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) featurizer를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-290">Your image processing estimator uses pre-trained [Deep Neural Network(DNN)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) featurizers for feature extraction.</span></span> <span data-ttu-id="b320d-291">심층 신경망을 처리할 때 필요한 네트워크 형식에 맞게 이미지를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-291">When dealing with deep neural networks, you  adapt the images to the expected network format.</span></span> <span data-ttu-id="b320d-292">이런 이유로 여러 가지 이미지 변환을 사용하여 모델에 필요한 형식으로 이미지 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-292">This is the reason you use several image transforms to get the image data into the model's expected form:</span></span>

1. <span data-ttu-id="b320d-293">`LoadImages` 변환 이미지는 비트맵 형식으로 메모리에 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-293">The `LoadImages`transform images are loaded in memory as a Bitmap type.</span></span>
2. <span data-ttu-id="b320d-294">미리 학습된 모델에 정의된 입력 이미지 너비 및 높이가 포함되므로 `ResizeImages` 변환은 이미지 크기를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-294">The `ResizeImages` transform resizes the images as the pre-trained model has a defined input image width and height.</span></span>
3. <span data-ttu-id="b320d-295">`ExtractPixels` 변환은 입력 이미지에서 픽셀을 추출하고 숫자 벡터로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-295">The `ExtractPixels` transform extracts the pixels from the input images and converts them into a numeric vector.</span></span>

<span data-ttu-id="b320d-296">이 이미지 변환을 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-296">Add these image transforms as the next lines of code:</span></span>

[!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

<span data-ttu-id="b320d-297">`LoadTensorFlowModel`은 `TensorFlow` 모델이 한 번 로드되도록 허용한 다음, `ScoreTensorFlowModel`을 사용하여 `TensorFlowEstimator`를 만드는 간편 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-297">The `LoadTensorFlowModel` is a convenience method that allows the `TensorFlow` model to be loaded once and then creates the `TensorFlowEstimator` using `ScoreTensorFlowModel`.</span></span> <span data-ttu-id="b320d-298">`ScoreTensorFlowModel`은 지정된 출력(`Inception model`의 이미지 기능 `softmax2_pre_activation`)을 추출하고 미리 학습된 `TensorFlow` 모델을 사용하여 데이터 세트의 점수를 매깁니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-298">The `ScoreTensorFlowModel` extracts specified outputs (the `Inception model`'s image features `softmax2_pre_activation`), and scores a dataset using the pre-trained `TensorFlow` model.</span></span>

<span data-ttu-id="b320d-299">`softmax2_pre_activation`은 이미지가 속한 클래스를 판별하여 모델을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-299">`softmax2_pre_activation` assists the model with determining which class the images belongs to.</span></span> <span data-ttu-id="b320d-300">`softmax2_pre_activation`은 각 이미지 범주의 확률을 반환하고, 모든 해당 확률의 합계는 1이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-300">`softmax2_pre_activation` returns a probability for each of the categories for an image, and all of those probabilities must add up to 1.</span></span> <span data-ttu-id="b320d-301">다음 예제와 같이 이미지가 하나의 범주에만 속한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-301">It assumes that an image will belong to only one category, as shown in the following example:</span></span>

| <span data-ttu-id="b320d-302">클래스</span><span class="sxs-lookup"><span data-stu-id="b320d-302">Class</span></span>         | <span data-ttu-id="b320d-303">확률</span><span class="sxs-lookup"><span data-stu-id="b320d-303">Probability</span></span>   |
| ------------- | ------------- |
| `Food`        |  <span data-ttu-id="b320d-304">0.001</span><span class="sxs-lookup"><span data-stu-id="b320d-304">0.001</span></span>        |
| `Toy`         |  <span data-ttu-id="b320d-305">0.95</span><span class="sxs-lookup"><span data-stu-id="b320d-305">0.95</span></span>         |
| `Appliance`   |  <span data-ttu-id="b320d-306">0.06</span><span class="sxs-lookup"><span data-stu-id="b320d-306">0.06</span></span>         |

<span data-ttu-id="b320d-307">다음 코드 줄을 사용하여 `TensorFlowTransform`을 `estimator`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-307">Append the `TensorFlowTransform` to the `estimator` with the following line of code:</span></span>

[!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

### <a name="choose-a-training-algorithm"></a><span data-ttu-id="b320d-308">학습 알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="b320d-308">Choose a training algorithm</span></span>

<span data-ttu-id="b320d-309">학습 알고리즘을 추가하려면 `mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()` 래퍼 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-309">To add the training algorithm, call the `mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()` wrapper method.</span></span>  <span data-ttu-id="b320d-310">[LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer)는 `estimator`에 추가되고 Inception 이미지 기능(`softmax2_pre_activation`) 및 `Label` 입력 매개 변수를 수락하여 기록 데이터를 기반으로 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-310">The [LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer) is appended to the `estimator` and accepts the Inception image features (`softmax2_pre_activation`) and the `Label` input parameters to learn from the historic data.</span></span>  <span data-ttu-id="b320d-311">다음 코드를 사용하여 강사를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-311">Add the trainer with the following code:</span></span>

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

<span data-ttu-id="b320d-312">또한 `predictedlabel`을 `predictedlabelvalue`에 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-312">You also need to map the `predictedlabel` to the `predictedlabelvalue`:</span></span>

[!code-csharp[MapValueToKey2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey2)]

<span data-ttu-id="b320d-313">`Fit()` 메서드는 데이터 세트를 변환하고 학습을 적용하여 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-313">The `Fit()` method trains your model by transforming the dataset and applying the training.</span></span> <span data-ttu-id="b320d-314">모델을 학습 데이터 세트에 맞추고 `ReuseAndTuneInceptionModel()` 메서드에서 다음 줄로 다음 항목을 추가하여 학습된 모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-314">Fit the model to the training dataset and return the trained model by adding the following as the next line of code in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

<span data-ttu-id="b320d-315">[Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 메서드는 테스트 데이터 세트의 여러 입력 행을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-315">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for multiple provided input rows of a test dataset.</span></span>  <span data-ttu-id="b320d-316">`ReuseAndTuneInceptionModel()`에 다음 코드를 추가하여 `Training`데이터를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-316">Transform the `Training` data by adding the following code to `ReuseAndTuneInceptionModel()`:</span></span>

[!code-csharp[TransformData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TransformData)]

<span data-ttu-id="b320d-317">보다 쉽게 표시할 수 있도록 이미지 데이터와 예측 `DataViews`를 강력한 형식의 `IEnumerables`로 변환하여 쌍으로 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-317">Convert your image data and prediction `DataViews` into strongly-typed `IEnumerables` to pair for easier display.</span></span> <span data-ttu-id="b320d-318">다음 코드를 사용하여 `MLContext.CreateEnumerable()` 메서드를 통해 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-318">Use the `MLContext.CreateEnumerable()` method to do that, using the following code:</span></span>

[!code-csharp[EnumerateDataViews](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#EnumerateDataViews)]

<span data-ttu-id="b320d-319">다음 코드를 추가하여 데이터 및 예측을 `ReuseAndTuneInceptionModel()` 메서드의 다음 줄과 같이 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-319">Add the following code to display your data and predictions as the next lines in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[CallDisplayResults1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults1)]

<span data-ttu-id="b320d-320">예측 세트가 있으면 [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) 메서드가 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-320">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method:</span></span>

* <span data-ttu-id="b320d-321">모델을 평가합니다(예측 값을 실제 데이터 세트 `Labels`와 비교).</span><span class="sxs-lookup"><span data-stu-id="b320d-321">Assesses the model (compares the predicted values with the actual dataset `Labels`).</span></span>

* <span data-ttu-id="b320d-322">모델 성능 메트릭을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-322">Returns the model performance metrics.</span></span>

<span data-ttu-id="b320d-323">`ReuseAndTuneInceptionModel()` 메서드에 아래 코드를 다음 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-323">Add the following code to the `ReuseAndTuneInceptionModel()` method as the next line:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

<span data-ttu-id="b320d-324">이미지 분류를 위해 다음 메트릭이 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-324">The following metrics are evaluated for image classification:</span></span>

* <span data-ttu-id="b320d-325">`Log-loss` - [로그 손실](../resources/glossary.md#log-loss)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b320d-325">`Log-loss` - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="b320d-326">로그 손실을 가능한 한 0에 가깝게 합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-326">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="b320d-327">`Per class Log-loss`.</span><span class="sxs-lookup"><span data-stu-id="b320d-327">`Per class Log-loss`.</span></span> <span data-ttu-id="b320d-328">클래스별 로그 손실을 가능한 한 0에 가깝게 합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-328">You want per class Log-loss to be as close to zero as possible.</span></span>

<span data-ttu-id="b320d-329">다음 코드를 사용하여 메트릭을 표시하고, 결과를 공유한 다음, 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-329">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

 <span data-ttu-id="b320d-330">다음 코드를 추가하여 학습된 모델을 다음 줄로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-330">Add the following code to return the trained model as the next line:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReturnModel)]

## <a name="classify-images-with-a-loaded-model"></a><span data-ttu-id="b320d-331">로드된 모델을 통해 이미지 분류</span><span class="sxs-lookup"><span data-stu-id="b320d-331">Classify images with a loaded model</span></span>

<span data-ttu-id="b320d-332">`ClassifyImages()` 메서드에 아래 호출을 `Main` 메서드의 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-332">Add the following call to the `ClassifyImages()` method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallClassifyImages](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifyImages)]

<span data-ttu-id="b320d-333">`ClassifyImages()` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-333">The `ClassifyImages()` method executes the following tasks:</span></span>

* <span data-ttu-id="b320d-334">.TSV 파일을 `IEnumerable`로 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-334">Reads .TSV file into `IEnumerable`.</span></span>
* <span data-ttu-id="b320d-335">테스트 데이터를 기반으로 이미지 분류를 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-335">Predicts image classifications based on test data.</span></span>

<span data-ttu-id="b320d-336">다음 코드를 사용하여 `ReuseAndTuneInceptionModel()` 메서드 바로 뒤 및 `PairAndDisplayResults()` 메서드 바로 앞에 `ClassifyImages()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-336">Create the `ClassifyImages()` method, just after the `ReuseAndTuneInceptionModel()` method and just before the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static void ClassifyImages(MLContext mlContext, string dataLocation, string imagesFolder, string outputModelLocation, ITransformer model)
{

}
```

<span data-ttu-id="b320d-337">먼저 `ReadFromTsv()` 메서드를 호출하여 각 `ImagePath`의 정규화된 경로를 포함하는 `IEnumerable<ImageData>` 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-337">First, call the `ReadFromTsv()` method to create an `IEnumerable<ImageData>` class that contains the fully qualified path for each `ImagePath`.</span></span> <span data-ttu-id="b320d-338">데이터와 예측 결과를 쌍으로 연결하려면 파일 경로가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-338">You need that file path to pair your data and prediction results.</span></span> <span data-ttu-id="b320d-339">또한 예측하는 데 사용할 `IDataView`로 `IEnumerable<ImageData>` 클래스를 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-339">You also need to convert the `IEnumerable<ImageData>` class to an `IDataView` that you will use to predict.</span></span> <span data-ttu-id="b320d-340">`ClassifyImages()` 메서드의 다음 두 줄로 아래 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-340">Add the following code as the next two lines in the `ClassifyImages()` method:</span></span>

[!code-csharp[CallReadFromTSV](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReadFromTSV)]

<span data-ttu-id="b320d-341">이전에 학습 이미지 데이터를 예측한 것처럼 전달된 모델의 [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 메서드를 사용하여 테스트 이미지 데이터의 범주를 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-341">As you did previously with the training image data, predict the category of the test image data using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method of the model passed in.</span></span> <span data-ttu-id="b320d-342">예측을 위해 다음 코드를 `ClassifyImages()` 메서드에 추가하고, 쌍 연결 및 표시를 위해 `predictions` `IDataView`를 `IEnumerable`로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-342">Add the following code to the `ClassifyImages()` method for the predictions and to convert the `predictions` `IDataView` into an `IEnumerable` for pairing and display:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Predict)]

<span data-ttu-id="b320d-343">테스트 이미지 데이터 및 예측을 쌍으로 연결하고 표시하려면 다음 코드를 추가하여 `DisplayResults()` 메서드의 다음 줄로 이전에 만들어진 `ClassifyImages()` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-343">To pair and display your test image data and predictions, add the following code to call the `DisplayResults()` method previously created as the next line in the `ClassifyImages()` method:</span></span>

[!code-csharp[CallDisplayResults2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults2)]

## <a name="classify-a-single-image-with-a-loaded-model"></a><span data-ttu-id="b320d-344">로드된 모델을 통해 단일 이미지 분류</span><span class="sxs-lookup"><span data-stu-id="b320d-344">Classify a single image with a loaded model</span></span>

<span data-ttu-id="b320d-345">`ClassifySingleImage()` 메서드에 아래 호출을 `Main` 메서드의 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-345">Add the following call to the `ClassifySingleImage()` method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

<span data-ttu-id="b320d-346">`ClassifySingleImage()` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-346">The `ClassifySingleImage()` method executes the following tasks:</span></span>

* <span data-ttu-id="b320d-347">`ImageData` 인스턴스를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-347">Loads an `ImageData` instance.</span></span>
* <span data-ttu-id="b320d-348">테스트 데이터를 기반으로 이미지 분류를 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-348">Predicts image classification based on test data.</span></span>

<span data-ttu-id="b320d-349">다음 코드를 사용하여 `ClassifyImages()` 메서드 바로 뒤 및 `PairAndDisplayResults()` 메서드 바로 앞에 `ClassifySingleImage()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-349">Create the `ClassifySingleImage()` method, just after the `ClassifyImages()` method and just before the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static void ClassifySingleImage(MLContext mlContext, string imagePath, string outputModelLocation, ITransformer model)
{

}
```

<span data-ttu-id="b320d-350">먼저 단일 `ImagePath`의 정규화된 경로 및 이미지 파일 이름을 포함하는 `ImageData` 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-350">First, create an `ImageData` class that contains the fully qualified path and image file name for the single `ImagePath`.</span></span> <span data-ttu-id="b320d-351">`ClassifySingleImage()` 메서드의 다음 줄로 아래 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-351">Add the following code as the next  lines in the `ClassifySingleImage()` method:</span></span>

[!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

<span data-ttu-id="b320d-352">[PredictionEngine 클래스](xref:Microsoft.ML.PredictionEngine%602)는 단일 데이터 인스턴스에 대한 예측을 수행하는 편리한 API입니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-352">The [PredictionEngine class](xref:Microsoft.ML.PredictionEngine%602) is a convenience API that performs a prediction on a single instance of data.</span></span> <span data-ttu-id="b320d-353">[Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) 함수는 단일 데이터 열의 대한 예측을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-353">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single column of data.</span></span> <span data-ttu-id="b320d-354">`ClassifySingleImage()`에 다음 코드를 추가하여 이미지 범주를 예측하는 `PredictionEngine`에 `imageData`를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-354">Pass `imageData` to the `PredictionEngine` to predict the image category by adding the following code to `ClassifySingleImage()`:</span></span>

[!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

<span data-ttu-id="b320d-355">예측 결과를 `ClassifySingleImage()` 메서드의 다음 코드 줄로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-355">Display the prediction result as the next line of code in the `ClassifySingleImage()` method:</span></span>

[!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="results"></a><span data-ttu-id="b320d-356">결과</span><span class="sxs-lookup"><span data-stu-id="b320d-356">Results</span></span>

<span data-ttu-id="b320d-357">이전 단계를 수행한 후 콘솔 앱을 실행합니다(Ctrl+F5).</span><span class="sxs-lookup"><span data-stu-id="b320d-357">After following the previous steps, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="b320d-358">다음 출력과 같은 결과가 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-358">Your results should be similar to the following output.</span></span>  <span data-ttu-id="b320d-359">경고 또는 처리 메시지가 표시될 수 있지만, 이해하기 쉽도록 이러한 메시지는 다음 결과에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-359">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

```console
=============== Training classification model ===============
Image: broccoli.jpg predicted as: food with score: 0.976743
Image: pizza.jpg predicted as: food with score: 0.9751652
Image: pizza2.jpg predicted as: food with score: 0.9660203
Image: teddy2.jpg predicted as: toy with score: 0.9748783
Image: teddy3.jpg predicted as: toy with score: 0.9829691
Image: teddy4.jpg predicted as: toy with score: 0.9868168
Image: toaster.jpg predicted as: appliance with score: 0.9769174
Image: toaster2.png predicted as: appliance with score: 0.9800823
=============== Classification metrics ===============
LogLoss is: 0.0228266745633507
PerClassLogLoss is: 0.0277501705149937 , 0.0186303530571291 , 0.0217359128952187
=============== Making classifications ===============
Image: broccoli.png predicted as: food with score: 0.905548
Image: pizza3.jpg predicted as: food with score: 0.9709008
Image: teddy6.jpg predicted as: toy with score: 0.9750155
=============== Making single image classification ===============
Image: toaster3.jpg predicted as: appliance with score: 0.9625379

C:\Program Files\dotnet\dotnet.exe (process 4304) exited with code 0.
Press any key to close this window . . .
```

<span data-ttu-id="b320d-360">지금까지</span><span class="sxs-lookup"><span data-stu-id="b320d-360">Congratulations!</span></span> <span data-ttu-id="b320d-361">이제 ML.NET에서 미리 학습된 `TensorFlow` 모델을 다시 사용하여 이미지 분류를 위한 기계 학습 모델을 성공적으로 빌드했습니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-361">You've now successfully built a machine learning model for image classification by reusing a pre-trained `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="b320d-362">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-362">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span>

<span data-ttu-id="b320d-363">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="b320d-363">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="b320d-364">문제 이해</span><span class="sxs-lookup"><span data-stu-id="b320d-364">Understand the problem</span></span>
> * <span data-ttu-id="b320d-365">미리 학습된 모델 다시 사용 및 조정</span><span class="sxs-lookup"><span data-stu-id="b320d-365">Reuse and tune the pre-trained model</span></span>
> * <span data-ttu-id="b320d-366">로드된 모델을 통해 이미지 분류</span><span class="sxs-lookup"><span data-stu-id="b320d-366">Classify images with a loaded model</span></span>

<span data-ttu-id="b320d-367">기계 학습 샘플 GitHub 리포지토리를 확인하여 확장된 이미지 분류 샘플을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="b320d-367">Check out the Machine Learning samples GitHub repository to explore an expanded image classification sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="b320d-368">dotnet/machinelearning-samples GitHub 리포지토리</span><span class="sxs-lookup"><span data-stu-id="b320d-368">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/)
