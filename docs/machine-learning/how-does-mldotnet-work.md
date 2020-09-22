---
title: ML.NET은 무엇이며 어떻게 작동하나요?
description: ML.NET은 온라인 또는 오프라인 시나리오에서 .NET 애플리케이션에 기계 학습을 추가할 수 있는 기능을 제공합니다. 이 기능을 사용하면 ML.NET을 사용하기 위해 네트워크에 연결할 필요 없이 애플리케이션에 사용 가능한 데이터를 사용하여 자동 예측할 수 있습니다. 이 문서에서는 ML.NET에서 기계 학습의 기본 사항을 설명합니다.
ms.date: 11/5/2019
ms.topic: overview
ms.custom: mvc
ms.openlocfilehash: d9a218e57756ad8b95248193325e902c1798cc37
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679666"
---
# <a name="what-is-mlnet-and-how-does-it-work"></a><span data-ttu-id="d3b9a-105">ML.NET은 무엇이며 어떻게 작동하나요?</span><span class="sxs-lookup"><span data-stu-id="d3b9a-105">What is ML.NET and how does it work?</span></span>

<span data-ttu-id="d3b9a-106">ML.NET은 온라인 또는 오프라인 시나리오에서 .NET 애플리케이션에 기계 학습을 추가할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-106">ML.NET gives you the ability to add machine learning to .NET applications, in either online or offline scenarios.</span></span> <span data-ttu-id="d3b9a-107">이 기능을 사용하여 애플리케이션에 사용 가능한 데이터를 사용하여 자동 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-107">With this capability, you can make automatic predictions using the data available to your application.</span></span> <span data-ttu-id="d3b9a-108">기계 학습 애플리케이션은 명시적으로 프로그래밍하지 않아도 데이터의 패턴을 사용하여 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-108">Machine learning applications make use of patterns in the data to make predictions rather than needing to be explicitly programmed.</span></span>

<span data-ttu-id="d3b9a-109">ML.NET의 핵심은 기계 학습 **모델**입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-109">Central to ML.NET is a machine learning **model**.</span></span> <span data-ttu-id="d3b9a-110">모델은 입력 데이터를 예측으로 변환하는 데 필요한 단계를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-110">The model specifies the steps needed to transform your input data into a prediction.</span></span> <span data-ttu-id="d3b9a-111">ML.NET를 사용하면 알고리즘을 지정하여 사용자 지정 모델을 학습하거나 미리 학습된 TensorFlow 및 ONNX 모델을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-111">With ML.NET, you can train a custom model by specifying an algorithm, or you can import pre-trained TensorFlow and ONNX models.</span></span>

<span data-ttu-id="d3b9a-112">모델이 있는 경우, 애플리케이션에 이를 추가하여 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-112">Once you have a model, you can add it to your application to make the predictions.</span></span>

<span data-ttu-id="d3b9a-113">ML.NET은 .NET Core를 사용하여 Windows, Linux 및 macOS에서 실행되거나 .NET Framework를 사용하여 Windows를 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-113">ML.NET runs on Windows, Linux, and macOS using .NET Core, or Windows using .NET Framework.</span></span> <span data-ttu-id="d3b9a-114">64비트는 모든 플랫폼에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-114">64 bit is supported on all platforms.</span></span> <span data-ttu-id="d3b9a-115">32비트는 TensorFlow, LightGBM 및 ONNX 관련 기능을 제외하고 Windows에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-115">32 bit is supported on Windows, except for TensorFlow, LightGBM, and ONNX-related functionality.</span></span>

<span data-ttu-id="d3b9a-116">ML.NET을 사용하여 수행할 수 있는 예측 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-116">Examples of the type of predictions that you can make with ML.NET:</span></span>

