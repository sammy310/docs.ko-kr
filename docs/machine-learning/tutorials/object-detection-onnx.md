---
title: '자습서: ONNX 및 ML.NET를 통한 딥 러닝을 사용하여 개체 검색'
description: 이 자습서에서는 ML.NET에서 미리 학습된 ONNX 딥 러닝 학습 모델을 사용하여 이미지에서 개체를 검색하는 방법을 보여줍니다.
author: luisquintanilla
ms.author: luquinta
ms.date: 08/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: f31c5155dd3ca59b1a370599b3ffabb2648791b1
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318525"
---
# <a name="tutorial-detect-objects-using-onnx-in-mlnet"></a><span data-ttu-id="7720e-103">자습서: ML.NET에서 ONNX를 사용하여 개체 검색</span><span class="sxs-lookup"><span data-stu-id="7720e-103">Tutorial: Detect objects using ONNX in ML.NET</span></span>

<span data-ttu-id="7720e-104">ML.NET에서 미리 학습된 ONNX 모델을 사용하여 이미지에서 개체를 검색하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-104">Learn how to use a pre-trained ONNX model in ML.NET to detect objects in images.</span></span>

<span data-ttu-id="7720e-105">개체 검색 모델을 처음부터 학습시키려면 수백만 개의 매개 변수, 다량의 레이블 지정 학습 데이터 및 많은 양의 컴퓨팅 리소스(수백 시간의 GPU 시간)를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-105">Training an object detection model from scratch requires setting millions of parameters, a large amount of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="7720e-106">미리 학습된 모델을 사용하면 학습 프로세스를 바로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-106">Using a pre-trained model allows you to shortcut the training process.</span></span>

<span data-ttu-id="7720e-107">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="7720e-108">문제 이해</span><span class="sxs-lookup"><span data-stu-id="7720e-108">Understand the problem</span></span>
> - <span data-ttu-id="7720e-109">ONNX의 개념과 ML.NET에서 작동하는 방식에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="7720e-109">Learn what ONNX is and how it works with ML.NET</span></span>
> - <span data-ttu-id="7720e-110">모델 이해</span><span class="sxs-lookup"><span data-stu-id="7720e-110">Understand the model</span></span>
> - <span data-ttu-id="7720e-111">미리 학습된 모델 다시 사용</span><span class="sxs-lookup"><span data-stu-id="7720e-111">Reuse the pre-trained model</span></span>
> - <span data-ttu-id="7720e-112">로드된 모델을 사용하여 개체 검색</span><span class="sxs-lookup"><span data-stu-id="7720e-112">Detect objects with a loaded model</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="7720e-113">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="7720e-113">Pre-requisites</span></span>

