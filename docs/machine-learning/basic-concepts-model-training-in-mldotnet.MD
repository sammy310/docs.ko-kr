---
title: ML.NET의 모델 학습에 대한 기본 개념
description: 이 문서에서는 ML.NET의 *모델 학습* 시나리오에 대한 기본 개념을 설명합니다. 일부 개념은 보다 간단한 *기존 모델을 사용한 예측* 시나리오와 관련이 없습니다.
ms.date: 03/05/2019
ms.topic: overview
ms.custom: mvc
ms.openlocfilehash: 78554cfd1dfdb3dba82a325d47245aeb313bb6fe
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675565"
---
# <a name="basic-concepts-for-model-training-in-mlnet"></a><span data-ttu-id="7ff5f-104">ML.NET의 모델 학습에 대한 기본 개념</span><span class="sxs-lookup"><span data-stu-id="7ff5f-104">Basic concepts for model training in ML.NET</span></span>

<span data-ttu-id="7ff5f-105">이 문서에서는 ML.NET의 *모델 학습* 시나리오에 대한 기본 개념을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-105">This article explains the basic concepts covering *model training* scenarios in ML.NET.</span></span> <span data-ttu-id="7ff5f-106">일부 개념은 보다 간단한 *기존 모델을 사용한 예측* 시나리오와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-106">Not all concepts are relevant to the more simple scenario of *prediction with an existing model*.</span></span>

<span data-ttu-id="7ff5f-107">이 문서와 관련 샘플에서는 현재 **ML.NET 버전 0.10**을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-107">This article and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="7ff5f-108">자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-108">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="model-training-concepts"></a><span data-ttu-id="7ff5f-109">모델 학습 개념</span><span class="sxs-lookup"><span data-stu-id="7ff5f-109">Model training concepts</span></span>

<span data-ttu-id="7ff5f-110">이 문서에서는 ML.NET의 모델 학습과 관련된 다음 개념을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-110">This document covers the following concepts related to model training in ML.NET:</span></span>