|||
|-|-|
|<span data-ttu-id="d3b9a-117">분류/범주화</span><span class="sxs-lookup"><span data-stu-id="d3b9a-117">Classification/Categorization</span></span>|<span data-ttu-id="d3b9a-118">고객 피드백을 긍정과 부정 범주로 자동 구분</span><span class="sxs-lookup"><span data-stu-id="d3b9a-118">Automatically divide customer feedback into positive and negative categories</span></span>|
|<span data-ttu-id="d3b9a-119">재발/연속 값 예측</span><span class="sxs-lookup"><span data-stu-id="d3b9a-119">Regression/Predict continuous values</span></span>|<span data-ttu-id="d3b9a-120">크기 및 위치에 따라 주택 가격 예측</span><span class="sxs-lookup"><span data-stu-id="d3b9a-120">Predict the price of houses based on size and location</span></span>|
|<span data-ttu-id="d3b9a-121">변칙 검색</span><span class="sxs-lookup"><span data-stu-id="d3b9a-121">Anomaly Detection</span></span>|<span data-ttu-id="d3b9a-122">사기성 은행 거래 검색</span><span class="sxs-lookup"><span data-stu-id="d3b9a-122">Detect fraudulent banking transactions</span></span> |
|<span data-ttu-id="d3b9a-123">권장 사항</span><span class="sxs-lookup"><span data-stu-id="d3b9a-123">Recommendations</span></span>|<span data-ttu-id="d3b9a-124">이전 구매 내역에 기반하여 온라인 구매자가 구매하려는 제품 제안</span><span class="sxs-lookup"><span data-stu-id="d3b9a-124">Suggest products that online shoppers may want to buy, based on their previous purchases</span></span>|
|<span data-ttu-id="d3b9a-125">시계열/순차 데이터</span><span class="sxs-lookup"><span data-stu-id="d3b9a-125">Time series/sequential data</span></span>|<span data-ttu-id="d3b9a-126">날씨/제품 판매 예측</span><span class="sxs-lookup"><span data-stu-id="d3b9a-126">Forecast the weather/product sales</span></span>|
|<span data-ttu-id="d3b9a-127">이미지 분류</span><span class="sxs-lookup"><span data-stu-id="d3b9a-127">Image classification</span></span>|<span data-ttu-id="d3b9a-128">의료 이미지에서 병리학 분류</span><span class="sxs-lookup"><span data-stu-id="d3b9a-128">Categorize pathologies in medical images</span></span>|

## <a name="hello-mlnet-world"></a><span data-ttu-id="d3b9a-129">Hello ML.NET World</span><span class="sxs-lookup"><span data-stu-id="d3b9a-129">Hello ML.NET World</span></span>

<span data-ttu-id="d3b9a-130">다음 코드 조각의 코드는 가장 단순한 ML.NET 애플리케이션을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-130">The code in the following snippet demonstrates the simplest ML.NET application.</span></span> <span data-ttu-id="d3b9a-131">이 예제에서는 집 크기 및 가격 데이터를 사용하여 주택 가격을 예측하도록 선형 회귀 모델을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-131">This example constructs a linear regression model to predict house prices using house size and price data.</span></span>

 ```csharp
    using System;
    using Microsoft.ML;
    using Microsoft.ML.Data;

    class Program
    {
        public class HouseData
        {
            public float Size { get; set; }
            public float Price { get; set; }
        }

        public class Prediction
        {
            [ColumnName("Score")]
            public float Price { get; set; }
        }

        static void Main(string[] args)
        {
            MLContext mlContext = new MLContext();

            // 1. Import or create training data
            HouseData[] houseData = {
                new HouseData() { Size = 1.1F, Price = 1.2F },
                new HouseData() { Size = 1.9F, Price = 2.3F },
                new HouseData() { Size = 2.8F, Price = 3.0F },
                new HouseData() { Size = 3.4F, Price = 3.7F } };
            IDataView trainingData = mlContext.Data.LoadFromEnumerable(houseData);

            // 2. Specify data preparation and model training pipeline
            var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
                .Append(mlContext.Regression.Trainers.Sdca(labelColumnName: "Price", maximumNumberOfIterations: 100));

            // 3. Train model
            var model = pipeline.Fit(trainingData);

            // 4. Make a prediction
            var size = new HouseData() { Size = 2.5F };
            var price = mlContext.Model.CreatePredictionEngine<HouseData, Prediction>(model).Predict(size);

            Console.WriteLine($"Predicted price for size: {size.Size*1000} sq ft= {price.Price*100:C}k");

            // Predicted price for size: 2500 sq ft= $261.98k
        }
    }
```

## <a name="code-workflow"></a><span data-ttu-id="d3b9a-132">코드 워크플로</span><span class="sxs-lookup"><span data-stu-id="d3b9a-132">Code workflow</span></span>

<span data-ttu-id="d3b9a-133">다음 다이어그램은 반복적인 모델 개발 프로세스뿐만 아니라 애플리케이션 코드 구조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-133">The following diagram represents the application code structure, as well as the iterative process of model development:</span></span>

- <span data-ttu-id="d3b9a-134">학습 데이터를 수집하여 **IDataView** 개체로 로드</span><span class="sxs-lookup"><span data-stu-id="d3b9a-134">Collect and load training data into an **IDataView** object</span></span>
- <span data-ttu-id="d3b9a-135">기능을 추출하고 기계 학습 알고리즘을 적용할 작업 파이프라인 지정</span><span class="sxs-lookup"><span data-stu-id="d3b9a-135">Specify a pipeline of operations to extract features and apply a machine learning algorithm</span></span>
- <span data-ttu-id="d3b9a-136">파이프라인에서 **Fit()** 를 호출하여 모델 학습</span><span class="sxs-lookup"><span data-stu-id="d3b9a-136">Train a model by calling **Fit()** on the pipeline</span></span>
- <span data-ttu-id="d3b9a-137">모델을 평가하고 반복하여 개선</span><span class="sxs-lookup"><span data-stu-id="d3b9a-137">Evaluate the model and iterate to improve</span></span>
- <span data-ttu-id="d3b9a-138">애플리케이션에서 사용할 수 있도록 모델을 이진 형식으로 저장</span><span class="sxs-lookup"><span data-stu-id="d3b9a-138">Save the model into binary format, for use in an application</span></span>
- <span data-ttu-id="d3b9a-139">모델을 **ITransformer** 개체로 다시 로드</span><span class="sxs-lookup"><span data-stu-id="d3b9a-139">Load the model back into an **ITransformer** object</span></span>
- <span data-ttu-id="d3b9a-140">**CreatePredictionEngine.Predict()** 를 호출하여 예측</span><span class="sxs-lookup"><span data-stu-id="d3b9a-140">Make predictions by calling **CreatePredictionEngine.Predict()**</span></span>

