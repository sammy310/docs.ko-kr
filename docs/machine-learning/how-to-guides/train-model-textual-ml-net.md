---
title: 텍스트 데이터의 모델 학습에 대한 기능 엔지니어링 적용 - ML.NET
description: ML.NET를 사용하여 텍스트 데이터의 모델 학습에 대한 기능 엔지니어링을 적용하는 방법 알아보기
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 8733db281dbc60ae3f4ac0c139c482b39089f2b8
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57680076"
---
# <a name="apply-feature-engineering-for-machine-learning-model-training-on-textual-data-with-mlnet"></a><span data-ttu-id="55feb-103">ML.NET를 사용하여 텍스트 데이터의 기계 학습 모델 학습에 대한 기능 엔지니어링 적용</span><span class="sxs-lookup"><span data-stu-id="55feb-103">Apply feature engineering for machine learning model training on textual data with ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="55feb-104">이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55feb-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="55feb-105">자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55feb-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="55feb-106">이 방법과 관련 샘플에서는 현재 **ML.NET 버전 0.10**을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55feb-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="55feb-107">자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55feb-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="55feb-108">모든 ML.NET `learners`가 `float vector`로 기능을 사용하므로 비부동 데이터를 `float` 데이터 형식으로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55feb-108">You need to convert any non float data to `float` data types since all ML.NET `learners` expect features as a `float vector`.</span></span>

<span data-ttu-id="55feb-109">텍스트 데이터에 대해 알아보려면 텍스트 기능을 추출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55feb-109">To learn on textual data, you need to extract text features.</span></span> <span data-ttu-id="55feb-110">ML.NET에는 몇 가지 기본적인 텍스트 기능 추출 메커니즘이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55feb-110">ML.NET has some basic text feature extraction mechanisms:</span></span>

- <span data-ttu-id="55feb-111">`Text normalization`(문장 부호, 분음 부호 제거, 소문자 전환 등)</span><span class="sxs-lookup"><span data-stu-id="55feb-111">`Text normalization` (removing punctuation, diacritics, switching to lowercase etc.)</span></span>
- <span data-ttu-id="55feb-112">`Separator-based tokenization`.</span><span class="sxs-lookup"><span data-stu-id="55feb-112">`Separator-based tokenization`.</span></span>
- <span data-ttu-id="55feb-113">`Stopword` 제거</span><span class="sxs-lookup"><span data-stu-id="55feb-113">`Stopword` removal.</span></span>
- <span data-ttu-id="55feb-114">`Ngram` 및 `skip-gram` 추출</span><span class="sxs-lookup"><span data-stu-id="55feb-114">`Ngram` and `skip-gram` extraction.</span></span>
- <span data-ttu-id="55feb-115">`TF-IDF` 크기 재조정</span><span class="sxs-lookup"><span data-stu-id="55feb-115">`TF-IDF` rescaling.</span></span>
- <span data-ttu-id="55feb-116">`Bag of words` 전환</span><span class="sxs-lookup"><span data-stu-id="55feb-116">`Bag of words` conversion.</span></span>

<span data-ttu-id="55feb-117">다음 예제에서는 [Wikipedia detox 데이터 세트](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv)를 사용하는 ML.NET 텍스트 기능 추출 메커니즘을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="55feb-117">The following example demonstrates ML.NET text feature extraction mechanisms using the [Wikipedia detox dataset](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv):</span></span>

```console
Sentiment   SentimentText
1   Stop trolling, zapatancas, calling me a liar merely demonstartes that you arer Zapatancas. You may choose to chase every legitimate editor from this site and ignore me but I am an editor with a record that isnt 99% trolling and therefore my wishes are not to be completely ignored by a sockpuppet like yourself. The consensus is overwhelmingly against you and your trolling lover Zapatancas,  
1   ::::: Why are you threatening me? I'm not being disruptive, its you who is being disruptive.   
0   " *::Your POV and propaganda pushing is dully noted. However listing interesting facts in a netral and unacusitory tone is not POV. You seem to be confusing Censorship with POV monitoring. I see nothing POV expressed in the listing of intersting facts. If you want to contribute more facts or edit wording of the cited fact to make them sound more netral then go ahead. No need to CENSOR interesting factual information. "
0   ::::::::This is a gross exaggeration. Nobody is setting a kangaroo court. There was a simple addition concerning the airline. It is the only one disputed here.   
```

```csharp
// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(new[] 
    {
        new TextLoader.Column("IsToxic", DataKind.BL, 0),
        new TextLoader.Column("Message", DataKind.TX, 1),
    },
    hasHeader: true
);

// Read the data.
var data = reader.Read(dataPath);

// Inspect the message texts that are read from the file.
var messageTexts = data.GetColumn<string>(mlContext, "Message").Take(20).ToArray();

// Apply various kinds of text operations supported by ML.NET.
var pipeline =
    // One-stop shop to run the full text featurization.
    mlContext.Transforms.Text.FeaturizeText("TextFeatures", "Message")

    // Normalize the message for later transforms
    .Append(mlContext.Transforms.Text.NormalizeText("NormalizedMessage", "Message"))

    // NLP pipeline 1: bag of words.
    .Append(new WordBagEstimator(mlContext, "BagOfWords", "NormalizedMessage"))

    // NLP pipeline 2: bag of bigrams, using hashes instead of dictionary indices.
    .Append(new WordHashBagEstimator(mlContext, "BagOfBigrams","NormalizedMessage", 
                ngramLength: 2, allLengths: false))

    // NLP pipeline 3: bag of tri-character sequences with TF-IDF weighting.
    .Append(mlContext.Transforms.Text.TokenizeCharacters("MessageChars", "Message"))
    .Append(new NgramExtractingEstimator(mlContext, "BagOfTrichar", "MessageChars", 
                ngramLength: 3, weighting: NgramExtractingEstimator.WeightingCriteria.TfIdf))

    // NLP pipeline 4: word embeddings.
    .Append(mlContext.Transforms.Text.TokenizeWords("TokenizedMessage", "NormalizedMessage"))
    .Append(mlContext.Transforms.Text.ExtractWordEmbeddings("Embeddings", "TokenizedMessage",
                WordEmbeddingsExtractingTransformer.PretrainedModelKind.GloVeTwitter25D));

// Let's train our pipeline, and then apply it to the same data.
// Note that even on a small dataset of 70KB the pipeline above can take up to a minute to completely train.
var transformedData = pipeline.Fit(data).Transform(data);

// Inspect some columns of the resulting dataset.
var embeddings = transformedData.GetColumn<float[]>(mlContext, "Embeddings").Take(10).ToArray();
var unigrams = transformedData.GetColumn<float[]>(mlContext, "BagOfWords").Take(10).ToArray();
```
