---
title: 데이터 변환
description: ML.NET에서 지원되는 기능 엔지니어링 구성 요소를 탐색합니다.
author: natke
ms.author: nakersha
ms.date: 04/02/2019
ms.openlocfilehash: 7ea06e19b4651017079a6ae57136f033e0ce981c
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2019
ms.locfileid: "65558021"
---
# <a name="data-transformations"></a><span data-ttu-id="d6641-103">데이터 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-103">Data transformations</span></span>

<span data-ttu-id="d6641-104">데이터 변환은 모델 학습용 데이터를 준비하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6641-104">Data transformations are used to prepare data for model training.</span></span> <span data-ttu-id="d6641-105">이 가이드의 변환은 [IEstimator](xref:Microsoft.ML.IEstimator%601) 인터페이스를 구현하는 클래스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d6641-105">The transformations in this guide return classes that implement the [IEstimator](xref:Microsoft.ML.IEstimator%601) interface.</span></span> <span data-ttu-id="d6641-106">데이터 변환은 함께 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6641-106">Data transformations can be chained together.</span></span> <span data-ttu-id="d6641-107">두 변환은 각각 연결된 참조 설명서에 지정된 특정 형식 및 형태의 데이터를 예측하고 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d6641-107">Each transformation both expects and produces data of specific types and formats, which are specified in the linked reference documentation.</span></span>

<span data-ttu-id="d6641-108">일부 데이터 변환의 경우 해당 매개 변수를 계산하려면 학습 데이터가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d6641-108">Some data transformations require training data to calculate their parameters.</span></span> <span data-ttu-id="d6641-109">예를 들어 <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> 변환기는 `Fit()` 작업 중에 학습 데이터의 평균 및 분산을 계산하고 해당 매개 변수를 `Transform()` 작업에서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6641-109">For example: the <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> transformer calculates the mean and variance of the training data during the `Fit()` operation, and uses those parameters in the `Transform()` operation.</span></span> 

<span data-ttu-id="d6641-110">다른 데이터 변환에는 학습 데이터가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6641-110">Other data transformations don't require training data.</span></span> <span data-ttu-id="d6641-111">예를 들어 <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale*> 변환은 `Fit()` 작업 중에 학습 데이터를 확인하지 않고 `Transform()` 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6641-111">For example: the <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale*> transformation can perform the `Transform()` operation without having seen any training data during the `Fit()` operation.</span></span>

## <a name="column-mapping-and-grouping"></a><span data-ttu-id="d6641-112">열 매핑 및 그룹화</span><span class="sxs-lookup"><span data-stu-id="d6641-112">Column mapping and grouping</span></span>

| <span data-ttu-id="d6641-113">변형</span><span class="sxs-lookup"><span data-stu-id="d6641-113">Transform</span></span> | <span data-ttu-id="d6641-114">정의</span><span class="sxs-lookup"><span data-stu-id="d6641-114">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A> | <span data-ttu-id="d6641-115">새 출력 열에 하나 이상의 입력 열 연결</span><span class="sxs-lookup"><span data-stu-id="d6641-115">Concatenate one or more input columns into a new output column</span></span> |
| <xref:Microsoft.ML.TransformExtensionsCatalog.CopyColumns%2A> | <span data-ttu-id="d6641-116">하나 이상의 입력 열 복사 및 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="d6641-116">Copy and rename one or more input columns</span></span> |
| <xref:Microsoft.ML.TransformExtensionsCatalog.DropColumns%2A> | <span data-ttu-id="d6641-117">하나 이상의 입력 열 삭제</span><span class="sxs-lookup"><span data-stu-id="d6641-117">Drop one or more input columns</span></span> |
| <xref:Microsoft.ML.TransformExtensionsCatalog.SelectColumns%2A> | <span data-ttu-id="d6641-118">입력 데이터에서 유지할 하나 이상의 열 선택</span><span class="sxs-lookup"><span data-stu-id="d6641-118">Select one or more columns to keep from the input data</span></span> |

## <a name="normalization-and-scaling"></a><span data-ttu-id="d6641-119">정규화 및 크기 조정</span><span class="sxs-lookup"><span data-stu-id="d6641-119">Normalization and scaling</span></span>