![데이터 생성, 파이프라인 개발, 모델 학습, 모델 평가 및 모델 사용에 대한 구성 요소를 포함한 ML.NET 애플리케이션 개발 흐름](./media/mldotnet-annotated-workflow.png)

<span data-ttu-id="d3b9a-142">이러한 개념을 좀 더 깊이 살펴 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-142">Let's dig a little deeper into those concepts.</span></span>

## <a name="machine-learning-model"></a><span data-ttu-id="d3b9a-143">기계 학습 모델</span><span class="sxs-lookup"><span data-stu-id="d3b9a-143">Machine learning model</span></span>

<span data-ttu-id="d3b9a-144">ML.NET 모델은 예측된 출력에 도달하기 위해 입력 데이터에서 수행할 변형이 포함된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-144">An ML.NET model is an object that contains transformations to perform on your input data to arrive at the predicted output.</span></span>

### <a name="basic"></a><span data-ttu-id="d3b9a-145">Basic</span><span class="sxs-lookup"><span data-stu-id="d3b9a-145">Basic</span></span>

<span data-ttu-id="d3b9a-146">가장 기본적인 모델은 위의 주택 가격 예에서와 같이 하나의 지속적인 수량이 다른 것과 비례하는 2차원 선형 회귀입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-146">The most basic model is two-dimensional linear regression, where one continuous quantity is proportional to another, as in the house price example above.</span></span>

![편차와 가중치 매개 변수가 포함된 선형 회귀 모델](./media/linear-regression-model.svg)

<span data-ttu-id="d3b9a-148">모델은 단순히 $Price = b + Size \* w$입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-148">The model is simply: $Price = b + Size \* w$.</span></span> <span data-ttu-id="d3b9a-149">매개 변수 $b$ 및 $w$는 쌍 세트(크기, 가격)에 줄을 맞춰 추정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-149">The parameters $b$ and $w$ are estimated by fitting a line on a set of (size, price) pairs.</span></span> <span data-ttu-id="d3b9a-150">모델의 매개 변수를 찾는 데 사용되는 데이터를 **학습 데이터**라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-150">The data used to find the parameters of the model is called **training data**.</span></span> <span data-ttu-id="d3b9a-151">이 기계 학습 모델의 입력을 **특성(feature)** 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-151">The inputs of a machine learning model are called **features**.</span></span> <span data-ttu-id="d3b9a-152">이 예제에서는 $Size$가 유일한 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-152">In this example, $Size$ is the only feature.</span></span> <span data-ttu-id="d3b9a-153">기계 학습 모델을 학습하는 데 사용하는 실측 자료(ground-truth) 값은 **레이블**이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-153">The ground-truth values used to train a machine learning model are called **labels**.</span></span> <span data-ttu-id="d3b9a-154">여기에서는 학습 데이터 세트의 $Price$ 값이 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-154">Here, the $Price$ values in the training data set are the labels.</span></span>

### <a name="more-complex"></a><span data-ttu-id="d3b9a-155">더 복잡한</span><span class="sxs-lookup"><span data-stu-id="d3b9a-155">More complex</span></span>

<span data-ttu-id="d3b9a-156">더 복잡한 모델은 거래 텍스트 설명을 사용하여 금융 거래를 범주로 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-156">A more complex model classifies financial transactions into categories using the transaction text description.</span></span>

<span data-ttu-id="d3b9a-157">각 거래 설명은 중복되는 단어와 문자를 제거하고 단어와 문자 조합을 계산하여 일련의 기능으로 세분화됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-157">Each transaction description is broken down into a set of features by removing redundant words and characters, and counting word and character combinations.</span></span> <span data-ttu-id="d3b9a-158">기능 집합은 학습 데이터에서 범주 집합에 기반하여 선형 모델을 학습하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-158">The feature set is used to train a linear model based on the set of categories in the training data.</span></span> <span data-ttu-id="d3b9a-159">새로운 설명이 학습 집합의 설명과 유사할수록 동일한 범주에 할당될 가능성이 커집니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-159">The more similar a new description is to the ones in the training set, the more likely it will be assigned to the same category.</span></span>

![텍스트 분류 모델](./media/text-classification-model.svg)

