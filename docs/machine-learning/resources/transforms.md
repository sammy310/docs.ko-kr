---
title: 데이터 변환
description: ML.NET에서 지원되는 기능 엔지니어링 구성 요소를 탐색합니다.
ms.date: 04/02/2019
ms.openlocfilehash: ca410b475c556db5ad4c3862fb79755b455d6830
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "79397754"
---
# <a name="data-transformations"></a><span data-ttu-id="8b846-103">데이터 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-103">Data transformations</span></span>

<span data-ttu-id="8b846-104">데이터 변환은 다음 작업에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b846-104">Data transformations are used to:</span></span>

- <span data-ttu-id="8b846-105">모델 학습을 위한 데이터 준비</span><span class="sxs-lookup"><span data-stu-id="8b846-105">prepare data for model training</span></span>
- <span data-ttu-id="8b846-106">TensorFlow 또는 ONNX 형식으로 가져온 모델 적용</span><span class="sxs-lookup"><span data-stu-id="8b846-106">apply an imported model in TensorFlow or ONNX format</span></span>
- <span data-ttu-id="8b846-107">모델을 통해 전달된 후 데이터 사후 처리</span><span class="sxs-lookup"><span data-stu-id="8b846-107">post-process data after it has been passed through a model</span></span>

<span data-ttu-id="8b846-108">이 가이드의 변환은 [IEstimator](xref:Microsoft.ML.IEstimator%601) 인터페이스를 구현하는 클래스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8b846-108">The transformations in this guide return classes that implement the [IEstimator](xref:Microsoft.ML.IEstimator%601) interface.</span></span> <span data-ttu-id="8b846-109">데이터 변환은 함께 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b846-109">Data transformations can be chained together.</span></span> <span data-ttu-id="8b846-110">두 변환은 각각 연결된 참조 설명서에 지정된 특정 형식 및 형태의 데이터를 예측하고 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8b846-110">Each transformation both expects and produces data of specific types and formats, which are specified in the linked reference documentation.</span></span>

<span data-ttu-id="8b846-111">일부 데이터 변환의 경우 해당 매개 변수를 계산하려면 학습 데이터가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8b846-111">Some data transformations require training data to calculate their parameters.</span></span> <span data-ttu-id="8b846-112">예를 들어 <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> 변환기는 `Fit()` 작업 중에 학습 데이터의 평균 및 분산을 계산하고 해당 매개 변수를 `Transform()` 작업에서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8b846-112">For example: the <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> transformer calculates the mean and variance of the training data during the `Fit()` operation, and uses those parameters in the `Transform()` operation.</span></span>

<span data-ttu-id="8b846-113">다른 데이터 변환에는 학습 데이터가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b846-113">Other data transformations don't require training data.</span></span> <span data-ttu-id="8b846-114">예를 들어 <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale%2A> 변환은 `Transform()` 작업 중에 학습 데이터를 확인하지 않고 `Fit()` 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b846-114">For example: the <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale%2A> transformation can perform the `Transform()` operation without having seen any training data during the `Fit()` operation.</span></span>

## <a name="column-mapping-and-grouping"></a><span data-ttu-id="8b846-115">열 매핑 및 그룹화</span><span class="sxs-lookup"><span data-stu-id="8b846-115">Column mapping and grouping</span></span>

| <span data-ttu-id="8b846-116">변형</span><span class="sxs-lookup"><span data-stu-id="8b846-116">Transform</span></span> | <span data-ttu-id="8b846-117">정의</span><span class="sxs-lookup"><span data-stu-id="8b846-117">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A> | <span data-ttu-id="8b846-118">새 출력 열에 하나 이상의 입력 열 연결</span><span class="sxs-lookup"><span data-stu-id="8b846-118">Concatenate one or more input columns into a new output column</span></span> |
| <xref:Microsoft.ML.TransformExtensionsCatalog.CopyColumns%2A> | <span data-ttu-id="8b846-119">하나 이상의 입력 열 복사 및 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="8b846-119">Copy and rename one or more input columns</span></span> |
| <xref:Microsoft.ML.TransformExtensionsCatalog.DropColumns%2A> | <span data-ttu-id="8b846-120">하나 이상의 입력 열 삭제</span><span class="sxs-lookup"><span data-stu-id="8b846-120">Drop one or more input columns</span></span> |
| <xref:Microsoft.ML.TransformExtensionsCatalog.SelectColumns%2A> | <span data-ttu-id="8b846-121">입력 데이터에서 유지할 하나 이상의 열 선택</span><span class="sxs-lookup"><span data-stu-id="8b846-121">Select one or more columns to keep from the input data</span></span> |