- <span data-ttu-id="7ff5f-111">[데이터(*Data*)](#data)는 `IDataView` 인터페이스로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-111">[*Data*](#data) represented as an `IDataView` interface.</span></span>
  - <span data-ttu-id="7ff5f-112">ML.NET에서 데이터는 SQL 보기와 유사합니다. 지연 평가되고, 변경할 수 없고, 커서가 가능하고, 형식이 다르며, 스키마화된 데이터 세트입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-112">In ML.NET, data is similar to a SQL view: It's a lazily evaluated, immutable, cursorable, heterogenous, schematized dataset.</span></span> 
  - <span data-ttu-id="7ff5f-113">데이터 인터페이스에 대한 훌륭한 문서는 [IDataView 디자인 원칙](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-113">An excellent document about the data interface is [IDataView Design Principles](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md).</span></span>
- <span data-ttu-id="7ff5f-114">[변환기(*Transformer*)](#transformer)는 `ITransformer` 인터페이스로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-114">[*Transformer*](#transformer) represented as `ITransformer` interface.</span></span>
  - <span data-ttu-id="7ff5f-115">변환기는 데이터를 가져다가, 데이터에 작업을 수행하고, 변환된 새로운 데이터를 반환하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-115">A transformer is a component that takes data, does some work on it, and returns new transformed data.</span></span>
  - <span data-ttu-id="7ff5f-116">예를 들어 기계 학습 모델은 기능을 사용하고 예측을 반환하는 변환기로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-116">For example, you can think of a machine learning model as a transformer that takes features and returns predictions.</span></span>
  - <span data-ttu-id="7ff5f-117">다른 예로, 텍스트 토크나이저는 단일 텍스트 열을 가져와서 텍스트에서 개별 단어를 추출하여 벡터 열을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-117">Another example, text tokenizer takes a single text column and outputs a vector column with individual words extracted out of the texts.</span></span>
- <span data-ttu-id="7ff5f-118">[데이터 판독기(*Data reader*)](#data-reader)는 `IDataReader<T>` 인터페이스로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-118">[*Data reader*](#data-reader) represented as an `IDataReader<T>` interface.</span></span>
  - <span data-ttu-id="7ff5f-119">데이터 판독기는 데이터를 만드는 ML.NET 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-119">The data reader is ML.NET component to create data.</span></span> <span data-ttu-id="7ff5f-120">`T` 인스턴스를 가져다가 데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-120">It takes an instance of `T` and returns data out of it.</span></span> 
  - <span data-ttu-id="7ff5f-121">예를 들어, *TextLoader*는 `IDataReader<IMultiStreamSource>`입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-121">For example, a *TextLoader* is an `IDataReader<IMultiStreamSource>`.</span></span> <span data-ttu-id="7ff5f-122">소스를 사용하여 데이터를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-122">It takes the source and produces data.</span></span> 
- <span data-ttu-id="7ff5f-123">[평가자(*Estimator*)](#estimator)는 `IEstimator<T>` 인터페이스로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-123">[*Estimator*](#estimator) represented as an `IEstimator<T>` interface.</span></span>
  - <span data-ttu-id="7ff5f-124">데이터를 통해 학습하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-124">This is an object that learns from data.</span></span> <span data-ttu-id="7ff5f-125">학습의 결과는 변환기(*transformer*)입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-125">The result of the learning is a *transformer*.</span></span>
  - <span data-ttu-id="7ff5f-126">기계 학습 알고리즘(*algorithm*)은 데이터를 학습하고 기계 학습 모델(*model*)을 생성하는 평가자라고 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-126">You can think of a machine learning *algorithm* as an estimator that learns on data and produces a machine learning *model*.</span></span>
- <span data-ttu-id="7ff5f-127">[예측 함수(*Prediction function*)](#prediction-function)는 `PredictionEngine<TSrc, TDst>` 클래스로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-127">[*Prediction function*](#prediction-function) represented as a `PredictionEngine<TSrc, TDst>` class.</span></span>
  - <span data-ttu-id="7ff5f-128">예측 함수는 예측 시간과 같은 변환기를 한 행에 적용하는 머신으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-128">The prediction function can be seen as a machine that applies a transformer to one row, such as at prediction time.</span></span>

## <a name="data"></a><span data-ttu-id="7ff5f-129">데이터</span><span class="sxs-lookup"><span data-stu-id="7ff5f-129">Data</span></span>

<span data-ttu-id="7ff5f-130">ML.NET에서 데이터는 SQL 보기와 유사합니다. 지연 평가되고, 커서가 가능하고, 형식이 다르며, 스키마화된 데이터 세트입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-130">In ML.NET, data is similar to a SQL view: It's a lazily evaluated, cursorable, heterogenous, schematized dataset.</span></span>

- <span data-ttu-id="7ff5f-131">데이터 뷰의 열에 대한 정보가 포함된 스키마(*Schema*)(`ISchema` 인터페이스의 인스턴스)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-131">It has *Schema* (an instance of an `ISchema` interface) that contains the information about the data view's columns.</span></span>
  - <span data-ttu-id="7ff5f-132">각 열에는 이름(*Name*), 유형(*Type*) 및 이와 관련된 임의의 메타데이터(*metadata*) 세트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-132">Each column has a *Name*, a *Type*, and an arbitrary set of *metadata* associated with it.</span></span>
  - <span data-ttu-id="7ff5f-133">열의 메타데이터(*metadata*)에는 벡터 열의 슬롯 이름 등과 같은 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-133">The column's *metadata* contains information like slot names of a vector column and the like.</span></span> <span data-ttu-id="7ff5f-134">메타데이터 자체는 각 열에 고유한 또 다른 한 행 데이터(*data*)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-134">The metadata itself is represented as another one-row *data* that is unique to each column.</span></span>
  - <span data-ttu-id="7ff5f-135">데이터 뷰는 커서(*cursors*)의 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-135">The data view is a source of *cursors*.</span></span> <span data-ttu-id="7ff5f-136">SQL 커서를 생각해보면: 커서는 한 번에 한 행씩 데이터를 반복하고 사용 가능한 데이터를 표시하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-136">Think SQL cursors: A cursor is an object that iterates through the data, one row at a time, and presents the available data.</span></span>
  - <span data-ttu-id="7ff5f-137">물론 데이터에는 필요한 만큼 활성 커서가 많이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-137">Naturally, data can have as many active cursors over it as needed.</span></span> <span data-ttu-id="7ff5f-138">데이터 자체는 변경할 수 없기 때문에 커서는 완전히 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-138">Since data itself is immutable, cursors are truly independent.</span></span>
  - <span data-ttu-id="7ff5f-139">커서는 일반적으로 열의 하위 집합에만 액세스합니다. 효율성을 높이기 위해 ML.NET은 커서에 필요한 열의 값만 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-139">Cursors typically access only a subset of columns: For efficiency, ML.NET computes only the values of columns that are needed by the cursor.</span></span>

## <a name="transformer"></a><span data-ttu-id="7ff5f-140">변환기</span><span class="sxs-lookup"><span data-stu-id="7ff5f-140">Transformer</span></span>

<span data-ttu-id="7ff5f-141">변환기는 데이터를 가져다가, 데이터에 작업을 수행하고, 변환된 새로운 데이터를 반환하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-141">A transformer is a component that takes data, does some work on it, and returns new transformed data.</span></span>

<span data-ttu-id="7ff5f-142">ML.NET에서 대부분의 변환기는 한 번에 하나의 입력 열(*input column*)에 작동하고 출력 열(*output column*)을 생성하는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-142">Most transformers in ML.NET tend to operate on one *input column* at a time, and produce the *output column*.</span></span> <span data-ttu-id="7ff5f-143">예를 들어 `new HashTransformer("bar", "foo")`는 "foo" 열의 값을 사용하여, 해시를 지정하고, "bar" 열에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-143">For example, a `new HashTransformer("bar", "foo")` takes the values from column "foo", hashes them, and puts them into column "bar".</span></span> 

<span data-ttu-id="7ff5f-144">또한, 입력 및 출력 열 이름이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-144">It's also common that the input and output column names are the same.</span></span> <span data-ttu-id="7ff5f-145">이런 경우 기존 열이 새 열로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-145">In this case, the old column is replaced with the new one.</span></span> <span data-ttu-id="7ff5f-146">예를 들어 `new HashTransformer("foo")`는 "foo" 열의 값을 사용하여, 해시를 지정하고, "foo" 열에 다시 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-146">For example, a `new HashTransformer("foo")` takes the values from column "foo", hashes them, and puts them back into "foo".</span></span> 

<span data-ttu-id="7ff5f-147">`Transform`이 호출될 때 모든 변환기는 새로운 데이터 보기를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-147">Any transformer, produces a new data view when `Transform` is called.</span></span> <span data-ttu-id="7ff5f-148">데이터 보기는 변경할 수 없다는 것을 기억하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-148">Remember, data views are immutable.</span></span>

<span data-ttu-id="7ff5f-149">또 다른 주요 고려 사항은 데이터가 지연 평가되기 때문에 *변환기도 지연*된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-149">Another important consideration is that, because data is lazily evaluated, *transformers are lazy too*.</span></span> <span data-ttu-id="7ff5f-150">특히, 호출 후에</span><span class="sxs-lookup"><span data-stu-id="7ff5f-150">Essentially, after you call</span></span>

```csharp
var newData = transformer.Transform(oldData)
```

<span data-ttu-id="7ff5f-151">실제 계산 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-151">no actual computation happens.</span></span> <span data-ttu-id="7ff5f-152">`newData`에서 커서를 가져와서 값을 사용하기 시작한 후에야 `newData`는 `transformer` 변환 논리를 호출합니다(그럼에도 요청된 열을 생성하기 위해 해당 `transformer`가 필요한 경우에만 발생합니다).</span><span class="sxs-lookup"><span data-stu-id="7ff5f-152">Only after you get a cursor from `newData` and start consuming the value does `newData` invoke the `transformer` transformation logic (and even then, it only happens if the `transformer` in question is needed to produce the requested columns).</span></span>

### <a name="transformer-chains"></a><span data-ttu-id="7ff5f-153">변환기 체인</span><span class="sxs-lookup"><span data-stu-id="7ff5f-153">Transformer chains</span></span>

<span data-ttu-id="7ff5f-154">변환기의 유용한 속성은 *변환기의 순차적인 적용을 다른 변환기로 빌드할 수 있다는 점입니다*.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-154">A useful property of a transformer is that *you can build a sequential application of transformers as yet another transformer*:</span></span>

```csharp
var fullTransformer = transformer1.Append(transformer2).Append(transformer3);
```

<span data-ttu-id="7ff5f-155">이 속성은 ML.NET에서 일반적으로 사용됩니다. 일반적으로, 학습된 ML.NET 모델은 모든 의도와 목적을 위한 변환기(*transformer*)의 연결인 변환기 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-155">This property is commonly used in ML.NET: typically, the trained ML.NET model is a chain of transformers, which is, for all intents and purposes, a *transformer*.</span></span>

## <a name="data-reader"></a><span data-ttu-id="7ff5f-156">데이터 판독기</span><span class="sxs-lookup"><span data-stu-id="7ff5f-156">Data reader</span></span>

<span data-ttu-id="7ff5f-157">데이터 판독기는 데이터를 '생성'하는 ML.NET 구성 요소입니다. `T` 인스턴스를 사용하여 데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-157">The data reader is an ML.NET component to 'create' data: it takes an instance of `T` and returns data out of it.</span></span>

<span data-ttu-id="7ff5f-158">흥미로운 점은, 기존 데이터 판독기에 변환기를 연결하여 데이터 판독기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-158">An interesting property to note is that you can create a data reader by attaching a transformer to an existing data reader.</span></span> <span data-ttu-id="7ff5f-159">이러한 방식으로 변환 동작이 베이킹된 판독기를 사용 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-159">This way you can have a reader with transformation behavior baked in:</span></span>

```csharp
var newReader = reader.Append(transformer1).Append(transformer2)
```

<span data-ttu-id="7ff5f-160">변환기와 유사한 또 다른 점은 데이터가 지연 평가되기 때문에 판독기가 지연된다는 점입니다. `reader.Read()`를 호출하면 실제로 '읽기'가 발생하지 않습니다(또는 최소로 발생함). 커서가 결과 데이터에 요청된 경우에만 판독기 작업이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-160">Another similarity to transformers is that, since data is lazily evaluated, *readers are lazy*: no (or minimal) actual 'reading' happens when you call `reader.Read()`: only when a cursor is requested on the resulting data does the reader begin to work.</span></span>

## <a name="estimator"></a><span data-ttu-id="7ff5f-161">평가자</span><span class="sxs-lookup"><span data-stu-id="7ff5f-161">Estimator</span></span>

<span data-ttu-id="7ff5f-162">평가자(*estimator*)는 데이터를 통해 학습하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-162">The *estimator* is an object that learns from data.</span></span> <span data-ttu-id="7ff5f-163">학습의 결과는 변환기(*transformer*)입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-163">The result of the learning is a *transformer*.</span></span>

<span data-ttu-id="7ff5f-164">ML.NET에서는 이 속성을 사용하여 다른 평가자를 연결하는 학습 파이프 라인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-164">In ML.NET, use this property to create learning pipelines that chain together different estimators:</span></span>

```csharp
MLContext mlContext = new MLContext(seed: 0);

var pipeline = mlContext.Transforms.CopyColumns("Label","FareAmount")
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("VendorId"))
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("RateCode"))
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("PaymentType"))
    .Append(mlContext.Transforms.Concatenate("Features","VendorId","RateCode","PassengerCount","TripTime","TripDistance","PaymentType"))
    .Append(mlContext.Regression.Trainers.FastTree("Label","Features"));

var model = pipeline.Fit(dataView);
```

<span data-ttu-id="7ff5f-165">평가자의 중요한 특성 중 하나는 지연되지 않고 즉시 수행된다는 점입니다.`Fit`을 호출할 때마다 학습이 발생하며 이러한 작업은 잠재적으로 시간이 오래 걸리는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-165">One important property of estimators is that *estimators are eager, not lazy*: every call to `Fit` is causing learning to happen, which is potentially a time-consuming operation.</span></span>

## <a name="prediction-function"></a><span data-ttu-id="7ff5f-166">예측 함수</span><span class="sxs-lookup"><span data-stu-id="7ff5f-166">Prediction function</span></span>

<span data-ttu-id="7ff5f-167">예측 함수는 한 행에 변환기를 적용하는 구성 요소로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-167">The prediction function can be seen as a component that applies a transformer to one row.</span></span>

<span data-ttu-id="7ff5f-168">모델(`Fit()`을 통해 학습된 또는 다른 곳에서 로드한 변환기(*transformer*))을 얻은 후에는 `model.Transform(data)`에 대한 일반적인 호출을 사용하여 예측을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-168">Once you get the model (a *transformer* either trained via `Fit()`, or loaded from somewhere), you can use it to make predictions using the normal calls to `model.Transform(data)`.</span></span> <span data-ttu-id="7ff5f-169">하지만 실제 시나리오에 이 모델을 사용하면 예측할 사례가 많지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-169">However, when you use this model in a real-life scenario, you often don't have many examples to predict on.</span></span> <span data-ttu-id="7ff5f-170">대신, 한 번에 하나의 예제가 있으며, 적절한 시기에 즉시 예측을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-170">Instead, you have one example at a time, and you need to make timely predictions on them immediately.</span></span>

<span data-ttu-id="7ff5f-171">물론 이러한 작업을 일괄 처리 예측으로 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-171">Of course, you can reduce this to the batch prediction:</span></span>

- <span data-ttu-id="7ff5f-172">정확히 하나의 행으로 데이터 뷰를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-172">Create a data view with exactly one row.</span></span>
- <span data-ttu-id="7ff5f-173">`model.Transform(data)`을 호출하여 예측된 데이터 뷰를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-173">Call `model.Transform(data)` to get the predicted data view.</span></span>
- <span data-ttu-id="7ff5f-174">결과 데이터에 대해 커서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-174">Get a cursor over the resulting data.</span></span>
- <span data-ttu-id="7ff5f-175">커서를 한 단계 전진하여 첫 번째(유일한) 행을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-175">Advance the cursor one step to get to the first (and only) row.</span></span>
- <span data-ttu-id="7ff5f-176">여기에서 예측된 값을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-176">Extract the predicted values out of it.</span></span>

<span data-ttu-id="7ff5f-177">앞의 알고리즘은 다음과 같이 두 개의 사용자 정의 개체(`InputExample` 및 `OutputPrediction`)를 사용하여 [스키마 이해를](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md) 사용하여 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-177">The preceding algorithm can be implemented using the [schema comprehension](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md), with two user-defined objects `InputExample` and `OutputPrediction` as follows:</span></span>

```csharp
var inputData = mlContext.Data.ReadFromEnumerable(new InputExample[] { example });
var outputData = model.Transform(inputData);
var output = mlContext.CreateEnumerable<OutputPrediction>(outputData,reuseRowObject:false).First();
```

<span data-ttu-id="7ff5f-178">하지만 이 작업은 번거롭고 성능 비용이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-178">But this is cumbersome and incurs performance costs.</span></span> <span data-ttu-id="7ff5f-179">대신, 예측 함수 개체는 확장 메서드, `CreatePredictionEngine`을 통해 동일한 작업을 더 빠르고 편리하게 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-179">Instead, a prediction function object performs the same work, but faster and more convenient, via an extension method `CreatePredictionEngine`:</span></span>

```csharp
var predictionEngine = model.CreatePredictionEngine<InputExample,OutputPrediction>(mlContext);
var prediction = predictionEngine.Predict(example);
```

<span data-ttu-id="7ff5f-180">예측 함수는 재진입하지 않고/스레드로부터 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-180">The prediction function is *not re-entrant / thread-safe*.</span></span> <span data-ttu-id="7ff5f-181">여러 스레드에서 동시에 예측을 수행하려면 스레드당 예측 함수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff5f-181">If you want to conduct predictions simultaneously with multiple threads, you need to have a prediction function per thread.</span></span>