<span data-ttu-id="d3b9a-161">주택 가격 책정 모델 및 텍스트 분류 모델 둘 다 **선형** 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-161">Both the house price model and the text classification model are **linear** models.</span></span> <span data-ttu-id="d3b9a-162">데이터의 성격과 해결하려는 문제에 따라, **결정 트리**, **일반화된 부가** 모델 등을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-162">Depending on the nature of your data and the problem you are solving, you can also use **decision tree** models, **generalized additive** models, and others.</span></span> <span data-ttu-id="d3b9a-163">[작업](./resources/tasks.md)에서 모델에 대해 더 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-163">You can find out more about the models in [Tasks](./resources/tasks.md).</span></span>

## <a name="data-preparation"></a><span data-ttu-id="d3b9a-164">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="d3b9a-164">Data preparation</span></span>

<span data-ttu-id="d3b9a-165">대부분의 경우에서 사용자가 가지고 있는 사용 가능한 데이터는 기계 학습 모델을 학습하기 위해 직접 사용하기에는 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-165">In most cases, the data that you have available isn't suitable to be used directly to train a machine learning model.</span></span> <span data-ttu-id="d3b9a-166">원시 데이터는 준비하거나 사전 처리되어야 모델의 매개 변수를 찾기 위해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-166">The raw data needs to be prepared, or pre-processed, before it can be used to find the parameters of your model.</span></span> <span data-ttu-id="d3b9a-167">데이터를 문자열 값에서 숫자 표현으로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-167">Your data may need to be converted from string values to a numerical representation.</span></span> <span data-ttu-id="d3b9a-168">사용자의 입력 데이터에서 중복되는 정보가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-168">You might have redundant information in your input data.</span></span> <span data-ttu-id="d3b9a-169">입력 데이터의 크기를 축소 또는 확장해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-169">You may need to reduce or expand the dimensions of your input data.</span></span> <span data-ttu-id="d3b9a-170">데이터를 정규화 또는 크기 조정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-170">Your data might need to be normalized or scaled.</span></span>

<span data-ttu-id="d3b9a-171">[ML.NET 자습서](./tutorials/index.md)는 특정 기계 학습 작업에 사용되는 텍스트, 이미지, 숫자 및 시계열 데이터에 대한 다른 데이터 처리 파이프라인에 대해 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-171">The [ML.NET tutorials](./tutorials/index.md) teach you about different data processing pipelines for text, image, numerical, and time-series data used for specific machine learning tasks.</span></span>

<span data-ttu-id="d3b9a-172">[데이터 준비 방법](./how-to-guides/prepare-data-ml-net.md)은 데이터 준비를 더 일반적으로 적용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-172">[How to prepare your data](./how-to-guides/prepare-data-ml-net.md) shows you how to apply data preparation more generally.</span></span>

<span data-ttu-id="d3b9a-173">리소스 섹션에서 모든 [사용 가능한 변환](./resources/transforms.md)의 부록을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-173">You can find an appendix of all of the [available transformations](./resources/transforms.md) in the resources section.</span></span>

## <a name="model-evaluation"></a><span data-ttu-id="d3b9a-174">모델 평가</span><span class="sxs-lookup"><span data-stu-id="d3b9a-174">Model evaluation</span></span>

<span data-ttu-id="d3b9a-175">모델을 학습한 후에는 미래의 예측을 얼마나 잘 할지 어떻게 알까요?</span><span class="sxs-lookup"><span data-stu-id="d3b9a-175">Once you have trained your model, how do you know how well it will make future predictions?</span></span> <span data-ttu-id="d3b9a-176">ML.NET를 사용하여 새로운 테스트 데이터를 기준으로 모델을 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-176">With ML.NET, you can evaluate your model against some new test data.</span></span>

<span data-ttu-id="d3b9a-177">기계 학습 작업의 각 유형에는 테스트 데이터 세트를 기준으로 모델의 정확성 및 정밀도를 평가하는 데 사용하는 메트릭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-177">Each type of machine learning task has metrics used to evaluate the accuracy and precision of the model against the test data set.</span></span>

<span data-ttu-id="d3b9a-178">주택 가격 예의 경우 **회귀** 작업을 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-178">For our house price example, we used the **Regression** task.</span></span> <span data-ttu-id="d3b9a-179">모델을 평가하려면 원래 샘플에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-179">To evaluate the model, add the following code to the original sample.</span></span>

```csharp
        HouseData[] testHouseData =
        {
            new HouseData() { Size = 1.1F, Price = 0.98F },
            new HouseData() { Size = 1.9F, Price = 2.1F },
            new HouseData() { Size = 2.8F, Price = 2.9F },
            new HouseData() { Size = 3.4F, Price = 3.6F }
        };

        var testHouseDataView = mlContext.Data.LoadFromEnumerable(testHouseData);
        var testPriceDataView = model.Transform(testHouseDataView);

        var metrics = mlContext.Regression.Evaluate(testPriceDataView, labelColumnName: "Price");

        Console.WriteLine($"R^2: {metrics.RSquared:0.##}");
        Console.WriteLine($"RMS error: {metrics.RootMeanSquaredError:0.##}");

        // R^2: 0.96
        // RMS error: 0.19
```