## <a name="normalization-and-scaling"></a><span data-ttu-id="8b846-122">정규화 및 크기 조정</span><span class="sxs-lookup"><span data-stu-id="8b846-122">Normalization and scaling</span></span>

| <span data-ttu-id="8b846-123">변형</span><span class="sxs-lookup"><span data-stu-id="8b846-123">Transform</span></span> | <span data-ttu-id="8b846-124">정의</span><span class="sxs-lookup"><span data-stu-id="8b846-124">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> | <span data-ttu-id="8b846-125">학습 데이터의 평균을 빼고 학습 데이터의 차이로 나누기</span><span class="sxs-lookup"><span data-stu-id="8b846-125">Subtract the mean (of the training data) and divide by the variance (of the training data)</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLogMeanVariance%2A> | <span data-ttu-id="8b846-126">학습 데이터의 로그를 기반으로 정규화</span><span class="sxs-lookup"><span data-stu-id="8b846-126">Normalize based on the logarithm of the training data</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLpNorm%2A> | <span data-ttu-id="8b846-127">[lp-norm](https://en.wikipedia.org/wiki/Lp_space#The_p-norm_in_finite_dimensions)으로 입력 벡터 크기 조정. 여기서 p는 1, 2 또는 무한대입니다.</span><span class="sxs-lookup"><span data-stu-id="8b846-127">Scale input vectors by their [lp-norm](https://en.wikipedia.org/wiki/Lp_space#The_p-norm_in_finite_dimensions), where p is 1, 2 or infinity.</span></span> <span data-ttu-id="8b846-128">기본값 l2(유클리드 거리)로 설정</span><span class="sxs-lookup"><span data-stu-id="8b846-128">Defaults to the l2 (Euclidean distance) norm</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeGlobalContrast%2A> | <span data-ttu-id="8b846-129">행 데이터의 평균을 빼서 행에 있는 각 값의 크기를 조정하고, 표준 편차 또는 l2-norm(행 데이터)으로 나누고, 구성 가능한 배율(기본값 2) 곱하기</span><span class="sxs-lookup"><span data-stu-id="8b846-129">Scale each value in a row by subtracting the mean of the row data and divide by either the standard deviation or l2-norm (of the row data), and multiply by a configurable scale factor (default 2)</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A> | <span data-ttu-id="8b846-130">bin 인덱스에 입력 값을 할당하고 bin 수로 나누어 0과 1 사이 float 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8b846-130">Assign the input value to a bin index and divide by the number of bins to produce a float value between 0 and 1.</span></span> <span data-ttu-id="8b846-131">bin 경계는 여러 bin에 학습 데이터를 균등하게 분배하도록 계산됨</span><span class="sxs-lookup"><span data-stu-id="8b846-131">The bin boundaries are calculated to evenly distribute the training data across bins</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeSupervisedBinning%2A> | <span data-ttu-id="8b846-132">레이블 열에 대한 상관 관계에 따라 bin에 입력 값 할당</span><span class="sxs-lookup"><span data-stu-id="8b846-132">Assign the input value to a bin based on its correlation with label column</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A> | <span data-ttu-id="8b846-133">학습 데이터에서 최솟값과 최댓값의 차이로 입력 크기 조정</span><span class="sxs-lookup"><span data-stu-id="8b846-133">Scale the input by the difference between the minimum and maximum values in the training data</span></span> |

## <a name="conversions-between-data-types"></a><span data-ttu-id="8b846-134">데이터 형식 간 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-134">Conversions between data types</span></span>

| <span data-ttu-id="8b846-135">변형</span><span class="sxs-lookup"><span data-stu-id="8b846-135">Transform</span></span> | <span data-ttu-id="8b846-136">정의</span><span class="sxs-lookup"><span data-stu-id="8b846-136">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.ConvertType%2A> | <span data-ttu-id="8b846-137">입력 열 형식을 새 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-137">Convert the type of an input column to a new type</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValue%2A> | <span data-ttu-id="8b846-138">제공된 매핑 사전을 기반으로 키(범주)에 값 매핑</span><span class="sxs-lookup"><span data-stu-id="8b846-138">Map values to keys (categories) based on the supplied dictionary of mappings</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> | <span data-ttu-id="8b846-139">입력 데이터에서 매핑을 만들어 키(범주)에 값 매핑</span><span class="sxs-lookup"><span data-stu-id="8b846-139">Map values to keys (categories) by creating the mapping from the input data</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue%2A> | <span data-ttu-id="8b846-140">키를 다시 원래 값으로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-140">Convert keys back to their original values</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToVector%2A> | <span data-ttu-id="8b846-141">키를 다시 원래 값의 벡터로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-141">Convert keys back to vectors of original values</span></span> |
| <xref:Microsoft.ML.ConversionsCatalog.MapKeyToBinaryVector%2A> | <span data-ttu-id="8b846-142">키를 다시 원래 값의 이진 벡터로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-142">Convert keys back to a binary vector of original values</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash%2A> | <span data-ttu-id="8b846-143">입력 열에서 값 해시</span><span class="sxs-lookup"><span data-stu-id="8b846-143">Hash the value in the input column</span></span> |

## <a name="text-transformations"></a><span data-ttu-id="8b846-144">텍스트 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-144">Text transformations</span></span>

| <span data-ttu-id="8b846-145">변형</span><span class="sxs-lookup"><span data-stu-id="8b846-145">Transform</span></span> | <span data-ttu-id="8b846-146">정의</span><span class="sxs-lookup"><span data-stu-id="8b846-146">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.TextCatalog.FeaturizeText%2A> | <span data-ttu-id="8b846-147">텍스트 열을 정규화된 ngrams 및 char-grams 수의 float 배열로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-147">Transform a text column into a float array of normalized ngrams and char-grams counts</span></span> |
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A> | <span data-ttu-id="8b846-148">하나 이상의 텍스트 열을 개별 단어로 분할</span><span class="sxs-lookup"><span data-stu-id="8b846-148">Split one or more text columns into individual words</span></span> |
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoCharactersAsKeys%2A> | <span data-ttu-id="8b846-149">토픽 세트에서 하나 이상의 텍스트 열을 개별 문자 float로 분할</span><span class="sxs-lookup"><span data-stu-id="8b846-149">Split one or more text columns into individual characters floats over a set of topics</span></span> |
| <xref:Microsoft.ML.TextCatalog.NormalizeText%2A> | <span data-ttu-id="8b846-150">대/소문자 변경, 분음 부호, 문장 부호 및 숫자 제거</span><span class="sxs-lookup"><span data-stu-id="8b846-150">Change case, remove diacritical marks, punctuation marks, and numbers</span></span> |
| <xref:Microsoft.ML.TextCatalog.ProduceNgrams%2A> | <span data-ttu-id="8b846-151">텍스트 열을 ngrams 개수 모음(연속 단어의 시퀀스)으로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-151">Transform text column into a bag of counts of ngrams (sequences of consecutive words)</span></span>|
| <xref:Microsoft.ML.TextCatalog.ProduceWordBags%2A> | <span data-ttu-id="8b846-152">텍스트 열을 ngrams 벡터 개수 모음으로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-152">Transform text column into a bag of counts of ngrams vector</span></span> |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedNgrams%2A> | <span data-ttu-id="8b846-153">텍스트 열을 해시된 ngram 개수 벡터로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-153">Transform text column into a vector of hashed ngram counts</span></span> |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedWordBags%2A> | <span data-ttu-id="8b846-154">텍스트 열을 해시된 ngram 개수 모음으로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-154">Transform text column into a bag of hashed ngram counts</span></span> |
| <xref:Microsoft.ML.TextCatalog.RemoveDefaultStopWords%2A>  | <span data-ttu-id="8b846-155">입력 열에서 지정된 언어의 기본 중지 단어 제거</span><span class="sxs-lookup"><span data-stu-id="8b846-155">Remove default stop words for the specified language from input columns</span></span> |
| <xref:Microsoft.ML.TextCatalog.RemoveStopWords%2A> | <span data-ttu-id="8b846-156">입력 열에서 지정된 중지 단어 제거</span><span class="sxs-lookup"><span data-stu-id="8b846-156">Removes specified stop words from input columns</span></span> |
| <xref:Microsoft.ML.TextCatalog.LatentDirichletAllocation%2A> | <span data-ttu-id="8b846-157">토픽 세트에서 문서(float 벡터로 표시됨)를 float 벡터로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-157">Transform a document (represented as a vector of floats) into a vector of floats over a set of topics</span></span> |
| <xref:Microsoft.ML.TextCatalog.ApplyWordEmbedding%2A> | <span data-ttu-id="8b846-158">미리 학습된 모델을 사용하여 텍스트 토큰의 벡터를 문장 벡터로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-158">Convert vectors of text tokens into sentence vectors using a pre-trained model</span></span> |

## <a name="image-transformations"></a><span data-ttu-id="8b846-159">이미지 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-159">Image transformations</span></span>

| <span data-ttu-id="8b846-160">변형</span><span class="sxs-lookup"><span data-stu-id="8b846-160">Transform</span></span> | <span data-ttu-id="8b846-161">정의</span><span class="sxs-lookup"><span data-stu-id="8b846-161">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale%2A> | <span data-ttu-id="8b846-162">이미지를 회색조로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-162">Convert an image to grayscale</span></span> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToImage%2A> | <span data-ttu-id="8b846-163">픽셀의 벡터를 <xref:Microsoft.ML.Transforms.Image.ImageDataViewType>으로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-163">Convert a vector of pixels to <xref:Microsoft.ML.Transforms.Image.ImageDataViewType></span></span> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels%2A> | <span data-ttu-id="8b846-164">입력 이미지의 벡터를 숫자의 벡터로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-164">Convert pixels from input image into a vector of numbers</span></span> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages%2A> | <span data-ttu-id="8b846-165">폴더에서 메모리로 이미지 로드</span><span class="sxs-lookup"><span data-stu-id="8b846-165">Load images from a folder into memory</span></span> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages%2A> | <span data-ttu-id="8b846-166">이미지 크기 조정</span><span class="sxs-lookup"><span data-stu-id="8b846-166">Resize images</span></span> |
| <xref:Microsoft.ML.OnnxCatalog.DnnFeaturizeImage%2A> | <span data-ttu-id="8b846-167">미리 학습된 심층 신경망(DNN) 모델을 적용하여 입력 이미지를 기능 벡터로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-167">Applies a pre-trained deep neural network (DNN) model to transform an input image into a feature vector</span></span> |

## <a name="categorical-data-transformations"></a><span data-ttu-id="8b846-168">범주별 데이터 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-168">Categorical data transformations</span></span>

| <span data-ttu-id="8b846-169">변형</span><span class="sxs-lookup"><span data-stu-id="8b846-169">Transform</span></span> | <span data-ttu-id="8b846-170">정의</span><span class="sxs-lookup"><span data-stu-id="8b846-170">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding%2A> | <span data-ttu-id="8b846-171">하나 이상의 텍스트 열을 [원 핫(one-hot)](https://en.wikipedia.org/wiki/One-hot) 인코딩된 벡터로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-171">Convert one or more text columns into [one-hot](https://en.wikipedia.org/wiki/One-hot) encoded vectors</span></span> |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotHashEncoding%2A> | <span data-ttu-id="8b846-172">하나 이상의 텍스트 열을 해시 기반 원 핫(one-hot) 인코딩된 벡터로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-172">Convert one or more text columns into hash-based one-hot encoded vectors</span></span> |

## <a name="time-series-data-transformations"></a><span data-ttu-id="8b846-173">시계열 데이터 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-173">Time series data transformations</span></span>

| <span data-ttu-id="8b846-174">변형</span><span class="sxs-lookup"><span data-stu-id="8b846-174">Transform</span></span> | <span data-ttu-id="8b846-175">정의</span><span class="sxs-lookup"><span data-stu-id="8b846-175">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectAnomalyBySrCnn%2A> | <span data-ttu-id="8b846-176">SR(Spectral Residual) 알고리즘을 사용하여 입력 시계열 데이터에서 변칙 검색</span><span class="sxs-lookup"><span data-stu-id="8b846-176">Detect anomalies in the input time series data using the Spectral Residual (SR) algorithm</span></span> |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectChangePointBySsa%2A> | <span data-ttu-id="8b846-177">단일 스펙트럼 분석(SSA)을 사용하여 시계열 데이터에서 변경점 검색</span><span class="sxs-lookup"><span data-stu-id="8b846-177">Detect change points in time series data using singular spectrum analysis (SSA)</span></span> |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectIidChangePoint%2A> | <span data-ttu-id="8b846-178">적응 커널 밀도 예측 및 마팅게일(martingale) 점수를 사용하여 개별적으로 동일하게 배포된(IID) 시계열 데이터에서 변경점 검색</span><span class="sxs-lookup"><span data-stu-id="8b846-178">Detect change points in independent and identically distributed (IID) time series data using adaptive kernel density estimations and martingale scores</span></span> |
| <xref:Microsoft.ML.TimeSeriesCatalog.ForecastBySsa%2A> | <span data-ttu-id="8b846-179">단일 스펙트럼 분석(SSA)을 사용하여 시계열 데이터 예측</span><span class="sxs-lookup"><span data-stu-id="8b846-179">Forecast time series data using singular spectrum analysis (SSA)</span></span> |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectSpikeBySsa%2A> | <span data-ttu-id="8b846-180">단일 스펙트럼 분석(SSA)을 사용하여 시계열 데이터에서 급증 검색</span><span class="sxs-lookup"><span data-stu-id="8b846-180">Detect spikes in time series data using singular spectrum analysis (SSA)</span></span> |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectIidSpike%2A> | <span data-ttu-id="8b846-181">적응 커널 밀도 예측 및 마팅게일(martingale) 점수를 사용하여 개별적으로 동일하게 배포된(IID) 시계열 데이터에서 급증 검색</span><span class="sxs-lookup"><span data-stu-id="8b846-181">Detect spikes in independent and identically distributed (IID) time series data using adaptive kernel density estimations and martingale scores</span></span> |

## <a name="missing-values"></a><span data-ttu-id="8b846-182">누락 값</span><span class="sxs-lookup"><span data-stu-id="8b846-182">Missing values</span></span>

| <span data-ttu-id="8b846-183">변형</span><span class="sxs-lookup"><span data-stu-id="8b846-183">Transform</span></span> | <span data-ttu-id="8b846-184">정의</span><span class="sxs-lookup"><span data-stu-id="8b846-184">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.ExtensionsCatalog.IndicateMissingValues%2A> | <span data-ttu-id="8b846-185">새 부울 출력 열 만들기. 이 열의 값은 입력 열의 값이 누락된 경우 true입니다.</span><span class="sxs-lookup"><span data-stu-id="8b846-185">Create a new boolean output column, the value of which is true when the value in the input column is missing</span></span> |
| <xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A> | <span data-ttu-id="8b846-186">새 출력 열 만들기. 이 열의 값은 입력 열에 값이 없는 경우 기본값으로 설정되고, 이외의 경우에는 해당 값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b846-186">Create a new output column, the value of which is set to a default value if the value is missing from the input column, and the input value otherwise</span></span> |

## <a name="feature-selection"></a><span data-ttu-id="8b846-187">기능 선택</span><span class="sxs-lookup"><span data-stu-id="8b846-187">Feature selection</span></span>

| <span data-ttu-id="8b846-188">변형</span><span class="sxs-lookup"><span data-stu-id="8b846-188">Transform</span></span> | <span data-ttu-id="8b846-189">정의</span><span class="sxs-lookup"><span data-stu-id="8b846-189">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnCount%2A> | <span data-ttu-id="8b846-190">기본값이 아닌 값이 임계값보다 큰 기능 선택</span><span class="sxs-lookup"><span data-stu-id="8b846-190">Select features whose non-default values are greater than a threshold</span></span> |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnMutualInformation%2A> | <span data-ttu-id="8b846-191">레이블 열의 데이터가 종속성이 가장 높은 기능 선택</span><span class="sxs-lookup"><span data-stu-id="8b846-191">Select the features on which the data in the label column is most dependent</span></span> |

## <a name="feature-transformations"></a><span data-ttu-id="8b846-192">기능 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-192">Feature transformations</span></span>

| <span data-ttu-id="8b846-193">변형</span><span class="sxs-lookup"><span data-stu-id="8b846-193">Transform</span></span> | <span data-ttu-id="8b846-194">정의</span><span class="sxs-lookup"><span data-stu-id="8b846-194">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.KernelExpansionCatalog.ApproximatedKernelMap%2A> | <span data-ttu-id="8b846-195">기능을 선형 알고리즘의 입력으로 사용할 수 있도록 내부 제품에서 커널 함수에 가까운 낮은 차원 기능 영역에 각 입력 벡터를 매핑</span><span class="sxs-lookup"><span data-stu-id="8b846-195">Map each input vector onto a lower dimensional feature space, where inner products approximate a kernel function, so that the features can be used as inputs to the linear algorithms</span></span> |
| <xref:Microsoft.ML.PcaCatalog.ProjectToPrincipalComponents%2A> | <span data-ttu-id="8b846-196">보안 주체 구성 요소 분석 알고리즘을 적용하여 입력 기능 벡터의 차원 줄이기</span><span class="sxs-lookup"><span data-stu-id="8b846-196">Reduce the dimensions of the input feature vector by applying the Principal Component Analysis algorithm</span></span> |

## <a name="explainability-transformations"></a><span data-ttu-id="8b846-197">설명 가능성 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-197">Explainability transformations</span></span>

| <span data-ttu-id="8b846-198">변형</span><span class="sxs-lookup"><span data-stu-id="8b846-198">Transform</span></span> | <span data-ttu-id="8b846-199">정의</span><span class="sxs-lookup"><span data-stu-id="8b846-199">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.ExplainabilityCatalog.CalculateFeatureContribution%2A> | <span data-ttu-id="8b846-200">기능 벡터의 각 요소에 대한 기여 점수 계산</span><span class="sxs-lookup"><span data-stu-id="8b846-200">Calculate contribution scores for each element of a feature vector</span></span> |

## <a name="calibration-transformations"></a><span data-ttu-id="8b846-201">보정 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-201">Calibration transformations</span></span>

| <span data-ttu-id="8b846-202">변형</span><span class="sxs-lookup"><span data-stu-id="8b846-202">Transform</span></span> | <span data-ttu-id="8b846-203">정의</span><span class="sxs-lookup"><span data-stu-id="8b846-203">Definition</span></span> |
| --- | --- |
|<xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Platt%28System.String%2CSystem.String%2CSystem.String%29> | <span data-ttu-id="8b846-204">학습 데이터를 사용하여 추정한 매개 변수가 있는 로지스틱 회귀 분석을 사용하여 이진 분류자 원시 점수를 클래스 확률로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-204">Transforms a binary classifier raw score into a class probability using logistic regression with parameters estimated using the training data</span></span> |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Platt%28System.Double%2CSystem.Double%2CSystem.String%29> | <span data-ttu-id="8b846-205">고정 매개 변수가 있는 로지스틱 회귀 분석을 사용하여 이진 분류자 원시 점수를 클래스 확률로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-205">Transforms a binary classifier raw score into a class probability using logistic regression with fixed parameters</span></span> |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Naive%2A> | <span data-ttu-id="8b846-206">Bin에 점수를 할당하고 bin 간 분포를 기준으로 확률을 계산하여 이진 분류자 원시 점수를 클래스 확률로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-206">Transforms a binary classifier raw score into a class probability by assigning scores to bins, and calculating the probability based on the distribution among the bins</span></span> |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Isotonic%2A> | <span data-ttu-id="8b846-207">점수를 bin에 할당하여 이진 분류자 원시 점수를 클래스 확률로 변환합니다. 여기서 경계 위치와 bin 크기는 학습 데이터를 사용하여 추정함</span><span class="sxs-lookup"><span data-stu-id="8b846-207">Transforms a binary classifier raw score into a class probability by assigning scores to bins, where the position of boundaries and the size of bins are estimated using the training data</span></span>  |

## <a name="deep-learning-transformations"></a><span data-ttu-id="8b846-208">딥 러닝 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-208">Deep learning transformations</span></span>

| <span data-ttu-id="8b846-209">변형</span><span class="sxs-lookup"><span data-stu-id="8b846-209">Transform</span></span> | <span data-ttu-id="8b846-210">정의</span><span class="sxs-lookup"><span data-stu-id="8b846-210">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.OnnxCatalog.ApplyOnnxModel%2A> | <span data-ttu-id="8b846-211">가져온 ONNX 모델을 사용하여 입력 데이터 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-211">Transform the input data with an imported ONNX model</span></span> |
| <xref:Microsoft.ML.TensorflowCatalog.LoadTensorFlowModel%2A> | <span data-ttu-id="8b846-212">가져온 TensorFlow 모델을 사용하여 입력 데이터 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-212">Transform the input data with an imported TensorFlow model</span></span> |

## <a name="custom-transformations"></a><span data-ttu-id="8b846-213">사용자 지정 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-213">Custom transformations</span></span>

| <span data-ttu-id="8b846-214">변형</span><span class="sxs-lookup"><span data-stu-id="8b846-214">Transform</span></span> | <span data-ttu-id="8b846-215">정의</span><span class="sxs-lookup"><span data-stu-id="8b846-215">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.CustomMappingCatalog.CustomMapping%2A> | <span data-ttu-id="8b846-216">사용자 정의 매핑을 사용하여 기존 열을 새 열로 변환</span><span class="sxs-lookup"><span data-stu-id="8b846-216">Transform existing columns onto new ones with a user-defined mapping</span></span> |