- <span data-ttu-id="7720e-114">“.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017).</span><span class="sxs-lookup"><span data-stu-id="7720e-114">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- [<span data-ttu-id="7720e-115">Microsoft.ML NuGet 패키지</span><span class="sxs-lookup"><span data-stu-id="7720e-115">Microsoft.ML NuGet Package</span></span>](https://www.nuget.org/packages/Microsoft.ML/)
- [<span data-ttu-id="7720e-116">Microsoft.ML.ImageAnalytics NuGet 패키지</span><span class="sxs-lookup"><span data-stu-id="7720e-116">Microsoft.ML.ImageAnalytics NuGet Package</span></span>](https://www.nuget.org/packages/Microsoft.ML.ImageAnalytics/)
- [<span data-ttu-id="7720e-117">Microsoft.ML.OnnxTransformer NuGet 패키지</span><span class="sxs-lookup"><span data-stu-id="7720e-117">Microsoft.ML.OnnxTransformer NuGet Package</span></span>](https://www.nuget.org/packages/Microsoft.ML.OnnxTransformer/)
- [<span data-ttu-id="7720e-118">Tiny YOLOv2 미리 학습된 모델</span><span class="sxs-lookup"><span data-stu-id="7720e-118">Tiny YOLOv2 pre-trained model</span></span>](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny_yolov2)
- <span data-ttu-id="7720e-119">[Netron](https://github.com/lutzroeder/netron)(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="7720e-119">[Netron](https://github.com/lutzroeder/netron) (optional)</span></span>

## <a name="onnx-object-detection-sample-overview"></a><span data-ttu-id="7720e-120">ONNX 개체 검색 샘플 개요</span><span class="sxs-lookup"><span data-stu-id="7720e-120">ONNX object detection sample overview</span></span>

<span data-ttu-id="7720e-121">이 샘플에서는 미리 학습된 딥 러닝 ONNX 모델을 사용하여 이미지 내에서 개체를 검색하는 .NET core 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-121">This sample creates a .NET core console application that detects objects within an image using a pre-trained deep learning ONNX model.</span></span> <span data-ttu-id="7720e-122">이 샘플의 코드는 GitHub의 [dotnet/machinelearning-samples repository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-122">The code for this sample can be found on the [dotnet/machinelearning-samples repository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx) on GitHub.</span></span>

## <a name="what-is-object-detection"></a><span data-ttu-id="7720e-123">개체 검색의 개념</span><span class="sxs-lookup"><span data-stu-id="7720e-123">What is object detection?</span></span>

<span data-ttu-id="7720e-124">개체 검색은 컴퓨터 비전 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-124">Object detection is a computer vision problem.</span></span> <span data-ttu-id="7720e-125">개체 검색은 이미지 분류와 밀접하게 관련된 반면, 보다 세부적인 규모에서 이미지 분류를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-125">While closely related to image classification, object detection performs image classification at a more granular scale.</span></span> <span data-ttu-id="7720e-126">개체 검색에서는 이미지에서 엔터티 찾기 _및_ 분류를 둘 다 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-126">Object detection both locates _and_ categorizes entities within images.</span></span> <span data-ttu-id="7720e-127">이미지에 서로 다른 유형의 개체가 여러 개 포함되어 있는 경우 개체 검색을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-127">Use object detection when images contain multiple objects of different types.</span></span>

![왼쪽에는 한 강아지의 이미지 분류를 표시하고, 오른쪽에는 한 강아지의 그룹 개체 분류를 보여 주는 병렬 이미지](./media/object-detection-onnx/img-classification-obj-detection.PNG)

<span data-ttu-id="7720e-129">개체 검색의 몇 가지 사용 사례는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-129">Some use cases for object detection include:</span></span>

- <span data-ttu-id="7720e-130">자동 주행 자동차</span><span class="sxs-lookup"><span data-stu-id="7720e-130">Self-Driving Cars</span></span>
- <span data-ttu-id="7720e-131">Robotics</span><span class="sxs-lookup"><span data-stu-id="7720e-131">Robotics</span></span>
- <span data-ttu-id="7720e-132">얼굴 감지</span><span class="sxs-lookup"><span data-stu-id="7720e-132">Face Detection</span></span>
- <span data-ttu-id="7720e-133">작업 영역 안전성</span><span class="sxs-lookup"><span data-stu-id="7720e-133">Workplace Safety</span></span>
- <span data-ttu-id="7720e-134">개체 수 계산</span><span class="sxs-lookup"><span data-stu-id="7720e-134">Object Counting</span></span>
- <span data-ttu-id="7720e-135">활동 인식</span><span class="sxs-lookup"><span data-stu-id="7720e-135">Activity Recognition</span></span>

## <a name="select-a-deep-learning-model"></a><span data-ttu-id="7720e-136">딥 러닝 모델 선택</span><span class="sxs-lookup"><span data-stu-id="7720e-136">Select a deep learning model</span></span>

<span data-ttu-id="7720e-137">딥 러닝은 기계 학습의 하위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-137">Deep learning is a subset of machine learning.</span></span> <span data-ttu-id="7720e-138">딥 러닝 모델을 학습시키려면 많은 양의 데이터가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-138">To train deep learning models, large quantities of data are required.</span></span> <span data-ttu-id="7720e-139">데이터의 패턴은 일련의 계층으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-139">Patterns in the data are represented by a series of layers.</span></span> <span data-ttu-id="7720e-140">데이터의 관계는 가중치를 포함하는 계층 간의 연결로 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-140">The relationships in the data are encoded as connections between the layers containing weights.</span></span> <span data-ttu-id="7720e-141">가중치가 높을수록 관계가 강해집니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-141">The higher the weight, the stronger the relationship.</span></span> <span data-ttu-id="7720e-142">이러한 일련의 계층 및 연결을 통칭하여 인공신경망이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-142">Collectively, this series of layers and connections are known as artificial neural networks.</span></span> <span data-ttu-id="7720e-143">네트워크에 있는 계층이 많을수록 “심층 강화”되어, 심층 신경망으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-143">The more layers in a network, the "deeper" it is, making it a deep neural network.</span></span>

<span data-ttu-id="7720e-144">신경망의 유형은 여러 가지가 있습니다. 가장 일반적으로 MLP(Multi-Layered Perceptron), CNN(Convolutional Neural Network) 및 RNN(Recurrent Neural Network)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-144">There are different types of neural networks, the most common being Multi-Layered Perceptron (MLP), Convolutional Neural Network (CNN) and Recurrent Neural Network (RNN).</span></span> <span data-ttu-id="7720e-145">가장 기본적인 유형은 일련의 입력을 출력 집합에 매핑하는 MLP입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-145">The most basic is the MLP, which maps a set of inputs to a set of outputs.</span></span> <span data-ttu-id="7720e-146">이 신경망은 데이터에 공간 또는 시간 구성 요소가 없는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-146">This neural network is good when the data does not have a spatial or time component.</span></span> <span data-ttu-id="7720e-147">CNN은 나선형 계층을 사용하여 데이터에 포함된 공간 정보를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-147">The CNN makes use of convolutional layers to process spatial information contained in the data.</span></span> <span data-ttu-id="7720e-148">CNN의 좋은 사용 사례는 이미지의 영역에 기능이 있는지 검색하는 이미지 처리입니다(예: 이미지의 중심에 코가 있나요?).</span><span class="sxs-lookup"><span data-stu-id="7720e-148">A good use case for CNNs is image processing to detect the presence of a feature in a region of an image (for example, is there a nose in the center of an image?).</span></span> <span data-ttu-id="7720e-149">마지막으로 RNN은 상태 또는 메모리의 지속성을 입력으로 사용할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-149">Finally, RNNs allow for the persistence of state or memory to be used as input.</span></span> <span data-ttu-id="7720e-150">RNN은 순차 순서와 이벤트 컨텍스트가 중요한 시계열 분석에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-150">RNNs are used for time-series analysis, where the sequential ordering and context of events is important.</span></span>

### <a name="understand-the-model"></a><span data-ttu-id="7720e-151">모델 이해</span><span class="sxs-lookup"><span data-stu-id="7720e-151">Understand the model</span></span>

<span data-ttu-id="7720e-152">개체 검색은 이미지 처리 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-152">Object detection is an image processing task.</span></span> <span data-ttu-id="7720e-153">따라서 이 문제를 해결하도록 학습된 대부분의 딥 러닝 모델은 CNN입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-153">Therefore, most deep learning models trained to solve this problem are CNNs.</span></span> <span data-ttu-id="7720e-154">이 자습서에서 사용되는 모델은 백서에 설명된 YOLOv2 모델의 축소 버전인 Tiny YOLOv2 모델입니다. [“YOLO9000: Better, Faster, Stronger” by Redmon and Fadhari](https://arxiv.org/pdf/1612.08242.pdf).</span><span class="sxs-lookup"><span data-stu-id="7720e-154">The model used in this tutorial is the Tiny YOLOv2 model, a more compact version of the YOLOv2 model described in the paper: ["YOLO9000: Better, Faster, Stronger" by Redmon and Fadhari](https://arxiv.org/pdf/1612.08242.pdf).</span></span> <span data-ttu-id="7720e-155">Tiny YOLOv2는 Pascal VOC 데이터 세트에서 학습되며 20개의 서로 다른 개체 클래스를 예측할 수 있는 15개의 계층으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-155">Tiny YOLOv2 is trained on the Pascal VOC dataset and is made up of 15 layers that can predict 20 different classes of objects.</span></span> <span data-ttu-id="7720e-156">Tiny YOLOv2는 소스 YOLOv2 모델의 축소된 버전이며, 속도와 정확도가 서로 절충됩니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-156">Because Tiny YOLOv2 is a condensed version of the original YOLOv2 model, a tradeoff is made between speed and accuracy.</span></span> <span data-ttu-id="7720e-157">Netron과 같은 도구를 사용하여 모델을 구성하는 다양한 계층을 시각화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-157">The different layers that make up the model can be visualized using tools like Netron.</span></span> <span data-ttu-id="7720e-158">모델을 검사하면 신경망을 구성하는 모든 계층 간에 연결 매핑이 일시 중단됩니다. 여기서 각 계층에는 각 입력/출력의 차원과 함께 계층 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-158">Inspecting the model would yield a mapping of the connections between all the layers that make up the neural network, where each layer would contain the name of the layer along with the dimensions of the respective input / output.</span></span> <span data-ttu-id="7720e-159">모델의 입력 및 출력을 설명하는 데 사용하는 데이터 구조를 텐서(tensor)라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-159">The data structures used to describe the inputs and outputs of the model are known as tensors.</span></span> <span data-ttu-id="7720e-160">텐서는 N 차원에 데이터를 저장하는 컨테이너로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-160">Tensors can be thought of as containers that store data in N-dimensions.</span></span> <span data-ttu-id="7720e-161">Tiny YOLOv2의 경우 입력 계층의 이름은 `image`이고 `3 x 416 x 416` 차원의 텐서가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-161">In the case of Tiny YOLOv2, the name of the input layer is `image` and it expects a tensor of dimensions `3 x 416 x 416`.</span></span> <span data-ttu-id="7720e-162">출력 계층의 이름은 `grid`이고 `125 x 13 x 13` 차원의 출력 텐서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-162">The name of the output layer is `grid` and generates an output tensor of dimensions `125 x 13 x 13`.</span></span>

![숨겨진 레이어로 분할되는 입력 계층을 표시한 후 출력 계층 표시](./media/object-detection-onnx/netron-model-map.png)

<span data-ttu-id="7720e-164">YOLO 모델에서는 `3(RGB) x 416px x 416px` 이미지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-164">The YOLO model takes an image `3(RGB) x 416px x 416px`.</span></span> <span data-ttu-id="7720e-165">이 모델에서는 출력을 생성하기 위해 이 입력을 받아 다양한 계층에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-165">The model takes this input and passes it through the different layers to produce an output.</span></span> <span data-ttu-id="7720e-166">출력은 입력 이미지를 `13 x 13` 그리드로 나누며, 그리드의 각 셀은 `125` 값으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-166">The output divides the input image into a `13 x 13` grid, with each cell in the grid consisting of `125` values.</span></span>

### <a name="what-is-an-onnx-model"></a><span data-ttu-id="7720e-167">ONNX 모델의 개념</span><span class="sxs-lookup"><span data-stu-id="7720e-167">What is an ONNX model?</span></span>

<span data-ttu-id="7720e-168">ONNX(Open Neural Network Exchange)는 AI 모델의 오픈 소스 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-168">The Open Neural Network Exchange (ONNX) is an open source format for AI models.</span></span> <span data-ttu-id="7720e-169">ONNX에서는 프레임워크 간의 상호 운용성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-169">ONNX supports interoperability between frameworks.</span></span> <span data-ttu-id="7720e-170">즉, PyTorch와 같이 널리 사용되는 여러 기계 학습 프레임워크 중 하나에서 모델을 학습시키고, ONNX 형식으로 변환하며, ML.NET과 같은 다른 프레임워크에서 ONNX 모델을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-170">This means you can train a model in one of the many popular machine learning frameworks like PyTorch, convert it into ONNX format and consume the ONNX model in a different framework like ML.NET.</span></span> <span data-ttu-id="7720e-171">자세히 알아보려면 [ONNX 웹 사이트](https://onnx.ai/)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="7720e-171">To learn more, visit the [ONNX website](https://onnx.ai/).</span></span>

![ONNX 지원 형식을 ONNX로 가져온 다음, 다른 ONNX 지원 형식에서 사용](./media/object-detection-onnx/onnx-frameworks.png)

<span data-ttu-id="7720e-173">미리 학습된 Tiny YOLOv2 모델은 계층과 해당 계층의 학습된 패턴을 직렬화하여 표시하는 ONNX 형식으로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-173">The pre-trained Tiny YOLOv2 model is stored in ONNX format, a serialized representation of the layers and learned patterns of those layers.</span></span> <span data-ttu-id="7720e-174">ML.NET에서 ONNX와의 상호 운용성은 [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) 및 [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) NuGet 패키지를 통해 달성합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-174">In ML.NET, interoperability with ONNX is achieved with the [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) and [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) NuGet packages.</span></span> <span data-ttu-id="7720e-175">[`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) 패키지에는 이미지를 받아 예측이나 학습 파이프라인의 입력으로 사용할 수 있는 숫자 값으로 인코딩하는 일련의 변환이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-175">The [`ImageAnalytics`](xref:Microsoft.ML.Transforms.Image) package contains a series of transforms that take an image and encode it into numerical values that can be used as input into a prediction or training pipeline.</span></span> <span data-ttu-id="7720e-176">[`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) 패키지에서는 ONNX Runtime을 사용하여 ONNX 모델을 로드하고 제공된 입력을 기반으로 예측하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-176">The [`OnnxTransformer`](xref:Microsoft.ML.Transforms.Onnx.OnnxTransformer) package leverages the ONNX Runtime to load an ONNX model and use it to make predictions based on input provided.</span></span>

![ONNX 파일에서 ONNX 런타임으로, 마지막으로 C# 애플리케이션으로의 데이터 흐름 표시](./media/object-detection-onnx/onnx-ml-net-integration.png)

## <a name="set-up-the-net-core-project"></a><span data-ttu-id="7720e-178">.NET Core 프로젝트 설정</span><span class="sxs-lookup"><span data-stu-id="7720e-178">Set up the .NET Core project</span></span>

<span data-ttu-id="7720e-179">이제 ONNX의 개념과 Tiny YOLOv2의 작동 원리를 대략적으로 파악했으므로 이제 애플리케이션을 빌드하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-179">Now that you have a general understanding of what ONNX is and how Tiny YOLOv2 works, it's time to build the application.</span></span>

### <a name="create-a-console-application"></a><span data-ttu-id="7720e-180">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="7720e-180">Create a console application</span></span>

1. <span data-ttu-id="7720e-181">“ObjectDetection”이라는 **.NET Core 콘솔 애플리케이션**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-181">Create a **.NET Core Console Application** called "ObjectDetection".</span></span>

1. <span data-ttu-id="7720e-182">**Microsoft.ML NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-182">Install the **Microsoft.ML NuGet Package**:</span></span>

    - <span data-ttu-id="7720e-183">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-183">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    - <span data-ttu-id="7720e-184">패키지 소스로 “nuget.org”를 선택하고, [찾아보기] 탭을 선택하고, **Microsoft.ML**을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-184">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span>
    - <span data-ttu-id="7720e-185">**설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-185">Select the **Install** button.</span></span>
    - <span data-ttu-id="7720e-186">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-186">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>
    - <span data-ttu-id="7720e-187">**Microsoft.ML.ImageAnalytics** 및 **Microsoft.ML.OnnxTransformer**에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-187">Repeat these steps for **Microsoft.ML.ImageAnalytics** and **Microsoft.ML.OnnxTransformer**.</span></span>

### <a name="prepare-your-data-and-pre-trained-model"></a><span data-ttu-id="7720e-188">데이터 및 미리 학습된 모델 준비</span><span class="sxs-lookup"><span data-stu-id="7720e-188">Prepare your data and pre-trained model</span></span>

1. <span data-ttu-id="7720e-189">[프로젝트 자산 디렉터리 zip 파일](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/assets.zip)을 다운로드하고 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-189">Download [The project assets directory zip file](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/assets.zip) and unzip.</span></span>

1. <span data-ttu-id="7720e-190">`assets` 디렉터리를 *ObjectDetection* 프로젝트 디렉터리에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-190">Copy the `assets` directory into your *ObjectDetection* project directory.</span></span> <span data-ttu-id="7720e-191">이 디렉터리 및 해당 하위 디렉터리에는 이 자습서에 필요한 이미지 파일이 포함되어 있습니다(다음 단계에서 다운로드 및 추가하는 Tiny YOLOv2 모델 제외).</span><span class="sxs-lookup"><span data-stu-id="7720e-191">This directory and its subdirectories contain the image files (except for the Tiny YOLOv2 model, which you'll download and add in the next step) needed for this tutorial.</span></span>

1. <span data-ttu-id="7720e-192">[ONNX Model Zoo](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny_yolov2)에서 [Tiny YOLOv2 모델](https://onnxzoo.blob.core.windows.net/models/opset_8/tiny_yolov2/tiny_yolov2.tar.gz)을 다운로드하고 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-192">Download the [Tiny YOLOv2 model](https://onnxzoo.blob.core.windows.net/models/opset_8/tiny_yolov2/tiny_yolov2.tar.gz) from the [ONNX Model Zoo](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny_yolov2), and unzip.</span></span>

    <span data-ttu-id="7720e-193">명령 프롬프트를 열고 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-193">Open the command prompt and enter the following command:</span></span>

    ```shell
    tar -xvzf tiny_yolov2.tar.gz
    ```

1. <span data-ttu-id="7720e-194">방금 압축을 푼 디렉터리에서 *ObjectDetection* 프로젝트 `assets\Model` 디렉터리로 추출된 `model.onnx` 파일을 복사하고 이름을 `TinyYolo2_model.onnx`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-194">Copy the extracted `model.onnx` file from the directory just unzipped into your *ObjectDetection* project `assets\Model` directory and rename it to `TinyYolo2_model.onnx`.</span></span> <span data-ttu-id="7720e-195">이 디렉터리에는 이 자습서에 필요한 모델이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-195">This directory contains the model needed for this tutorial.</span></span>

1. <span data-ttu-id="7720e-196">솔루션 탐색기에서 자산 디렉터리 및 하위 디렉터리의 각 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-196">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="7720e-197">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-197">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="7720e-198">클래스 만들기 및 경로 정의</span><span class="sxs-lookup"><span data-stu-id="7720e-198">Create classes and define paths</span></span>

<span data-ttu-id="7720e-199">*Program.cs* 파일을 열고 다음 추가 `using` 문을 파일의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-199">Open the *Program.cs* file and add the following additional `using` statements to the top of the file:</span></span>

[!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L1-L7)]

<span data-ttu-id="7720e-200">다음으로 다양한 자산의 경로를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-200">Next, define the paths of the various assets.</span></span>

1. <span data-ttu-id="7720e-201">먼저 `GetAbsolutePath` 메서드를 `Program` 클래스의 `Main` 메서드 아래 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-201">First, add the `GetAbsolutePath` method below the `Main` method in the `Program` class.</span></span>

    [!code-csharp [GetAbsolutePath](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L66-L74)]

1. <span data-ttu-id="7720e-202">그런 다음, `Main` 메서드 내에서 자산의 위치를 저장하는 필드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-202">Then, inside the `Main` method, create fields to store the location of your assets.</span></span>

    [!code-csharp [AssetDefinition](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L17-L21)]

<span data-ttu-id="7720e-203">프로젝트에 새 디렉터리를 추가하여 입력 데이터 및 예측 클래스를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-203">Add a new directory to your project to store your input data and prediction classes.</span></span>

<span data-ttu-id="7720e-204">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-204">In **Solution Explorer**, right-click the project, and then select **Add** > **New Folder**.</span></span> <span data-ttu-id="7720e-205">새 폴더가 솔루션 탐색기에 표시되면 이름을 “DataStructures”로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-205">When the new folder appears in the Solution Explorer, name it "DataStructures".</span></span>

<span data-ttu-id="7720e-206">새로 만든 *DataStructures* 디렉터리에 입력 데이터 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-206">Create your input data class in the newly created *DataStructures* directory.</span></span>

1. <span data-ttu-id="7720e-207">**솔루션 탐색기**에서 *DataStructures* 디렉터리를 마우스 오른쪽 단추로 클릭한 다음 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-207">In **Solution Explorer**, right-click the *DataStructures* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="7720e-208">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *ImageNetData.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-208">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImageNetData.cs*.</span></span> <span data-ttu-id="7720e-209">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-209">Then, select the **Add** button.</span></span>

    <span data-ttu-id="7720e-210">*ImageNetData.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-210">The *ImageNetData.cs* file opens in the code editor.</span></span> <span data-ttu-id="7720e-211">다음 `using` 문을 *ImageNetData.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-211">Add the following `using` statement to the top of *ImageNetData.cs*:</span></span>

    [!code-csharp [ImageNetDataUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetData.cs#L1-L4)]

    <span data-ttu-id="7720e-212">기존 클래스 정의를 제거하고 `ImageNetData` 클래스에 대한 다음 코드를 *ImageNetData.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-212">Remove the existing class definition and add the following code for the `ImageNetData` class to the *ImageNetData.cs* file:</span></span>

    [!code-csharp [ImageNetDataClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetData.cs#L8-L23)]

    <span data-ttu-id="7720e-213">`ImageNetData`는 입력 이미지 데이터 클래스이며 다음 <xref:System.String> 필드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-213">`ImageNetData` is the input image data class and has the following <xref:System.String> fields:</span></span>

    - <span data-ttu-id="7720e-214">`ImagePath`에는 이미지가 저장되는 경로가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-214">`ImagePath` contains the path where the image is stored.</span></span>
    - <span data-ttu-id="7720e-215">`Label`에는 파일 이름이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-215">`Label` contains the name of the file.</span></span>

    <span data-ttu-id="7720e-216">또한 `ImageNetData`에는 지정된 `imageFolder` 경로에 저장된 여러 이미지 파일을 로드하여 `ImageNetData` 개체의 컬렉션으로 반환하는 `ReadFromFile` 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-216">Additionally, `ImageNetData` contains a method `ReadFromFile` which loads multiple image files stored in the `imageFolder` path specified and returns them as a collection of `ImageNetData` objects.</span></span>

<span data-ttu-id="7720e-217">*DataStructures* 디렉터리에 예측 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-217">Create your prediction class in the *DataStructures* directory.</span></span>

1. <span data-ttu-id="7720e-218">**솔루션 탐색기**에서 *DataStructures* 디렉터리를 마우스 오른쪽 단추로 클릭한 다음 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-218">In **Solution Explorer**, right-click the *DataStructures* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="7720e-219">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *ImageNetPrediction.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-219">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImageNetPrediction.cs*.</span></span> <span data-ttu-id="7720e-220">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-220">Then, select the **Add** button.</span></span>

    <span data-ttu-id="7720e-221">*ImageNetPrediction.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-221">The *ImageNetPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="7720e-222">다음 `using` 문을 *ImageNetPrediction.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-222">Add the following `using` statement to the top of *ImageNetPrediction.cs*:</span></span>

    [!code-csharp [ImageNetPredictionUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetPrediction.cs#L1)]

    <span data-ttu-id="7720e-223">기존 클래스 정의를 제거하고 `ImageNetPrediction` 클래스에 대한 다음 코드를 *ImageNetPrediction.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-223">Remove the existing class definition and add the following code for the `ImageNetPrediction` class to the *ImageNetPrediction.cs* file:</span></span>

    [!code-csharp [ImageNetPredictionClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/DataStructures/ImageNetPrediction.cs#L5-L9)]

    <span data-ttu-id="7720e-224">`ImageNetPrediction`은 예측 데이터 클래스이며 다음 `float[]` 필드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-224">`ImageNetPrediction` is the prediction data class and has the following `float[]` field:</span></span>

    - <span data-ttu-id="7720e-225">`PredictedLabel`에는 이미지에서 검색된 각 경계 상자의 크기, 개체 점수 및 클래스 확률이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-225">`PredictedLabel` contains the dimensions, objectness score and class probabilities for each of the bounding boxes detected in an image.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="7720e-226">Main에서 변수 초기화</span><span class="sxs-lookup"><span data-stu-id="7720e-226">Initialize variables in Main</span></span>

<span data-ttu-id="7720e-227">[MLContext 클래스](xref:Microsoft.ML.MLContext)는 모든 ML.NET 작업의 시작점이며, `mlContext`를 초기화하면 모델 생성 워크플로 개체 간에 공유할 수 있는 새 ML.NET 환경이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-227">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="7720e-228">개념적으로 Entity Framework의 `DBContext`와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-228">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="7720e-229">`outputFolder` 필드 아래 *Program.cs*의 `Main` 메서드에 다음 줄을 추가하여 `MLContext`의 새로운 인스턴스로 `mlContext` 변수를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-229">Initialize the `mlContext` variable with a new instance of `MLContext` by adding the following line to the `Main` method of *Program.cs* below the `outputFolder` field.</span></span>

[!code-csharp [InitMLContext](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L24)]

## <a name="create-a-parser-to-post-process-model-outputs"></a><span data-ttu-id="7720e-230">파서를 만들어 모델 출력 후처리</span><span class="sxs-lookup"><span data-stu-id="7720e-230">Create a parser to post-process model outputs</span></span>

<span data-ttu-id="7720e-231">모델은 이미지를 `13 x 13` 그리드로 나눕니다. 여기서 각 그리드 셀은 `32px x 32px`입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-231">The model segments an image into a `13 x 13` grid, where each grid cell is `32px x 32px`.</span></span> <span data-ttu-id="7720e-232">각 그리드 셀에는 5개의 잠재적 개체 경계 상자가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-232">Each grid cell contains 5 potential object bounding boxes.</span></span> <span data-ttu-id="7720e-233">경계 상자에는 25개의 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-233">A bounding box has  25 elements:</span></span>

![왼쪽에 모눈 샘플, 오른쪽에 경계 상자 샘플 표시](./media/object-detection-onnx/model-output-description.png)

- <span data-ttu-id="7720e-235">`x` 연결된 그리드 셀을 기준으로 하는 경계 상자 중심의 x 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-235">`x` the x position of the bounding box center relative to the grid cell it's associated with.</span></span>
- <span data-ttu-id="7720e-236">`y` 연결된 그리드 셀을 기준으로 하는 경계 상자 중심의 y 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-236">`y` the y position of the bounding box center relative to the grid cell it's associated with.</span></span>
- <span data-ttu-id="7720e-237">`w` 경계 상자의 너비입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-237">`w` the width of the bounding box.</span></span>
- <span data-ttu-id="7720e-238">`h` 경계 상자의 높이입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-238">`h` the height of the bounding box.</span></span>
- <span data-ttu-id="7720e-239">`o` 경계 상자 내에 개체가 있는 신뢰도 값입니다(개체성 점수라고도 함).</span><span class="sxs-lookup"><span data-stu-id="7720e-239">`o` the confidence value that an object exists within the bounding box, also known as objectness score.</span></span>
- <span data-ttu-id="7720e-240">`p1-p20` 모델에서 예측하는 20개 클래스 각각의 클래스 확률입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-240">`p1-p20` class probabilities for each of the 20 classes predicted by the model.</span></span>

<span data-ttu-id="7720e-241">각각 5개의 경계 상자를 설명하는 총 25개의 요소는 각 그리드 셀에 포함된 125개의 요소를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-241">In total, the 25 elements describing each of the 5 bounding boxes make up the 125 elements contained in each grid cell.</span></span>

<span data-ttu-id="7720e-242">미리 학습된 ONNX 모델에서 생성한 출력은 `125 x 13 x 13` 크기의 텐서 요소를 나타내는 `21125` 길이의 부동 소수점 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-242">The output generated by the pre-trained ONNX model is a float array of length `21125`, representing the elements of a tensor with dimensions `125 x 13 x 13`.</span></span> <span data-ttu-id="7720e-243">모델에서 생성한 예측을 텐서로 변환하려면 몇 가지 후처리 작업이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-243">In order to transform the predictions generated by the model into a tensor, some post-processing work is required.</span></span> <span data-ttu-id="7720e-244">이렇게 하려면 출력을 구문 분석하는 데 도움이 되는 클래스 집합을 만드세요.</span><span class="sxs-lookup"><span data-stu-id="7720e-244">To do so, create a set of classes to help parse the output.</span></span>

<span data-ttu-id="7720e-245">프로젝트에 새 디렉터리를 추가하여 파서 클래스 집합을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-245">Add a new directory to your project to organize the set of parser classes.</span></span>

1. <span data-ttu-id="7720e-246">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-246">In **Solution Explorer**, right-click the project, and then select **Add** > **New Folder**.</span></span> <span data-ttu-id="7720e-247">새 폴더가 솔루션 탐색기에 표시되면 이름을 “YoloParser”로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-247">When the new folder appears in the Solution Explorer, name it "YoloParser".</span></span>

### <a name="create-bounding-boxes-and-dimensions"></a><span data-ttu-id="7720e-248">경계 상자 및 차원 만들기</span><span class="sxs-lookup"><span data-stu-id="7720e-248">Create bounding boxes and dimensions</span></span>

<span data-ttu-id="7720e-249">모델의 데이터 출력에는 이미지 내 개체의 경계 상자에 대한 좌표와 크기가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-249">The data output by the model contains coordinates and dimensions of the bounding boxes of objects within the image.</span></span> <span data-ttu-id="7720e-250">차원의 기본 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-250">Create a base class for dimensions.</span></span>

1. <span data-ttu-id="7720e-251">**솔루션 탐색기**에서 *YoloParser* 디렉터리를 마우스 오른쪽 단추로 클릭한 다음 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-251">In **Solution Explorer**, right-click the *YoloParser* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="7720e-252">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *DimensionsBase.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-252">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *DimensionsBase.cs*.</span></span> <span data-ttu-id="7720e-253">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-253">Then, select the **Add** button.</span></span>

    <span data-ttu-id="7720e-254">*DimensionsBase.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-254">The *DimensionsBase.cs* file opens in the code editor.</span></span> <span data-ttu-id="7720e-255">모든 `using` 문과 기존 클래스 정의를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-255">Remove all `using` statements and existing class definition.</span></span>

    <span data-ttu-id="7720e-256">`DimensionsBase` 클래스의 다음 코드를 *DimensionsBase.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-256">Add the following code for the `DimensionsBase` class to the *DimensionsBase.cs* file:</span></span>

    [!code-csharp [DimensionsBaseClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/DimensionsBase.cs#L3-L9)]

    <span data-ttu-id="7720e-257">`DimensionsBase`에는 다음 `float` 필드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-257">`DimensionsBase` has the following `float` fields:</span></span>

    - <span data-ttu-id="7720e-258">`X`에는 x축의 개체 위치가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-258">`X` contains the position of the object along the x-axis.</span></span>
    - <span data-ttu-id="7720e-259">`Y`에는 y축의 개체 위치가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-259">`Y` contains the position of the object along the y-axis.</span></span>
    - <span data-ttu-id="7720e-260">`Height`에는 개체의 높이가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-260">`Height` contains the height of the object.</span></span>
    - <span data-ttu-id="7720e-261">`Width`에는 개체의 너비가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-261">`Width` contains the width of the object.</span></span>

<span data-ttu-id="7720e-262">다음으로 경계 상자의 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-262">Next, create a class for your bounding boxes.</span></span>

1. <span data-ttu-id="7720e-263">**솔루션 탐색기**에서 *YoloParser* 디렉터리를 마우스 오른쪽 단추로 클릭한 다음 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-263">In **Solution Explorer**, right-click the *YoloParser* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="7720e-264">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *YoloBoundingBox.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-264">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *YoloBoundingBox.cs*.</span></span> <span data-ttu-id="7720e-265">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-265">Then, select the **Add** button.</span></span>

    <span data-ttu-id="7720e-266">*YoloBoundingBox.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-266">The *YoloBoundingBox.cs* file opens in the code editor.</span></span> <span data-ttu-id="7720e-267">다음 `using` 문을 *YoloBoundingBox.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-267">Add the following `using` statement to the top of *YoloBoundingBox.cs*:</span></span>

    [!code-csharp [YoloBoundingBoxUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L1)]

    <span data-ttu-id="7720e-268">각 경계 상자의 크기를 포함하도록 기존 클래스 정의 바로 위에 `DimensionsBase` 클래스에서 상속하는 `BoundingBoxDimensions`라는 새 클래스 정의를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-268">Just above the existing class definition, add a new class definition called `BoundingBoxDimensions` which inherits from the `DimensionsBase` class to contain the dimensions of the respective bounding box.</span></span>

    [!code-csharp [BoundingBoxDimClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L5)]

    <span data-ttu-id="7720e-269">기존 `YoloBoundingBox` 클래스 정의를 제거하고 `YoloBoundingBox` 클래스의 다음 코드를 *YoloBoundingBox.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-269">Remove the existing `YoloBoundingBox` class definition and add the following code for the `YoloBoundingBox` class to the *YoloBoundingBox.cs* file:</span></span>

    [!code-csharp [YoloBoundingBoxClass](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloBoundingBox.cs#L7-L21)]

    <span data-ttu-id="7720e-270">`YoloBoundingBox`에는 다음 필드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-270">`YoloBoundingBox` has the following fields:</span></span>

    - <span data-ttu-id="7720e-271">`Dimensions`에는 경계 상자의 크기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-271">`Dimensions` contains dimensions of the bounding box.</span></span>
    - <span data-ttu-id="7720e-272">`Label`에는 경계 상자 내에서 검색된 개체의 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-272">`Label` contains the class of object detected within the bounding box.</span></span>
    - <span data-ttu-id="7720e-273">`Confidence`에는 클래스의 신뢰도가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-273">`Confidence` contains the confidence of the class.</span></span>
    - <span data-ttu-id="7720e-274">`Rect`에는 경계 상자 크기의 사각형 표현이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-274">`Rect` contains the rectangle representation of the bounding box's dimensions.</span></span>
    - <span data-ttu-id="7720e-275">`BoxColor`에는 이미지를 그리는 데 사용되는 각 클래스와 관련된 색이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-275">`BoxColor` contains the color associated with the respective class used to draw on the image.</span></span>

### <a name="create-the-parser"></a><span data-ttu-id="7720e-276">파서 만들기</span><span class="sxs-lookup"><span data-stu-id="7720e-276">Create the parser</span></span>

<span data-ttu-id="7720e-277">이제 차원 및 경계 상자의 클래스가 생성되므로, 파서를 만들 때입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-277">Now that the classes for dimensions and bounding boxes are created, it's time to create the parser.</span></span>

1. <span data-ttu-id="7720e-278">**솔루션 탐색기**에서 *YoloParser* 디렉터리를 마우스 오른쪽 단추로 클릭한 다음 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-278">In **Solution Explorer**, right-click the *YoloParser* directory, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="7720e-279">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *YoloOutputParser.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-279">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *YoloOutputParser.cs*.</span></span> <span data-ttu-id="7720e-280">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-280">Then, select the **Add** button.</span></span>

    <span data-ttu-id="7720e-281">*YoloOutputParser.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-281">The *YoloOutputParser.cs* file opens in the code editor.</span></span> <span data-ttu-id="7720e-282">다음 `using` 문을 *YoloOutputParser.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-282">Add the following `using` statement to the top of *YoloOutputParser.cs*:</span></span>

    [!code-csharp [YoloParserUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L1-L4)]

    <span data-ttu-id="7720e-283">기존 `YoloOutputParser` 클래스 정의 내에서 이미지에 있는 각 셀의 크기를 포함하는 중첩된 클래스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-283">Inside the existing `YoloOutputParser` class definition, add a nested class that contains the dimensions of each of the cells in the image.</span></span> <span data-ttu-id="7720e-284">`YoloOutputParser` 클래스 정의의 맨 위에 있는 `DimensionsBase` 클래스에서 상속하는 `CellDimensions` 클래스의 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-284">Add the following code for the `CellDimensions` class which inherits from the `DimensionsBase` class at the top of the `YoloOutputParser` class definition.</span></span>

    [!code-csharp [YoloParserUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L10)]

1. <span data-ttu-id="7720e-285">`YoloOutputParser` 클래스 정의 내에 다음 상수와 필드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-285">Inside the `YoloOutputParser` class definition, add the following constant and fields.</span></span>

    [!code-csharp [ParserVarDefinitions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L12-L21)]

    - <span data-ttu-id="7720e-286">`ROW_COUNT`는 그리드에서 이미지가 나뉘는 행의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-286">`ROW_COUNT` is the number of rows in the grid the image is divided into.</span></span>
    - <span data-ttu-id="7720e-287">`COL_COUNT`는 그리드에서 이미지가 나뉘는 열의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-287">`COL_COUNT` is the number of columns in the grid the image is divided into.</span></span>
    - <span data-ttu-id="7720e-288">`CHANNEL_COUNT`는 그리드의 한 셀에 포함된 총 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-288">`CHANNEL_COUNT` is the total number of values contained in one cell of the grid.</span></span>
    - <span data-ttu-id="7720e-289">`BOXES_PER_CELL`은 셀의 경계 상자 수이며,</span><span class="sxs-lookup"><span data-stu-id="7720e-289">`BOXES_PER_CELL` is the number of bounding boxes in a cell,</span></span>
    - <span data-ttu-id="7720e-290">`BOX_INFO_FEATURE_COUNT`는 상자에 포함된 기능 수입니다(x, y, 높이, 너비, 신뢰도).</span><span class="sxs-lookup"><span data-stu-id="7720e-290">`BOX_INFO_FEATURE_COUNT` is the number of features contained within a box (x,y,height,width,confidence).</span></span>
    - <span data-ttu-id="7720e-291">`CLASS_COUNT`는 각 경계 상자에 포함된 클래스 예측 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-291">`CLASS_COUNT` is the number of class predictions contained in each bounding box.</span></span>
    - <span data-ttu-id="7720e-292">`CELL_WIDTH`는 이미지 그리드에 있는 한 셀의 너비입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-292">`CELL_WIDTH` is the width of one cell in the image grid.</span></span>
    - <span data-ttu-id="7720e-293">`CELL_HEIGHT`는 이미지 그리드에 있는 한 셀의 높이입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-293">`CELL_HEIGHT` is the height of one cell in the image grid.</span></span>
    - <span data-ttu-id="7720e-294">`channelStride`는 그리드에서 현재 셀의 시작 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-294">`channelStride` is the starting position of the current cell in the grid.</span></span>

    <span data-ttu-id="7720e-295">모델은 점수라고도 하는 예측을 생성할 때 `416px x 416px` 입력 이미지를 `13 x 13` 크기의 셀 그리드로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-295">When the model makes a prediction, also known as scoring, it divides the `416px x 416px` input image into a grid of cells the size of `13 x 13`.</span></span> <span data-ttu-id="7720e-296">포함된 각 셀은 `32px x 32px`입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-296">Each cell contains is `32px x 32px`.</span></span> <span data-ttu-id="7720e-297">각 셀에는 각각 5개의 기능(x, y, 너비, 높이, 신뢰도)을 포함하는 5개의 경계 상자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-297">Within each cell, there are 5 bounding boxes each containing 5 features (x, y, width, height, confidence).</span></span> <span data-ttu-id="7720e-298">또한 각 경계 상자에는 각 클래스의 확률이 포함되며, 이 경우에는 20입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-298">In addition, each bounding box contains the probability of each of the classes which in this case is 20.</span></span> <span data-ttu-id="7720e-299">따라서 각 셀에는 125개의 정보(5개의 기능 + 20개의 클래스 확률)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-299">Therefore, each cell contains 125 pieces of information (5 features + 20 class probabilities).</span></span>

<span data-ttu-id="7720e-300">`channelStride` 아래에 5개의 경계 상자 모두에 대한 고정 목록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-300">Create a list of anchors below `channelStride` for all 5 bounding boxes:</span></span>

[!code-csharp [ParserAnchors](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L23-L26)]

<span data-ttu-id="7720e-301">앵커는 경계 상자의 미리 정의된 높이 및 너비 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-301">Anchors are pre-defined height and width ratios of bounding boxes.</span></span> <span data-ttu-id="7720e-302">모델에서 검색한 대부분의 개체 또는 클래스는 비율이 서로 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-302">Most object or classes detected by a model have similar ratios.</span></span> <span data-ttu-id="7720e-303">따라서 경계 상자를 만들 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-303">This is valuable when it comes to creating bounding boxes.</span></span> <span data-ttu-id="7720e-304">경계 상자를 예측하는 대신 미리 정의된 차원의 오프셋을 계산하므로 경계 상자를 예측하는 데 필요한 계산이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-304">Instead of predicting the bounding boxes, the offset from the pre-defined dimensions is calculated therefore reducing the computation required to predict the bounding box.</span></span> <span data-ttu-id="7720e-305">일반적으로 이러한 고정 비율은 사용된 데이터 세트를 기반으로 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-305">Typically these anchor ratios are calculated based on the dataset used.</span></span> <span data-ttu-id="7720e-306">이 경우 데이터 세트가 알려져 있고 값이 미리 컴퓨팅되었기 때문에 앵커는 하드 코딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-306">In this case because the dataset is known and the values have been pre-computed, the anchors can be hard-coded.</span></span>

<span data-ttu-id="7720e-307">그런 다음 모델에서 예측할 레이블 또는 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-307">Next, define the labels or classes that the model will predict.</span></span> <span data-ttu-id="7720e-308">이 모델은 원래 YOLOv2 모델에서 예측한 총 클래스 수의 하위 집합인 20개의 클래스를 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-308">This model predicts 20 classes which is a subset of the total number of classes predicted by the original YOLOv2 model.</span></span>

<span data-ttu-id="7720e-309">`anchors` 아래에 레이블 목록을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-309">Add your list of labels below the `anchors`.</span></span>

[!code-csharp [ParserLabels](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L28-L34)]

<span data-ttu-id="7720e-310">각 클래스와 관련된 색이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-310">There are colors associated with each of the classes.</span></span> <span data-ttu-id="7720e-311">`labels` 아래에 클래스 색을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-311">Assign your class colors below your `labels`:</span></span>

[!code-csharp [ParserColors](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L36-L59)]

### <a name="create-helper-functions"></a><span data-ttu-id="7720e-312">도우미 함수 만들기</span><span class="sxs-lookup"><span data-stu-id="7720e-312">Create helper functions</span></span>

<span data-ttu-id="7720e-313">후처리 단계와 관련된 일련의 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-313">There are a series of steps involved in the post-processing phase.</span></span> <span data-ttu-id="7720e-314">이를 지원하려면 몇 가지 도우미 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-314">To help with that, several helper methods can be employed.</span></span>

<span data-ttu-id="7720e-315">파서에서 사용하는 도우미 메서드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-315">The helper methods used in by the parser are:</span></span>

- <span data-ttu-id="7720e-316">`Sigmoid`는 0에서 1 사이의 숫자를 출력하는 sigmoid 함수를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-316">`Sigmoid` applies the sigmoid function that outputs a number between 0 and 1.</span></span>
- <span data-ttu-id="7720e-317">`Softmax`는 입력 벡터를 확률 분포로 정규화합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-317">`Softmax` normalizes an input vector into a probability distribution.</span></span>
- <span data-ttu-id="7720e-318">`GetOffset`은 1차원 모델 출력의 요소를 `125 x 13 x 13` 텐서의 해당 위치에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-318">`GetOffset` maps elements in the one-dimensional model output to the corresponding position in a `125 x 13 x 13` tensor.</span></span>
- <span data-ttu-id="7720e-319">`ExtractBoundingBoxes`는 모델 출력의 `GetOffset` 메서드를 사용하여 경계 상자 차원을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-319">`ExtractBoundingBoxes` extracts the bounding box dimensions using the `GetOffset` method from the model output.</span></span>
- <span data-ttu-id="7720e-320">`GetConfidence`는 모델에서 개체를 발견한 확률을 나타내는 신뢰도 값을 추출하고 `Sigmoid` 함수를 사용하여 백분율로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-320">`GetConfidence` extracts the confidence value which states how sure the model is that it has detected an object and uses the `Sigmoid` function to turn it into a percentage.</span></span>
- <span data-ttu-id="7720e-321">`MapBoundingBoxToCell`은 경계 상자 차원을 사용하여 이미지 내의 해당 셀에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-321">`MapBoundingBoxToCell` uses the bounding box dimensions and maps them onto its respective cell within the image.</span></span>
- <span data-ttu-id="7720e-322">`ExtractClasses`는 `GetOffset` 메서드를 사용하여 모델 출력에서 경계 상자의 클래스 예측을 추출한 다음 `Softmax` 메서드를 사용하여 확률 분포로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-322">`ExtractClasses` extracts the class predictions for the bounding box from the model output using the `GetOffset` method and turns them into a probability distribution using the `Softmax` method.</span></span>
- <span data-ttu-id="7720e-323">`GetTopResult`는 확률이 가장 높은 예측 클래스 목록에서 클래스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-323">`GetTopResult` selects the class from the list of predicted classes with the highest probability.</span></span>
- <span data-ttu-id="7720e-324">`IntersectionOverUnion`은 낮은 확률의 겹치는 경계 상자를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-324">`IntersectionOverUnion` filters overlapping bounding boxes with lower probabilities.</span></span>

<span data-ttu-id="7720e-325">모든 도우미 메서드 코드를 `classColors` 목록 아래 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-325">Add the code for all the helper methods below your list of `classColors`.</span></span>

[!code-csharp [ParserHelperMethods](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L61-L151)]

<span data-ttu-id="7720e-326">모든 도우미 메서드를 정의하고 나면 이제 이 메서드를 사용하여 모델 출력을 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-326">Once you have defined all of the helper methods, it's time to use them to process the model output.</span></span>

<span data-ttu-id="7720e-327">`IntersectionOverUnion` 메서드 아래에서 `ParseOutputs` 메서드를 만들어 모델에서 생성한 출력을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-327">Below the `IntersectionOverUnion` method, create the `ParseOutputs` method to process the output generated by the model.</span></span>

```csharp
public IList<YoloBoundingBox> ParseOutputs(float[] yoloModelOutputs, float threshold = .3F)
{

}
```

<span data-ttu-id="7720e-328">목록을 만들어 경계 상자를 저장하고 `ParseOutputs` 메서드 내에 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-328">Create a list to store your bounding boxes and define variables inside the `ParseOutputs` method.</span></span>

[!code-csharp [BBoxList](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L155)]

<span data-ttu-id="7720e-329">각 이미지는 `13 x 13` 셀의 그리드로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-329">Each image is divided into a grid of `13 x 13` cells.</span></span> <span data-ttu-id="7720e-330">각 셀에는 5개의 경계 상자가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-330">Each cell contains five bounding boxes.</span></span> <span data-ttu-id="7720e-331">`boxes` 변수 아래에 각 셀의 모든 상자를 처리하는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-331">Below the `boxes` variable, add code to process all of the boxes in each of the cells.</span></span>

```csharp
for (int row = 0; row < ROW_COUNT; row++)
{
    for (int column = 0; column < COL_COUNT; column++)
    {
        for (int box = 0; box < BOXES_PER_CELL; box++)
        {

        }
    }
}
```

<span data-ttu-id="7720e-332">1차원 모델 출력에서 현재 상자의 시작 위치를 가장 안쪽의 루프에서 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-332">Inside the inner-most loop, calculate the starting position of the current box within the one-dimensional model output.</span></span>

[!code-csharp [ChannelDef](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L163)]

<span data-ttu-id="7720e-333">바로 아래에서 `ExtractBoundingBoxDimensions` 메서드를 사용하여 현재 경계 상자의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-333">Directly below that, use the `ExtractBoundingBoxDimensions` method to get the dimensions of the current bounding box.</span></span>

[!code-csharp [GetBBoxDims](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L165)]

<span data-ttu-id="7720e-334">그런 다음 `GetConfidence` 메서드를 사용하여 현재 경계 상자의 신뢰도를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-334">Then, use the `GetConfidence` method to get the confidence for the current bounding box.</span></span>

[!code-csharp [GetConfidence](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L167)]

<span data-ttu-id="7720e-335">그런 다음 `MapBoundingBoxToCell` 메서드를 사용하여 현재 경계 상자를 처리 중인 현재 셀에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-335">After that, use the `MapBoundingBoxToCell` method to map the current bounding box to the current cell being processed.</span></span>

[!code-csharp [MapBoundingBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L169)]

<span data-ttu-id="7720e-336">추가 처리를 수행하기 전에 신뢰도 값이 제공된 임계값보다 큰지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-336">Before doing any further processing, check whether your confidence value is greater than the threshold provided.</span></span> <span data-ttu-id="7720e-337">그렇지 않은 경우 다음 경계 상자를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-337">If not, process the next bounding box.</span></span>

[!code-csharp [CheckThreshold1](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L171-L172)]

<span data-ttu-id="7720e-338">그렇지 않으면 출력을 계속 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-338">Otherwise, continue processing the output.</span></span> <span data-ttu-id="7720e-339">다음 단계에서는 `ExtractClasses` 메서드를 사용하여 현재 경계 상자에 대해 예측된 클래스의 확률 분포를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-339">The next step is to get the probability distribution of the predicted classes for the current bounding box using the `ExtractClasses` method.</span></span>

[!code-csharp [ExtractClasses](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L174)]

<span data-ttu-id="7720e-340">그런 다음 `GetTopResult` 메서드를 사용하여 현재 상자의 확률이 가장 높은 클래스 값과 색인을 가져오고 해당 점수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-340">Then, use the `GetTopResult` method to get the value and index of the class with the highest probability for the current box and compute its score.</span></span>

[!code-csharp [GetTopResult](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L176-L177)]

<span data-ttu-id="7720e-341">`topScore`를 사용하여 지정된 임계값을 초과하는 경계 상자만 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-341">Use the `topScore` to once again keep only those bounding boxes that are above the specified threshold.</span></span>

[!code-csharp [CheckThreshold2](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L179-L180)]

<span data-ttu-id="7720e-342">마지막으로 현재 경계 상자가 임계값을 초과하는 경우 새 `BoundingBox` 개체를 만들어 `boxes` 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-342">Finally, if the current bounding box exceeds the threshold, create a new `BoundingBox` object and add it to the `boxes` list.</span></span>

[!code-csharp [AddBBoxToList](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L182-L194)]

<span data-ttu-id="7720e-343">이미지의 모든 셀을 처리한 후 `boxes` 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-343">Once all cells in the image have been processed, return the `boxes` list.</span></span> <span data-ttu-id="7720e-344">`ParseOutputs` 메서드의 가장 바깥쪽 for 루프 아래에 다음 return 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-344">Add the following return statement below the outer-most for-loop in the `ParseOutputs` method.</span></span>

[!code-csharp [ReturnBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L198)]

### <a name="filter-overlapping-boxes"></a><span data-ttu-id="7720e-345">겹치는 상자 필터</span><span class="sxs-lookup"><span data-stu-id="7720e-345">Filter overlapping boxes</span></span>

<span data-ttu-id="7720e-346">모델 출력에서 신뢰도가 높은 모든 경계 상자를 추출했으므로 추가 필터링을 수행하여 겹치는 이미지를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-346">Now that all of the highly confident bounding boxes have been extracted from the model output, additional filtering needs to be done to remove overlapping images.</span></span> <span data-ttu-id="7720e-347">`ParseOutputs` 메서드 아래 `FilterBoundingBoxes`라는 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-347">Add a method called `FilterBoundingBoxes` below the `ParseOutputs` method:</span></span>

```csharp
public IList<YoloBoundingBox> FilterBoundingBoxes(IList<YoloBoundingBox> boxes, int limit, float threshold)
{

}
```

<span data-ttu-id="7720e-348">`FilterBoundingBoxes` 메서드 내에서 검색된 상자의 크기와 같은 배열을 만들고 모든 슬롯을 활성 또는 처리할 준비 완료로 표시하여 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-348">Inside the `FilterBoundingBoxes` method, start off by creating an array equal to the size of detected boxes and marking all slots as active or ready for processing.</span></span>

[!code-csharp [InitActiveSlots](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L203-L207)]

<span data-ttu-id="7720e-349">그런 다음, 경계 상자를 포함하는 목록을 신뢰도에 따라 내림차순으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-349">Then, sort the list containing your bounding boxes in descending order based on confidence.</span></span>

[!code-csharp [SortBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L209-L211)]

<span data-ttu-id="7720e-350">그런 다음 필터링된 결과를 저장할 목록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-350">After that, create a list to hold the filtered results.</span></span>

[!code-csharp [InitFilterResult](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L213)]

<span data-ttu-id="7720e-351">각 경계 상자를 반복하여 각 경계 상자에 대한 처리를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-351">Begin processing each bounding box by iterating over each of the bounding boxes.</span></span>

```csharp
for (int i = 0; i < boxes.Count; i++)
{

}
```

<span data-ttu-id="7720e-352">이 for 루프 내에서 현재 경계 상자를 처리할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-352">Inside of this for-loop, check whether the current bounding box can be processed.</span></span>

```csharp
if (isActiveBoxes[i])
{

}
```

<span data-ttu-id="7720e-353">그런 경우 경계 상자를 결과 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-353">If so, add the bounding box to the list of results.</span></span> <span data-ttu-id="7720e-354">결과가 추출할 상자의 지정된 한도를 초과하면 루프를 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-354">If the results exceeds the specified limit of boxes to be extracted, break out of the loop.</span></span> <span data-ttu-id="7720e-355">If-문 내에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-355">Add the following code inside the if-statement.</span></span>

[!code-csharp [AddFirstBBoxToResults](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L219-L223)]

<span data-ttu-id="7720e-356">처리할 수 없으면 인접한 경계 상자를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-356">Otherwise, look at the adjacent bounding boxes.</span></span> <span data-ttu-id="7720e-357">상자 제한 검사 아래에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-357">Add the following code below the box limit check.</span></span>

```csharp
for (var j = i + 1; j < boxes.Count; j++)
{

}
```

<span data-ttu-id="7720e-358">첫 번째 상자와 같이 인접한 상자가 활성 상태이거나 처리할 준비가 된 경우 `IntersectionOverUnion` 메서드를 사용하여 첫 번째 상자와 두 번째 상자가 지정된 임계값을 초과하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-358">Like the first box, if the adjacent box is active or ready to be processed, use the `IntersectionOverUnion` method to check whether the first box and the second box exceed the specified threshold.</span></span> <span data-ttu-id="7720e-359">가장 안쪽에 있는 for 루프에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-359">Add the following code to your inner-most for-loop.</span></span>

[!code-csharp [IOUBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L227-L239)]

<span data-ttu-id="7720e-360">인접 경계 상자를 확인하는 가장 안쪽의 for 루프 외부에서 처리할 나머지 경계 상자가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-360">Outside of the inner-most for-loop that checks adjacent bounding boxes, see whether there are any remaining bounding boxes to be processed.</span></span> <span data-ttu-id="7720e-361">그렇지 않은 경우 외부 for 루프를 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-361">If not, break out of the outer for-loop.</span></span>

[!code-csharp [CheckActiveSlots](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L242-L243)]

<span data-ttu-id="7720e-362">마지막으로 `FilterBoundingBoxes` 메서드의 초기 for 루프 외부에서 다음 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-362">Finally, outside of the initial for-loop of the `FilterBoundingBoxes` method, return the results:</span></span>

[!code-csharp [ReturnFilteredBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/YoloParser/YoloOutputParser.cs#L246)]

<span data-ttu-id="7720e-363">잘하셨습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-363">Great!</span></span> <span data-ttu-id="7720e-364">이제 채점을 위해 모델과 함께 이 코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-364">Now it's time to use this code along with the model for scoring.</span></span>

## <a name="use-the-model-for-scoring"></a><span data-ttu-id="7720e-365">모델을 사용하여 채점</span><span class="sxs-lookup"><span data-stu-id="7720e-365">Use the model for scoring</span></span>

<span data-ttu-id="7720e-366">후처리와 마찬가지로 채점 단계에는 몇 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-366">Just like with post-processing, there are a few steps in the scoring steps.</span></span> <span data-ttu-id="7720e-367">이 작업을 지원하기 위해 채점 로직을 포함하는 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-367">To help with this, add a class that will contain the scoring logic to your project.</span></span>

1. <span data-ttu-id="7720e-368">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-368">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="7720e-369">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *OnnxModelScorer.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-369">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *OnnxModelScorer.cs*.</span></span> <span data-ttu-id="7720e-370">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-370">Then, select the **Add** button.</span></span>

    <span data-ttu-id="7720e-371">*OnnxModelScorer.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-371">The *OnnxModelScorer.cs* file opens in the code editor.</span></span> <span data-ttu-id="7720e-372">다음 `using` 문을 *OnnxModelScorer.cs*의 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-372">Add the following `using` statement to the top of *OnnxModelScorer.cs*:</span></span>

    [!code-csharp [ScorerUsings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L1-L7)]

    <span data-ttu-id="7720e-373">`OnnxModelScorer` 클래스 정의에 다음 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-373">Inside the `OnnxModelScorer` class definition, add the following variables.</span></span>

    [!code-csharp [InitScorerVars](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L13-L17)]

    <span data-ttu-id="7720e-374">바로 아래에서 이전에 정의된 변수를 초기화할 `OnnxModelScorer` 클래스의 생성자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-374">Directly below that, create a constructor for the `OnnxModelScorer` class that will initialize the previously defined variables.</span></span>

    [!code-csharp [ScorerCtor](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L19-L24)]

    <span data-ttu-id="7720e-375">생성자를 만들었으면 이미지 및 모델 설정과 관련된 변수를 포함하는 두 개의 구조체를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-375">Once you have created the constructor, define a couple of structs that contain variables related to the image and model settings.</span></span> <span data-ttu-id="7720e-376">`ImageNetSettings`라는 구조체를 만들어 예상 높이와 너비를 모델의 입력으로 포함시킵니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-376">Create a struct called `ImageNetSettings` to contain the height and width expected as input for the model.</span></span>

    [!code-csharp [ImageNetSettingStruct](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L26-L30)]

    <span data-ttu-id="7720e-377">그런 다음 모델의 입력 및 출력 계층 이름을 포함하는 `TinyYoloModelSettings`라는 또 다른 구조체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-377">After that, create another struct called `TinyYoloModelSettings` which contains the names of the input and output layers of the model.</span></span> <span data-ttu-id="7720e-378">모델의 입력 및 출력 계층 이름을 시각화하려면 [Netron](https://github.com/lutzroeder/netron)과 같은 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-378">To visualize the name of the input and output layers of the model, you can use a tool like [Netron](https://github.com/lutzroeder/netron).</span></span>

    [!code-csharp [YoloSettingsStruct](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L32-L43)]

    <span data-ttu-id="7720e-379">다음으로 채점에 사용되는 첫 번째 메서드 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-379">Next, create the first set of methods use for scoring.</span></span> <span data-ttu-id="7720e-380">`OnnxModelScorer` 클래스 내부에 `LoadModel` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-380">Create the `LoadModel` method inside of your `OnnxModelScorer` class.</span></span>

    ```csharp
    private ITransformer LoadModel(string modelLocation)
    {

    }
    ```

    <span data-ttu-id="7720e-381">`LoadModel` 메서드 내에서 로깅을 위해 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-381">Inside the `LoadModel` method, add the following code for logging.</span></span>

    [!code-csharp [LoadModelLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L47-L49)]

    <span data-ttu-id="7720e-382">ML.NET 파이프라인은 [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*) 메서드가 호출될 때 작동할 데이터 스키마를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-382">ML.NET pipelines need to know the data schema to operate on when the [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*) method is called.</span></span> <span data-ttu-id="7720e-383">이 경우 학습과 비슷한 프로세스가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-383">In this case, a process similar to training will be used.</span></span> <span data-ttu-id="7720e-384">그러나 실제 학습이 발생하지 않기 때문에 빈 [ `IDataView` ](xref:Microsoft.ML.IDataView)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-384">However, because no actual training is happening, it is acceptable to use an empty [`IDataView`](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="7720e-385">빈 목록에서 파이프라인의 새로운 [`IDataView`](xref:Microsoft.ML.IDataView)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-385">Create a new [`IDataView`](xref:Microsoft.ML.IDataView) for the pipeline from an empty list.</span></span>

    [!code-csharp [LoadEmptyIDV](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L52)]

    <span data-ttu-id="7720e-386">그런 다음 파이프라인을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-386">Below that, define the pipeline.</span></span> <span data-ttu-id="7720e-387">파이프라인은 4개의 변환으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-387">The pipeline will consist of four transforms.</span></span>

    - <span data-ttu-id="7720e-388">[`LoadImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*)에서는 이미지를 비트맵으로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-388">[`LoadImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*) loads the image as a Bitmap.</span></span>
    - <span data-ttu-id="7720e-389">[`ResizeImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages*)는 지정된 크기로 이미지의 크기를 조정합니다(이 경우 `416 x 416`).</span><span class="sxs-lookup"><span data-stu-id="7720e-389">[`ResizeImages`](xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages*) rescales the image to the size specified (in this case, `416 x 416`).</span></span>
    - <span data-ttu-id="7720e-390">[`ExtractPixels`](xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels*)는 이미지의 픽셀 표현을 비트맵에서 숫자 벡터로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-390">[`ExtractPixels`](xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels*) changes the pixel representation of the image from a Bitmap to a numerical vector.</span></span>
    - <span data-ttu-id="7720e-391">[`ApplyOnnxModel`](xref:Microsoft.ML.OnnxCatalog.ApplyOnnxModel*)는 ONNX 모델을 로드하고 제공된 데이터를 채점하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-391">[`ApplyOnnxModel`](xref:Microsoft.ML.OnnxCatalog.ApplyOnnxModel*) loads the ONNX model and uses it to score on the data provided.</span></span>

    <span data-ttu-id="7720e-392">`data` 변수 아래에 `LoadModel` 메서드의 파이프라인을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-392">Define your pipeline in the `LoadModel` method below the `data` variable.</span></span>

    [!code-csharp [ScoringPipeline](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L55-L58)]

    <span data-ttu-id="7720e-393">이제 채점을 위해 모델을 인스턴스화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-393">Now it's time to instantiate the model for scoring.</span></span> <span data-ttu-id="7720e-394">파이프라인에서 [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*) 메서드를 호출하고 추가 처리를 위해 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-394">Call the [`Fit`](xref:Microsoft.ML.IEstimator%601.Fit*) method on the pipeline and return it for further processing.</span></span>

    [!code-csharp [FitReturnModel](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L61-L63)]

<span data-ttu-id="7720e-395">모델을 로드한 후에는 모델을 사용하여 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-395">Once the model is loaded, it can then be used to make predictions.</span></span> <span data-ttu-id="7720e-396">이 프로세스를 용이하게 하려면 `LoadModel` 메서드 아래 `PredictDataUsingModel`라는 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-396">To facilitate that process, create a method called `PredictDataUsingModel` below the `LoadModel` method.</span></span>

```csharp
private IEnumerable<float[]> PredictDataUsingModel(IDataView testData, ITransformer model)
{

}
```

<span data-ttu-id="7720e-397">`PredictDataUsingModel`내에서 로깅을 위해 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-397">Inside the `PredictDataUsingModel`, add the following code for logging.</span></span>

[!code-csharp [PredictDataLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L68-L71)]

<span data-ttu-id="7720e-398">그런 다음 [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) 메서드를 사용하여 데이터를 채점합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-398">Then, use the [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) method to score the data.</span></span>

[!code-csharp [ScoreImages](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L73)]

<span data-ttu-id="7720e-399">예측된 확률을 추출하고 추가 처리를 위해 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-399">Extract the predicted probabilities and return them for additional processing.</span></span>

[!code-csharp [ReturnModelOutput](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L75-L77)]

<span data-ttu-id="7720e-400">이제 두 단계가 모두 설정되었으므로 단일 메서드로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-400">Now that both steps are set up, combine them into a single method.</span></span> <span data-ttu-id="7720e-401">`PredictDataUsingModel` 메서드 아래 `Score`라는 새 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-401">Below the `PredictDataUsingModel` method, add a new method called `Score`.</span></span>

[!code-csharp [ScoreMethod](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/OnnxModelScorer.cs#L80-L85)]

<span data-ttu-id="7720e-402">거의 완료되었습니다!</span><span class="sxs-lookup"><span data-stu-id="7720e-402">Almost there!</span></span> <span data-ttu-id="7720e-403">이제 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-403">Now it's time to put it all to use.</span></span>

## <a name="detect-objects"></a><span data-ttu-id="7720e-404">개체 검색</span><span class="sxs-lookup"><span data-stu-id="7720e-404">Detect objects</span></span>

<span data-ttu-id="7720e-405">이제 모든 설치가 완료되었으므로 일부 개체를 검색해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-405">Now that all of the setup is complete, it's time to detect some objects.</span></span> <span data-ttu-id="7720e-406">먼저 *Program.cs* 클래스에서 채점자 및 파서에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-406">Start off by adding references to the scorer and parser in your *Program.cs* class.</span></span>

[!code-csharp [ReferenceScorerParser](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L8-L9)]

### <a name="score-and-parse-model-outputs"></a><span data-ttu-id="7720e-407">채점 및 구문 분석 모델 출력</span><span class="sxs-lookup"><span data-stu-id="7720e-407">Score and parse model outputs</span></span>

<span data-ttu-id="7720e-408">*Program.cs* 클래스의 `Main` 메서드에서 try-catch 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-408">Inside the `Main` method of your *Program.cs* class, add a try-catch statement.</span></span>

```csharp
try
{

}
catch (Exception ex)
{
    Console.WriteLine(ex.ToString());
}
```

<span data-ttu-id="7720e-409">`try` 블록에서 개체 검색 로직을 구현하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-409">Inside of the `try` block, start implementing the object detection logic.</span></span> <span data-ttu-id="7720e-410">먼저 데이터를 [`IDataView`](xref:Microsoft.ML.IDataView)에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-410">First, load the data into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

[!code-csharp [LoadData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L29-L30)]

<span data-ttu-id="7720e-411">그런 다음 `OnnxModelScorer`의 인스턴스를 만들고 이를 사용하여 로드된 데이터를 채점합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-411">Then, create an instance of `OnnxModelScorer` and use it to score the loaded data.</span></span>

[!code-csharp [ScoreData](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L33-L36)]

<span data-ttu-id="7720e-412">이제 후처리 단계가 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-412">Now it's time for the post-processing step.</span></span> <span data-ttu-id="7720e-413">`YoloOutputParser`의 인스턴스를 만들고 이를 사용하여 모델 출력을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-413">Create an instance of `YoloOutputParser` and use it to process the model output.</span></span>

[!code-csharp [ParsePredictions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L39-L44)]

<span data-ttu-id="7720e-414">모델 출력을 처리하고 나면 이미지에 경계 상자를 그릴 차례입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-414">Once the model output has been processed, it's time to draw the bounding boxes on the images.</span></span>

### <a name="visualize-predictions"></a><span data-ttu-id="7720e-415">예측 시각화</span><span class="sxs-lookup"><span data-stu-id="7720e-415">Visualize predictions</span></span>

<span data-ttu-id="7720e-416">모델에서 이미지를 채점하고 출력이 처리되고 나면 이미지에 경계 상자를 그려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-416">After the model has scored the images and the outputs have been processed, the bounding boxes have to be drawn on the image.</span></span> <span data-ttu-id="7720e-417">그렇게 하려면 `DrawBoundingBox` 메서드를 *Program.cs*의 `GetAbsolutePath` 메서드 아래 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-417">To do so, add a method called `DrawBoundingBox` below the `GetAbsolutePath` method inside of *Program.cs*.</span></span>

```csharp
private static void DrawBoundingBox(string inputImageLocation, string outputImageLocation, string imageName, IList<YoloBoundingBox> filteredBoundingBoxes)
{

}
```

<span data-ttu-id="7720e-418">먼저 이미지를 로드하고 `DrawBoundingBox` 메서드에서 높이 및 너비 차원을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-418">First, load the image and get the height and width dimensions in the `DrawBoundingBox` method.</span></span>

[!code-csharp [LoadImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L78-L81)]

<span data-ttu-id="7720e-419">그런 다음 모델에서 검색한 각 경계 상자를 반복하는 for-each 루프를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-419">Then, create a for-each loop to iterate over each of the bounding boxes detected by the model.</span></span>

```csharp
foreach (var box in filteredBoundingBoxes)
{

}
```

<span data-ttu-id="7720e-420">for-each 루프 내에서 경계 상자의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-420">Inside of the for-each loop, get the dimensions of the bounding box.</span></span>

[!code-csharp [GetBBoxDimensions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L86-L89)]

<span data-ttu-id="7720e-421">경계 상자의 크기는 `416 x 416`의 모델 입력에 해당하므로 경계 상자 크기를 이미지의 실제 크기와 일치하도록 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-421">Because the dimensions of the bounding box correspond to the model input of `416 x 416`, scale the bounding box dimensions to match the actual size of the image.</span></span>

[!code-csharp [ScaleImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L92-L95)]

<span data-ttu-id="7720e-422">그런 다음 각 경계 상자 위에 표시될 텍스트의 템플릿을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-422">Then, define a template for text that will appear above each bounding box.</span></span> <span data-ttu-id="7720e-423">텍스트에는 각 경계 상자 내의 개체 클래스와 신뢰도가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-423">The text will contain the class of the object inside of the respective bounding box as well as the confidence.</span></span>

[!code-csharp [DefineBBoxText](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L98)]

<span data-ttu-id="7720e-424">이미지를 그리려면 [`Graphics`](xref:System.Drawing.Graphics) 개체로 변환하세요.</span><span class="sxs-lookup"><span data-stu-id="7720e-424">In order to draw on the image, convert it to a [`Graphics`](xref:System.Drawing.Graphics) object.</span></span>

```csharp
using (Graphics thumbnailGraphic = Graphics.FromImage(image))
{

}
```

<span data-ttu-id="7720e-425">`using` 코드 블록에서 그래픽의 [`Graphics`](xref:System.Drawing.Graphics) 개체 설정을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-425">Inside the `using` code block, tune the graphic's [`Graphics`](xref:System.Drawing.Graphics) object settings.</span></span>

[!code-csharp [TuneGraphicSettings](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L102-L104)]

<span data-ttu-id="7720e-426">그런 다음 텍스트 및 경계 상자의 글꼴 및 색 옵션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-426">Below that, set the font and color options for the text and bounding box.</span></span>

[!code-csharp [SetColorOptions](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L106-L114)]

<span data-ttu-id="7720e-427">[`FillRectangle`](xref:System.Drawing.Graphics.FillRectangle*) 메서드를 사용하여 텍스트를 포함하도록 경계 상자 위에 직사각형을 만들어 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-427">Create and fill a rectangle above the bounding box to contain the text using the [`FillRectangle`](xref:System.Drawing.Graphics.FillRectangle*) method.</span></span> <span data-ttu-id="7720e-428">그러면 텍스트가 대비되어 가독성을 높이는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-428">This will help contrast the text and improve readability.</span></span>

[!code-csharp [DrawTextBackground](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L117)]

<span data-ttu-id="7720e-429">그런 다음 [`DrawString`](xref:System.Drawing.Graphics.DrawString*) 및 [`DrawRectangle`](xref:System.Drawing.Graphics.DrawRectangle*) 메서드를 사용하여 이미지에 텍스트와 경계 상자를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-429">Then, Draw the text and bounding box on the image using the [`DrawString`](xref:System.Drawing.Graphics.DrawString*) and [`DrawRectangle`](xref:System.Drawing.Graphics.DrawRectangle*) methods.</span></span>

[!code-csharp [DrawClassAndBBox](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L118-L121)]

<span data-ttu-id="7720e-430">for-each 루프 외부에서 `outputDirectory`에 이미지를 저장하는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-430">Outside of the for-each loop, add code to save the images in the `outputDirectory`.</span></span>

[!code-csharp [SaveImage](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L125-L130)]

<span data-ttu-id="7720e-431">런타임 시 애플리케이션이 예상대로 예측하는지에 대한 추가 피드백을 위해 `LogDetectedObjects` 메서드를 *Program.cs* 파일의 `DrawBoundingBox` 메서드 아래 추가하여 검색된 개체를 콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-431">For additional feedback that the application is making predictions as expected at runtime, add a method called `LogDetectedObjects` below the `DrawBoundingBox` method in the *Program.cs* file to output the detected objects to the console.</span></span>

[!code-csharp [LogOutputs](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L133-L143)]

<span data-ttu-id="7720e-432">이제 예측에서 시각적 피드백을 만드는 도우미 메서드가 있으므로 채점된 각 이미지를 반복하는 for 루프를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-432">Now that you have helper methods to create visual feedback from the predictions, add a for-loop to iterate over each of the scored images.</span></span>

```csharp
for (var i = 0; i < images.Count(); i++)
{

}
```

<span data-ttu-id="7720e-433">for 루프 내에서 이미지 파일의 이름과 연결된 경계 상자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-433">Inside of the for-loop, get the name of the image file and the bounding boxes associated with it.</span></span>

[!code-csharp [GetImageFileName](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L49-L50)]

<span data-ttu-id="7720e-434">그런 다음 `DrawBoundingBox` 메서드를 사용하여 이미지에 경계 상자를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-434">Below that, use the `DrawBoundingBox` method to draw the bounding boxes on the image.</span></span>

[!code-csharp [DrawBBoxes](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L52)]

<span data-ttu-id="7720e-435">마지막으로 `LogDetectedObjects` 메서드를 사용하여 예측을 콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-435">Lastly, use the `LogDetectedObjects` method to output predictions to the console.</span></span>

[!code-csharp [LogPredictionsOutput](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L54)]

<span data-ttu-id="7720e-436">try-catch 문 다음에 프로세스 실행이 완료되었음을 나타내는 추가 로직을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-436">After the try-catch statement, add additional logic to indicate the process is done running.</span></span>

[!code-csharp [EndProcessLog](~/machinelearning-samples/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx/ObjectDetectionConsoleApp/Program.cs#L62-L63)]

<span data-ttu-id="7720e-437">정말 간단하죠.</span><span class="sxs-lookup"><span data-stu-id="7720e-437">That's it!</span></span>

## <a name="results"></a><span data-ttu-id="7720e-438">결과</span><span class="sxs-lookup"><span data-stu-id="7720e-438">Results</span></span>

<span data-ttu-id="7720e-439">이전 단계를 수행한 후 콘솔 앱을 실행합니다(Ctrl+F5).</span><span class="sxs-lookup"><span data-stu-id="7720e-439">After following the previous steps, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="7720e-440">다음 출력과 같은 결과가 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-440">Your results should be similar to the following output.</span></span> <span data-ttu-id="7720e-441">경고 또는 처리 메시지가 표시될 수 있지만, 이해하기 쉽도록 이러한 메시지는 다음 결과에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-441">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

```console
=====Identify the objects in the images=====

.....The objects in the image image1.jpg are detected as below....
car and its Confidence score: 0.9697262
car and its Confidence score: 0.6674225
person and its Confidence score: 0.5226039
car and its Confidence score: 0.5224892
car and its Confidence score: 0.4675332

.....The objects in the image image2.jpg are detected as below....
cat and its Confidence score: 0.6461141
cat and its Confidence score: 0.6400049

.....The objects in the image image3.jpg are detected as below....
chair and its Confidence score: 0.840578
chair and its Confidence score: 0.796363
diningtable and its Confidence score: 0.6056048
diningtable and its Confidence score: 0.3737402

.....The objects in the image image4.jpg are detected as below....
dog and its Confidence score: 0.7608147
person and its Confidence score: 0.6321323
dog and its Confidence score: 0.5967442
person and its Confidence score: 0.5730394
person and its Confidence score: 0.5551759

========= End of Process..Hit any Key ========
```

<span data-ttu-id="7720e-442">경계 상자가 있는 이미지를 보려면 `assets/images/output/` 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-442">To see the images with bounding boxes, navigate to the `assets/images/output/` directory.</span></span> <span data-ttu-id="7720e-443">다음은 처리된 이미지 중 하나의 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-443">Below is a sample from one of the processed images.</span></span>

![처리된 거실 이미지 샘플](./media/object-detection-onnx/image3.jpg)

<span data-ttu-id="7720e-445">지금까지</span><span class="sxs-lookup"><span data-stu-id="7720e-445">Congratulations!</span></span> <span data-ttu-id="7720e-446">이제 ML.NET에서 미리 학습된 `ONNX` 모델을 다시 사용하여 개체 검색을 위한 기계 학습 모델을 성공적으로 빌드했습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-446">You've now successfully built a machine learning model for object detection by reusing a pre-trained `ONNX` model in ML.NET.</span></span>

<span data-ttu-id="7720e-447">[dotnet/samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-447">You can find the source code for this tutorial at the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx) repository.</span></span>

<span data-ttu-id="7720e-448">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="7720e-448">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="7720e-449">문제 이해</span><span class="sxs-lookup"><span data-stu-id="7720e-449">Understand the problem</span></span>
> - <span data-ttu-id="7720e-450">ONNX의 개념과 ML.NET에서 작동하는 방식에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="7720e-450">Learn what ONNX is and how it works with ML.NET</span></span>
> - <span data-ttu-id="7720e-451">모델 이해</span><span class="sxs-lookup"><span data-stu-id="7720e-451">Understand the model</span></span>
> - <span data-ttu-id="7720e-452">미리 학습된 모델 다시 사용</span><span class="sxs-lookup"><span data-stu-id="7720e-452">Reuse the pre-trained model</span></span>
> - <span data-ttu-id="7720e-453">로드된 모델을 사용하여 개체 검색</span><span class="sxs-lookup"><span data-stu-id="7720e-453">Detect objects with a loaded model</span></span>

<span data-ttu-id="7720e-454">기계 학습 샘플 GitHub 리포지토리를 확인하여 확장된 개체 검색 샘플을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="7720e-454">Check out the Machine Learning samples GitHub repository to explore an expanded object detection sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="7720e-455">dotnet/machinelearning-samples GitHub 리포지토리</span><span class="sxs-lookup"><span data-stu-id="7720e-455">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/DeepLearning_ObjectDetection_Onnx)