<span data-ttu-id="d3b9a-180">평가 메트릭은 오류가 낮은 수준이며 예측한 출력과 테스트 출력 간 상관 관계가 높다는 것을 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-180">The evaluation metrics tell you that the error is low-ish, and that correlation between the predicted output and the test output is high.</span></span> <span data-ttu-id="d3b9a-181">이 과정은 아주 쉽습니다!</span><span class="sxs-lookup"><span data-stu-id="d3b9a-181">That was easy!</span></span> <span data-ttu-id="d3b9a-182">실제 사례에서는 훌륭한 모델 메트릭을 얻는 데 더 많은 튜닝이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-182">In real examples, it takes more tuning to achieve good model metrics.</span></span>

## <a name="mlnet-architecture"></a><span data-ttu-id="d3b9a-183">ML.NET 아키텍처</span><span class="sxs-lookup"><span data-stu-id="d3b9a-183">ML.NET architecture</span></span>

<span data-ttu-id="d3b9a-184">이 섹션에서는 ML.NET의 아키텍처 패턴을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-184">In this section, we go through the architectural patterns of ML.NET.</span></span> <span data-ttu-id="d3b9a-185">숙련된 .NET 개발자라면 이러한 패턴의 일부는 익숙하고 일부는 덜 익숙해집니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-185">If you are an experienced .NET developer, some of these patterns will be familiar to you, and some will be less familiar.</span></span> <span data-ttu-id="d3b9a-186">자세히 살펴보는 동안 긴장을 놓지 마세요!</span><span class="sxs-lookup"><span data-stu-id="d3b9a-186">Hold tight, while we dive in!</span></span>

<span data-ttu-id="d3b9a-187">ML.NET 애플리케이션은 <xref:Microsoft.ML.MLContext> 개체로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-187">An ML.NET application starts with an <xref:Microsoft.ML.MLContext> object.</span></span> <span data-ttu-id="d3b9a-188">이 싱글톤 개체는 **카탈로그**를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-188">This singleton object contains **catalogs**.</span></span> <span data-ttu-id="d3b9a-189">카탈로그는 데이터 로드 및 저장, 변환, 트레이너, 모델 작동 구성 요소를 위한 팩터리입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-189">A catalog is a factory for data loading and saving, transforms, trainers, and model operation components.</span></span> <span data-ttu-id="d3b9a-190">각 카탈로그 개체마다 다른 유형의 구성 요소를 만드는 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-190">Each catalog object has methods to create the different types of components:</span></span>

|||||
|-|-|-|-|
|<span data-ttu-id="d3b9a-191">데이터 로드 및 저장</span><span class="sxs-lookup"><span data-stu-id="d3b9a-191">Data loading and saving</span></span>||<xref:Microsoft.ML.DataOperationsCatalog>||
|<span data-ttu-id="d3b9a-192">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="d3b9a-192">Data preparation</span></span>||<xref:Microsoft.ML.TransformsCatalog>||
|<span data-ttu-id="d3b9a-193">학습 알고리즘</span><span class="sxs-lookup"><span data-stu-id="d3b9a-193">Training algorithms</span></span>|<span data-ttu-id="d3b9a-194">이진 분류</span><span class="sxs-lookup"><span data-stu-id="d3b9a-194">Binary classification</span></span>|<xref:Microsoft.ML.BinaryClassificationCatalog>||
||<span data-ttu-id="d3b9a-195">다중 클래스 분류</span><span class="sxs-lookup"><span data-stu-id="d3b9a-195">Multiclass classification</span></span>|<xref:Microsoft.ML.MulticlassClassificationCatalog>||
||<span data-ttu-id="d3b9a-196">변칙 검색</span><span class="sxs-lookup"><span data-stu-id="d3b9a-196">Anomaly detection</span></span>|<xref:Microsoft.ML.AnomalyDetectionCatalog>||
||<span data-ttu-id="d3b9a-197">클러스터링</span><span class="sxs-lookup"><span data-stu-id="d3b9a-197">Clustering</span></span>|<xref:Microsoft.ML.ClusteringCatalog>||
||<span data-ttu-id="d3b9a-198">예측</span><span class="sxs-lookup"><span data-stu-id="d3b9a-198">Forecasting</span></span>|<xref:Microsoft.ML.ForecastingCatalog>||
||<span data-ttu-id="d3b9a-199">순위 지정</span><span class="sxs-lookup"><span data-stu-id="d3b9a-199">Ranking</span></span>|<xref:Microsoft.ML.RankingCatalog>||
||<span data-ttu-id="d3b9a-200">재발</span><span class="sxs-lookup"><span data-stu-id="d3b9a-200">Regression</span></span>|<xref:Microsoft.ML.RegressionCatalog>||
||<span data-ttu-id="d3b9a-201">권장</span><span class="sxs-lookup"><span data-stu-id="d3b9a-201">Recommendation</span></span>|<xref:Microsoft.ML.RecommendationCatalog>|<span data-ttu-id="d3b9a-202">`Microsoft.ML.Recommender` NuGet 패키지 추가</span><span class="sxs-lookup"><span data-stu-id="d3b9a-202">add the `Microsoft.ML.Recommender` NuGet package</span></span>|
||<span data-ttu-id="d3b9a-203">TimeSeries</span><span class="sxs-lookup"><span data-stu-id="d3b9a-203">TimeSeries</span></span>|<xref:Microsoft.ML.TimeSeriesCatalog>|<span data-ttu-id="d3b9a-204">`Microsoft.ML.TimeSeries` NuGet 패키지 추가</span><span class="sxs-lookup"><span data-stu-id="d3b9a-204">add the `Microsoft.ML.TimeSeries` NuGet package</span></span>|
|<span data-ttu-id="d3b9a-205">모델 사용</span><span class="sxs-lookup"><span data-stu-id="d3b9a-205">Model usage</span></span> ||<xref:Microsoft.ML.ModelOperationsCatalog>||