| <span data-ttu-id="d6641-120">변형</span><span class="sxs-lookup"><span data-stu-id="d6641-120">Transform</span></span> | <span data-ttu-id="d6641-121">정의</span><span class="sxs-lookup"><span data-stu-id="d6641-121">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> | <span data-ttu-id="d6641-122">학습 데이터의 평균을 빼고 학습 데이터의 차이로 나누기</span><span class="sxs-lookup"><span data-stu-id="d6641-122">Subtract the mean (of the training data) and divide by the variance (of the training data)</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLogMeanVariance%2A> | <span data-ttu-id="d6641-123">학습 데이터의 로그를 기반으로 정규화</span><span class="sxs-lookup"><span data-stu-id="d6641-123">Normalize based on the logarithm of the training data</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLpNorm%2A> | <span data-ttu-id="d6641-124">[lp-norm](https://en.wikipedia.org/wiki/Lp_space#The_p-norm_in_finite_dimensions)으로 입력 벡터 크기 조정. 여기서 p는 1, 2 또는 무한대입니다.</span><span class="sxs-lookup"><span data-stu-id="d6641-124">Scale input vectors by their [lp-norm](https://en.wikipedia.org/wiki/Lp_space#The_p-norm_in_finite_dimensions), where p is 1, 2 or infinity.</span></span> <span data-ttu-id="d6641-125">기본값 l2(유클리드 거리)로 설정</span><span class="sxs-lookup"><span data-stu-id="d6641-125">Defaults to the l2 (Euclidean distance) norm</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeGlobalContrast%2A> | <span data-ttu-id="d6641-126">행 데이터의 평균을 빼서 행에 있는 각 값의 크기를 조정하고, 표준 편차 또는 l2-norm(행 데이터)으로 나누고, 구성 가능한 배율(기본값 2) 곱하기</span><span class="sxs-lookup"><span data-stu-id="d6641-126">Scale each value in a row by subtracting the mean of the row data and divide by either the standard deviation or l2-norm (of the row data), and multiply by a configurable scale factor (default 2)</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A> | <span data-ttu-id="d6641-127">bin 인덱스에 입력 값을 할당하고 bin 수로 나누어 0과 1 사이 float 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d6641-127">Assign the input value to a bin index and divide by the number of bins to produce a float value between 0 and 1.</span></span> <span data-ttu-id="d6641-128">bin 경계는 여러 bin에 학습 데이터를 균등하게 분배하도록 계산됨</span><span class="sxs-lookup"><span data-stu-id="d6641-128">The bin boundaries are calculated to evenly distribute the training data across bins</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeSupervisedBinning%2A> | <span data-ttu-id="d6641-129">레이블 열에 대한 상관 관계에 따라 bin에 입력 값 할당</span><span class="sxs-lookup"><span data-stu-id="d6641-129">Assign the input value to a bin based on its correlation with label column</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A> | <span data-ttu-id="d6641-130">학습 데이터에서 최솟값과 최댓값의 차이로 입력 크기 조정</span><span class="sxs-lookup"><span data-stu-id="d6641-130">Scale the input by the difference between the minimum and maximum values in the training data</span></span> |

## <a name="conversions-between-data-types"></a><span data-ttu-id="d6641-131">데이터 형식 간 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-131">Conversions between data types</span></span>

| <span data-ttu-id="d6641-132">변형</span><span class="sxs-lookup"><span data-stu-id="d6641-132">Transform</span></span> | <span data-ttu-id="d6641-133">정의</span><span class="sxs-lookup"><span data-stu-id="d6641-133">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.ConvertType%2A> | <span data-ttu-id="d6641-134">입력 열 형식을 새 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-134">Convert the type of an input column to a new type</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValue*> | <span data-ttu-id="d6641-135">제공된 매핑 사전을 기반으로 키(범주)에 값 매핑</span><span class="sxs-lookup"><span data-stu-id="d6641-135">Map values to keys (categories) based on the supplied dictionary of mappings</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey*> | <span data-ttu-id="d6641-136">입력 데이터에서 매핑을 만들어 키(범주)에 값 매핑</span><span class="sxs-lookup"><span data-stu-id="d6641-136">Map values to keys (categories) by creating the mapping from the input data</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue*> | <span data-ttu-id="d6641-137">키를 다시 원래 값으로 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-137">Convert keys back to their original values</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToVector*> | <span data-ttu-id="d6641-138">키를 다시 원래 값의 벡터로 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-138">Convert keys back to vectors of original values</span></span> |
| <xref:Microsoft.ML.ConversionsCatalog.MapKeyToBinaryVector*> | <span data-ttu-id="d6641-139">키를 다시 원래 값의 이진 벡터로 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-139">Convert keys back to a binary vector of original values</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash*> | <span data-ttu-id="d6641-140">입력 열에서 값 해시</span><span class="sxs-lookup"><span data-stu-id="d6641-140">Hash the value in the input column</span></span> |

## <a name="text-transformations"></a><span data-ttu-id="d6641-141">텍스트 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-141">Text transformations</span></span>

| <span data-ttu-id="d6641-142">변형</span><span class="sxs-lookup"><span data-stu-id="d6641-142">Transform</span></span> | <span data-ttu-id="d6641-143">정의</span><span class="sxs-lookup"><span data-stu-id="d6641-143">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.TextCatalog.FeaturizeText*> | <span data-ttu-id="d6641-144">텍스트 열을 정규화된 ngrams 및 char-grams 수의 float 배열로 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-144">Transform a text column into a float array of normalized ngrams and char-grams counts</span></span> | 
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoWords*> | <span data-ttu-id="d6641-145">하나 이상의 텍스트 열을 개별 단어로 분할</span><span class="sxs-lookup"><span data-stu-id="d6641-145">Split one or more text columns into individual words</span></span> |
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoCharactersAsKeys*> | <span data-ttu-id="d6641-146">토픽 세트에서 하나 이상의 텍스트 열을 개별 문자 float로 분할</span><span class="sxs-lookup"><span data-stu-id="d6641-146">Split one or more text columns into individual characters floats over a set of topics</span></span> |
| <xref:Microsoft.ML.TextCatalog.NormalizeText*> | <span data-ttu-id="d6641-147">대/소문자 변경, 분음 부호, 문장 부호 및 숫자 제거</span><span class="sxs-lookup"><span data-stu-id="d6641-147">Change case, remove diacritical marks, punctuation marks and numbers</span></span> |
| <xref:Microsoft.ML.TextCatalog.ProduceNgrams*> | <span data-ttu-id="d6641-148">텍스트 열을 ngrams 개수 모음(연속 단어의 시퀀스)으로 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-148">Transform text column into a bag of counts of ngrams (sequences of consecutive words)</span></span>|
| <xref:Microsoft.ML.TextCatalog.ProduceWordBags*> | <span data-ttu-id="d6641-149">텍스트 열을 ngrams 벡터 개수 모음으로 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-149">Transform text column into a bag of counts of ngrams vector</span></span> |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedNgrams*> | <span data-ttu-id="d6641-150">텍스트 열을 해시된 ngram 개수 벡터로 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-150">Transform text column into a vector of hashed ngram counts</span></span> |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedWordBags*> | <span data-ttu-id="d6641-151">텍스트 열을 해시된 ngram 개수 모음으로 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-151">Transform text column into a bag of hashed ngram counts</span></span> |
| <xref:Microsoft.ML.TextCatalog.RemoveDefaultStopWords*>  | <span data-ttu-id="d6641-152">입력 열에서 지정된 언어의 기본 중지 단어 제거</span><span class="sxs-lookup"><span data-stu-id="d6641-152">Remove default stop words for the specified language from input columns</span></span> |
| <xref:Microsoft.ML.TextCatalog.RemoveStopWords*> | <span data-ttu-id="d6641-153">입력 열에서 지정된 중지 단어 제거</span><span class="sxs-lookup"><span data-stu-id="d6641-153">Removes specified stop words from input columns</span></span> |
| <xref:Microsoft.ML.TextCatalog.LatentDirichletAllocation*> | <span data-ttu-id="d6641-154">토픽 세트에서 문서(float 벡터로 표시됨)를 float 벡터로 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-154">Transform a document (represented as a vector of floats) into a vector of floats over a set of topics</span></span> |
| <xref:Microsoft.ML.TextCatalog.ApplyWordEmbedding*> | <span data-ttu-id="d6641-155">미리 학습된 모델을 사용하여 텍스트 토큰의 벡터를 문장 벡터로 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-155">Convert vectors of text tokens into sentence vectors using a pre-trained model</span></span> |

## <a name="image-transformations"></a><span data-ttu-id="d6641-156">이미지 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-156">Image transformations</span></span>

| <span data-ttu-id="d6641-157">변형</span><span class="sxs-lookup"><span data-stu-id="d6641-157">Transform</span></span> | <span data-ttu-id="d6641-158">정의</span><span class="sxs-lookup"><span data-stu-id="d6641-158">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale*> | <span data-ttu-id="d6641-159">이미지를 회색조로 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-159">Convert an image to grayscale</span></span> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToImage*> | <span data-ttu-id="d6641-160">픽셀의 벡터를 <xref:Microsoft.ML.Transforms.Image.ImageDataViewType>으로 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-160">Convert a vector of pixels to <xref:Microsoft.ML.Transforms.Image.ImageDataViewType></span></span> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels*> | <span data-ttu-id="d6641-161">입력 이미지의 벡터를 숫자의 벡터로 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-161">Convert pixels from input image into a vector of numbers</span></span> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*> | <span data-ttu-id="d6641-162">폴더에서 메모리로 이미지 로드</span><span class="sxs-lookup"><span data-stu-id="d6641-162">Load images from a folder into memory</span></span> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages*> | <span data-ttu-id="d6641-163">이미지 크기 조정</span><span class="sxs-lookup"><span data-stu-id="d6641-163">Resize images</span></span> |

## <a name="categorical-data-transformations"></a><span data-ttu-id="d6641-164">범주별 데이터 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-164">Categorical data transformations</span></span>

| <span data-ttu-id="d6641-165">변형</span><span class="sxs-lookup"><span data-stu-id="d6641-165">Transform</span></span> | <span data-ttu-id="d6641-166">정의</span><span class="sxs-lookup"><span data-stu-id="d6641-166">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*> | <span data-ttu-id="d6641-167">하나 이상의 텍스트 열을 [원 핫(one-hot)](https://en.wikipedia.org/wiki/One-hot) 인코딩된 벡터로 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-167">Convert one or more text columns into [one-hot](https://en.wikipedia.org/wiki/One-hot) encoded vectors</span></span> |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotHashEncoding*> | <span data-ttu-id="d6641-168">하나 이상의 텍스트 열을 해시 기반 원 핫(one-hot) 인코딩된 벡터로 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-168">Convert one more text columns into hash-based one-hot encoded vectors</span></span> |

## <a name="missing-values"></a><span data-ttu-id="d6641-169">누락 값</span><span class="sxs-lookup"><span data-stu-id="d6641-169">Missing values</span></span>

| <span data-ttu-id="d6641-170">변형</span><span class="sxs-lookup"><span data-stu-id="d6641-170">Transform</span></span> | <span data-ttu-id="d6641-171">정의</span><span class="sxs-lookup"><span data-stu-id="d6641-171">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.ExtensionsCatalog.IndicateMissingValues*> | <span data-ttu-id="d6641-172">새 부울 출력 열 만들기. 이 열의 값은 입력 열의 값이 누락된 경우 true입니다.</span><span class="sxs-lookup"><span data-stu-id="d6641-172">Create a new boolean output column, the value of which is true when the value in the input column is missing</span></span> |
| <xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*> | <span data-ttu-id="d6641-173">새 출력 열 만들기. 이 열의 값은 입력 열에 값이 없는 경우 기본값으로 설정되고, 이외의 경우에는 해당 값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6641-173">Create a new output column, the value of which is set to a default value if the value is missing from the input column, and the input value otherwise</span></span> |

## <a name="feature-selection"></a><span data-ttu-id="d6641-174">기능 선택</span><span class="sxs-lookup"><span data-stu-id="d6641-174">Feature selection</span></span>

| <span data-ttu-id="d6641-175">변형</span><span class="sxs-lookup"><span data-stu-id="d6641-175">Transform</span></span> | <span data-ttu-id="d6641-176">정의</span><span class="sxs-lookup"><span data-stu-id="d6641-176">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnCount*> | <span data-ttu-id="d6641-177">기본값이 아닌 값이 임계값보다 큰 기능 선택</span><span class="sxs-lookup"><span data-stu-id="d6641-177">Select features whose non-default values are greater than a threshold</span></span> |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnMutualInformation*> | <span data-ttu-id="d6641-178">레이블 열의 데이터가 종속성이 가장 높은 기능 선택</span><span class="sxs-lookup"><span data-stu-id="d6641-178">Select the features on which the data in the label column is most dependent</span></span> |

## <a name="custom-transformations"></a><span data-ttu-id="d6641-179">사용자 지정 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-179">Custom transformations</span></span>

| <span data-ttu-id="d6641-180">변형</span><span class="sxs-lookup"><span data-stu-id="d6641-180">Transform</span></span> | <span data-ttu-id="d6641-181">정의</span><span class="sxs-lookup"><span data-stu-id="d6641-181">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.CustomMappingCatalog.CustomMapping*> | <span data-ttu-id="d6641-182">사용자 정의 매핑을 사용하여 기존 열을 새 열로 변환</span><span class="sxs-lookup"><span data-stu-id="d6641-182">Transform existing columns onto new ones with a user-defined mapping</span></span> |