<span data-ttu-id="d3b9a-206">위의 각 범주에서 만들기 메서드로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-206">You can navigate to the creation methods in each of the above categories.</span></span> <span data-ttu-id="d3b9a-207">카탈로그는 Visual Studio를 사용하여 IntelliSense를 통해 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-207">Using Visual Studio, the catalogs show up via IntelliSense.</span></span>

   ![회귀 트레이너용 Intellisense](./media/catalog-intellisense.png)

### <a name="build-the-pipeline"></a><span data-ttu-id="d3b9a-209">파이프라인 빌드</span><span class="sxs-lookup"><span data-stu-id="d3b9a-209">Build the pipeline</span></span>

<span data-ttu-id="d3b9a-210">각 카탈로그 내에는 확장 메서드의 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-210">Inside each catalog is a set of extension methods.</span></span> <span data-ttu-id="d3b9a-211">확장 메서드를 사용하여 학습 파이프라인을 만드는 방법을 살펴 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-211">Let's look at how extension methods are used to create a training pipeline.</span></span>

```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
        .Append(mlContext.Regression.Trainers.Sdca(labelColumnName: "Price", maximumNumberOfIterations: 100));
```

<span data-ttu-id="d3b9a-212">코드 조각에서 `Concatenate` 및 `Sdca`는 카탈로그에 있는 두 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-212">In the snippet, `Concatenate` and `Sdca` are both methods in the catalog.</span></span> <span data-ttu-id="d3b9a-213">이러한 메서드는 파이프라인에 연결된 [IEstimator](xref:Microsoft.ML.IEstimator%601) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-213">They each create an [IEstimator](xref:Microsoft.ML.IEstimator%601) object that is appended to the pipeline.</span></span>

<span data-ttu-id="d3b9a-214">이 시점에서는 개체만 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-214">At this point, the objects are created only.</span></span> <span data-ttu-id="d3b9a-215">어떠한 실행도 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-215">No execution has happened.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="d3b9a-216">모델 학습</span><span class="sxs-lookup"><span data-stu-id="d3b9a-216">Train the model</span></span>

<span data-ttu-id="d3b9a-217">파이프라인에서 개체가 만들어지면 모델을 학습하는 데 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-217">Once the objects in the pipeline have been created, data can be used to train the model.</span></span>

```csharp
    var model = pipeline.Fit(trainingData);
```

<span data-ttu-id="d3b9a-218">`Fit()` 호출 시 입력 학습 데이터를 사용하여 모델의 매개 변수를 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-218">Calling `Fit()` uses the input training data to estimate the parameters of the model.</span></span> <span data-ttu-id="d3b9a-219">이를 모델 학습이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-219">This is known as training the model.</span></span> <span data-ttu-id="d3b9a-220">단, 위의 선형 회귀 모델에서는 두 가지 모델 매개 변수, 즉 **편차**와 **가중치**가 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-220">Remember, the linear regression model above had two model parameters: **bias** and **weight**.</span></span> <span data-ttu-id="d3b9a-221">`Fit()` 호출 후 매개 변수의 값이 알려집니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-221">After the `Fit()` call, the values of the parameters are known.</span></span> <span data-ttu-id="d3b9a-222">대부분 모델에는 이것보다 더 많은 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-222">Most models will have many more parameters than this.</span></span>

<span data-ttu-id="d3b9a-223">[모델 학습 방법](./how-to-guides/train-machine-learning-model-ml-net.md)에서 모델 학습에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-223">You can learn more about model training in [How to train your model](./how-to-guides/train-machine-learning-model-ml-net.md).</span></span>

<span data-ttu-id="d3b9a-224">결과 모델 개체는 <xref:Microsoft.ML.ITransformer> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-224">The resulting model object implements the <xref:Microsoft.ML.ITransformer> interface.</span></span> <span data-ttu-id="d3b9a-225">즉, 모델은 입력 데이터를 예측으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-225">That is, the model transforms input data into predictions.</span></span>

```csharp
   IDataView predictions = model.Transform(inputData);
```

### <a name="use-the-model"></a><span data-ttu-id="d3b9a-226">모델 사용</span><span class="sxs-lookup"><span data-stu-id="d3b9a-226">Use the model</span></span>

<span data-ttu-id="d3b9a-227">입력 데이터를 대량의 예측으로 변환하거나 한 번에 하나의 입력을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-227">You can transform input data into predictions in bulk, or one input at a time.</span></span> <span data-ttu-id="d3b9a-228">주택 가격 예에서는 두 가지(모델 평가 목적으로는 대량, 새로운 예측을 하기 위해서는 한 번에 하나씩)를 수행했습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-228">In the house price example, we did both: in bulk for the purpose of evaluating the model, and one at a time to make a new prediction.</span></span> <span data-ttu-id="d3b9a-229">단일 예측하기를 살펴 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-229">Let's look at making single predictions.</span></span>

```csharp
    var size = new HouseData() { Size = 2.5F };
    var predEngine = mlContext.CreatePredictionEngine<HouseData, Prediction>(model);
    var price = predEngine.Predict(size);
```

<span data-ttu-id="d3b9a-230">`CreatePredictionEngine()` 메서드는 입력 클래스 및 출력 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-230">The `CreatePredictionEngine()` method takes an input class and an output class.</span></span> <span data-ttu-id="d3b9a-231">필드 이름 및/또는 코드 특성은 모델 학습 및 예측 중 사용된 데이터 열의 이름을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-231">The field names and/or code attributes determine the names of the data columns used during model training and prediction.</span></span> <span data-ttu-id="d3b9a-232">자세한 내용은 [학습된 모델로 예측](how-to-guides/machine-learning-model-predictions-ml-net.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-232">For more information, see [Make predictions with a trained model](how-to-guides/machine-learning-model-predictions-ml-net.md).</span></span>

### <a name="data-models-and-schema"></a><span data-ttu-id="d3b9a-233">데이터 모델 및 스키마</span><span class="sxs-lookup"><span data-stu-id="d3b9a-233">Data models and schema</span></span>

<span data-ttu-id="d3b9a-234">ML.NET 기계 학습 파이프라인의 핵심에는 [DataView](xref:Microsoft.ML.IDataView) 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-234">At the core of an ML.NET machine learning pipeline are [DataView](xref:Microsoft.ML.IDataView) objects.</span></span>

<span data-ttu-id="d3b9a-235">파이프라인의 각 변환에는 입력 스키마(변환 시 입력에서 보길 원하는 데이터 이름, 유형 및 크기)와 출력 스키마(변환 후 해당 변환이 생성하는 데이터 이름, 유형 및 크기)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-235">Each transformation in the pipeline has an input schema (data names, types, and sizes that the transform expects to see on its input); and an output schema (data names, types, and sizes that the transform produces after the transformation).</span></span> <span data-ttu-id="d3b9a-236">다음 문서에서는 [IDataView 인터페이스 및 관련 형식 시스템](https://xadupre.github.io/machinelearningext/mlnetdocs/idataviewtypesystem.html)에 대한 자세한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-236">The following document provides an in-depth explanation of the [IDataView interface and its type system](https://xadupre.github.io/machinelearningext/mlnetdocs/idataviewtypesystem.html).</span></span>

<span data-ttu-id="d3b9a-237">파이프라인에서 하나의 변환으로 인한 출력 스키마가 다음 변환의 입력 스키마와 일치하지 않는 경우 ML.NET은 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-237">If the output schema from one transform in the pipeline doesn't match the input schema of the next transform, ML.NET will throw an exception.</span></span>

<span data-ttu-id="d3b9a-238">데이터 뷰 개체에는 열과 행이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-238">A data view object has columns and rows.</span></span> <span data-ttu-id="d3b9a-239">각 열에는 이름과 유형 및 길이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-239">Each column has a name and a type and a length.</span></span> <span data-ttu-id="d3b9a-240">예: 주택 가격 예의 입력 열에는 **크기**와 **가격**이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-240">For example, the input columns in the house price example are **Size** and **Price**.</span></span> <span data-ttu-id="d3b9a-241">두 가지 유형이며, 벡터 수량이라기 보다는 스칼라 수량입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-241">They are both type and they are scalar quantities rather than vector ones.</span></span>

   ![주택 가격 예측 데이터가 있는 ML.NET 데이터 뷰 예제](./media/ml-net-dataview.png)

<span data-ttu-id="d3b9a-243">모든 ML.NET 알고리즘은 벡터인 입력 열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-243">All ML.NET algorithms look for an input column that is a vector.</span></span> <span data-ttu-id="d3b9a-244">기본적으로 이 벡터 열은 **특성(feature)** 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-244">By default this vector column is called **Features**.</span></span> <span data-ttu-id="d3b9a-245">이것이 바로 주택 가격 예제에서 **Features**이라고 하는 새 열로 **크기** 열을 연관시킨 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-245">This is why we concatenated the **Size** column into a new column called **Features** in our house price example.</span></span>

 ```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
 ```

<span data-ttu-id="d3b9a-246">또한 모든 알고리즘은 예측을 수행한 후 새 열을 만들기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-246">All algorithms also create new columns after they have performed a prediction.</span></span> <span data-ttu-id="d3b9a-247">이러한 새 열의 고정된 이름은 기계 학습 알고리즘의 유형에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-247">The fixed names of these new columns depend on the type of machine learning algorithm.</span></span> <span data-ttu-id="d3b9a-248">회귀 작업의 경우 새 열 중 하나가 **점수**라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-248">For the regression task, one of the new columns is called **Score**.</span></span> <span data-ttu-id="d3b9a-249">이것이 바로 이 이름으로 가격 데이터의 이름을 지정한 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-249">This is why we attributed our price data with this name.</span></span>

```csharp
    public class Prediction
    {
        [ColumnName("Score")]
        public float Price { get; set; }
    }
```

<span data-ttu-id="d3b9a-250">[Machine Learning 작업](resources/tasks.md) 가이드에서 다른 기계 학습 작업의 출력 열에 대해 더 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-250">You can find out more about output columns of different machine learning tasks in the [Machine Learning Tasks](resources/tasks.md) guide.</span></span>

<span data-ttu-id="d3b9a-251">DataView의 중요한 속성은 이들이 **느리게** 평가된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-251">An important property of DataView objects is that they are evaluated **lazily**.</span></span> <span data-ttu-id="d3b9a-252">데이터 뷰는 모델 학습 및 평가, 데이터 예측 중에만 로드되고 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-252">Data views are only loaded and operated on during model training and evaluation, and data prediction.</span></span> <span data-ttu-id="d3b9a-253">ML.NET 애플리케이션을 쓰고 테스트하는 동안에는 Visual Studio 디버거를 사용하여 [미리 보기](xref:Microsoft.ML.DebuggerExtensions.Preview%2A) 메서드를 호출하여 어떠한 데이터 뷰 개체도 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-253">While you are writing and testing your ML.NET application, you can use the Visual Studio debugger to take a peek at any data view object by calling the [Preview](xref:Microsoft.ML.DebuggerExtensions.Preview%2A) method.</span></span>

```csharp
    var debug = testPriceDataView.Preview();
```

<span data-ttu-id="d3b9a-254">디버거에서 `debug` 변수를 보고 내용을 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-254">You can watch the `debug` variable in the debugger and examine its contents.</span></span> <span data-ttu-id="d3b9a-255">성능이 크게 저하되므로 프로덕션 코드에서는 미리 보기 메서드를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-255">Do not use the Preview method in production code, as it significantly degrades performance.</span></span>

### <a name="model-deployment"></a><span data-ttu-id="d3b9a-256">모델 배포</span><span class="sxs-lookup"><span data-stu-id="d3b9a-256">Model Deployment</span></span>

<span data-ttu-id="d3b9a-257">실제 애플리케이션에서 모델 학습과 평가 코드는 예측과 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-257">In real-life applications, your model training and evaluation code will be separate from your prediction.</span></span> <span data-ttu-id="d3b9a-258">사실,이 두 가지 활동은 별도의 팀에서 수행하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-258">In fact, these two activities are often performed by separate teams.</span></span> <span data-ttu-id="d3b9a-259">모델 개발 팀은 예측 애플리케이션에서 사용하기 위해 이 모델을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-259">Your model development team can save the model for use in the prediction application.</span></span>

```csharp
   mlContext.Model.Save(model, trainingData.Schema,"model.zip");
```

## <a name="next-steps"></a><span data-ttu-id="d3b9a-260">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d3b9a-260">Next steps</span></span>

* <span data-ttu-id="d3b9a-261">[자습서](./tutorials/index.md)에서 보다 현실적인 데이터 세트로 다른 기계 학습 작업을 사용하여 애플리케이션을 빌드하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-261">Learn how to build applications using different machine learning tasks with more realistic data sets in the [tutorials](./tutorials/index.md).</span></span>

* <span data-ttu-id="d3b9a-262">[방법 가이드](./how-to-guides/index.md)에서 더 자세히 특정 항목에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-262">Learn about specific topics in more depth in the [How To Guides](./how-to-guides/index.md).</span></span>

* <span data-ttu-id="d3b9a-263">만일 관심이 아주 많다면 [API 참조 문서](../../api/index.md?view=ml-dotnet)를 바로 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b9a-263">If you're super keen, you can dive straight into the [API Reference documentation](../../api/index.md?view=ml-dotnet).</span></span>
