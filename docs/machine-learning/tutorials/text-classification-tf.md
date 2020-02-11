---
title: '자습서: TensorFlow 모델을 사용하여 리뷰 감정 분석'
description: 이 자습서에서는 미리 학습된 TensorFlow 모델을 사용하여 웹 사이트 댓글의 감정을 분류하는 방법을 보여 줍니다. 이진 감정 분류자는 Visual Studio를 사용하여 개발된 C# 콘솔 애플리케이션입니다.
ms.date: 11/15/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7a6043f56a2ecaca633ba5545170f27a85a22efc
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092397"
---
# <a name="tutorial-analyze-sentiment-of-movie-reviews-using-a-pre-trained-tensorflow-model-in-mlnet"></a><span data-ttu-id="b4da5-104">자습서: ML.NET에서 미리 학습된 TensorFlow 모델을 사용하여 영화 리뷰의 감정 분석</span><span class="sxs-lookup"><span data-stu-id="b4da5-104">Tutorial: Analyze sentiment of movie reviews using a pre-trained TensorFlow model in ML.NET</span></span>

<span data-ttu-id="b4da5-105">이 자습서에서는 미리 학습된 TensorFlow 모델을 사용하여 웹 사이트 댓글의 감정을 분류하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-105">This tutorial shows you how to use a pre-trained TensorFlow model to classify sentiment in website comments.</span></span> <span data-ttu-id="b4da5-106">이진 감정 분류자는 Visual Studio를 사용하여 개발된 C# 콘솔 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-106">The binary sentiment classifier is a C# console application developed using Visual Studio.</span></span>

<span data-ttu-id="b4da5-107">이 자습서에서 사용되는 TensorFlow 모델은 IMDB 데이터베이스의 영화 리뷰를 사용하여 학습되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-107">The TensorFlow model used in this tutorial was trained using movie reviews from the IMDB database.</span></span> <span data-ttu-id="b4da5-108">애플리케이션 개발이 완료되면 영화 리뷰 텍스트를 제공할 수 있으며, 애플리케이션이 리뷰가 긍정적 또는 부정적 감정인지 여부를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-108">Once you have finished developing the application, you will be able to supply movie review text and the application will tell you whether the review has positive or negative sentiment.</span></span>

<span data-ttu-id="b4da5-109">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="b4da5-110">미리 학습된 TensorFlow 모델 로드</span><span class="sxs-lookup"><span data-stu-id="b4da5-110">Load a pre-trained TensorFlow model</span></span>
> * <span data-ttu-id="b4da5-111">웹 사이트 댓글 텍스트를 모델에 적합한 기능으로 변환</span><span class="sxs-lookup"><span data-stu-id="b4da5-111">Transform website comment text into features suitable for the model</span></span>
> * <span data-ttu-id="b4da5-112">모델로 예측 수행</span><span class="sxs-lookup"><span data-stu-id="b4da5-112">Use the model to make a prediction</span></span>

<span data-ttu-id="b4da5-113">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-113">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b4da5-114">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4da5-114">Prerequisites</span></span>

* <span data-ttu-id="b4da5-115">“.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 버전 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)</span><span class="sxs-lookup"><span data-stu-id="b4da5-115">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="setup"></a><span data-ttu-id="b4da5-116">설정</span><span class="sxs-lookup"><span data-stu-id="b4da5-116">Setup</span></span>

### <a name="create-the-application"></a><span data-ttu-id="b4da5-117">애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="b4da5-117">Create the application</span></span>

1. <span data-ttu-id="b4da5-118">"TextClassificationTF"라는 **.NET Core 콘솔 애플리케이션**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-118">Create a **.NET Core Console Application** called "TextClassificationTF".</span></span>

2. <span data-ttu-id="b4da5-119">프로젝트에서 *Data* 디렉터리를 만들어 데이터 세트 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-119">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="b4da5-120">**Microsoft.ML NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-120">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="b4da5-121">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-121">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="b4da5-122">패키지 소스로 "nuget.org"를 선택하고 **찾아보기** 탭을 선택합니다. **Microsoft.ML**을 검색하고 원하는 패키지를 선택한 다음, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-122">Choose "nuget.org" as the package source, and then select the **Browse** tab. Search for **Microsoft.ML**, select the package you want, and then select the **Install** button.</span></span> <span data-ttu-id="b4da5-123">선택한 패키지의 사용 조건에 동의하여 설치를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-123">Proceed with the installation by agreeing to the license terms for the package you choose.</span></span> <span data-ttu-id="b4da5-124">**Microsoft.ML.TensorFlow** 및 **SciSharp.TensorFlow.Redist**에 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-124">Repeat these steps for **Microsoft.ML.TensorFlow** and **SciSharp.TensorFlow.Redist**.</span></span>

### <a name="add-the-tensorflow-model-to-the-project"></a><span data-ttu-id="b4da5-125">TensorFlow 모델을 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-125">Add the TensorFlow model to the project</span></span>

> [!NOTE]
> <span data-ttu-id="b4da5-126">이 자습서의 모델은 [dotnet/machinelearning-testdata](https://github.com/dotnet/machinelearning-testdata/tree/master/Microsoft.ML.TensorFlow.TestModels/sentiment_model) GitHub 리포지토리에서 가져온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-126">The model for this tutorial is from the [dotnet/machinelearning-testdata](https://github.com/dotnet/machinelearning-testdata/tree/master/Microsoft.ML.TensorFlow.TestModels/sentiment_model) GitHub repo.</span></span> <span data-ttu-id="b4da5-127">모델은 TensorFlow SavedModel 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-127">The model is in TensorFlow SavedModel format.</span></span>

1. <span data-ttu-id="b4da5-128">[sentiment_model zip 파일](https://github.com/dotnet/samples/blob/master/machine-learning/models/textclassificationtf/sentiment_model.zip?raw=true)을 다운로드하고 압축을 해제합니다</span><span class="sxs-lookup"><span data-stu-id="b4da5-128">Download the [sentiment_model zip file](https://github.com/dotnet/samples/blob/master/machine-learning/models/textclassificationtf/sentiment_model.zip?raw=true), and unzip.</span></span>

    <span data-ttu-id="b4da5-129">zip 파일에는 다음 항목이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-129">The zip file contains:</span></span>

    * <span data-ttu-id="b4da5-130">`saved_model.pb`: TensorFlow 모델 자체입니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-130">`saved_model.pb`: the TensorFlow model itself.</span></span> <span data-ttu-id="b4da5-131">이 모델은 IMDB 리뷰 문자열의 텍스트를 나타내는 기능의 고정 길이(크기 600) 정수 배열을 사용하고, 합계가 1인 두 확률, 즉 입력 리뷰가 긍정적 감정일 확률과 입력 리뷰가 부정적 감정일 확률을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-131">The model takes a fixed length (size 600) integer array of features representing the text in an IMDB review string, and outputs two probabilities which sum to 1: the probability that the input review has positive sentiment, and the probability that the input review has negative sentiment.</span></span>
    * <span data-ttu-id="b4da5-132">`imdb_word_index.csv`: 개별 단어에서 정수 값으로의 매핑입니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-132">`imdb_word_index.csv`: a mapping from individual words to an integer value.</span></span> <span data-ttu-id="b4da5-133">이 매핑은 TensorFlow 모델에 대한 입력 기능을 생성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-133">The mapping is used to generate the input features for the TensorFlow model.</span></span>

2. <span data-ttu-id="b4da5-134">가장 안쪽의 `sentiment_model` 디렉터리의 내용을 *TextClassificationTF* 프로젝트 `sentiment_model` 디렉터리에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-134">Copy the contents of the innermost `sentiment_model` directory into your *TextClassificationTF* project `sentiment_model` directory.</span></span> <span data-ttu-id="b4da5-135">이 디렉터리에는 다음 이미지와 같이 이 자습서에 필요한 모델 및 추가 지원 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-135">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![sentiment_model 디렉터리 내용](./media/text-classification-tf/sentiment-model-files.png)

3. <span data-ttu-id="b4da5-137">솔루션 탐색기에서 `sentiment_model` 디렉터리 및 하위 디렉터리의 각 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-137">In Solution Explorer, right-click each of the files in the `sentiment_model` directory and subdirectory and select **Properties**.</span></span> <span data-ttu-id="b4da5-138">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-138">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="add-using-statements-and-global-variables"></a><span data-ttu-id="b4da5-139">Using 문 및 전역 변수 추가</span><span class="sxs-lookup"><span data-stu-id="b4da5-139">Add using statements and global variables</span></span>

1. <span data-ttu-id="b4da5-140">*Program.cs* 파일 맨 위에 다음 추가 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-140">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

   [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TextClassificationTF/Program.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="b4da5-141">저장된 모델 파일 경로와 기능 벡터 길이를 보관할 두 개의 전역 변수를 `Main` 메서드 바로 위에 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-141">Create two global variables right above the `Main` method to hold the saved model file path, and the feature vector length.</span></span>

   [!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TextClassificationTF/Program.cs#DeclareGlobalVariables "Declare global variables")]

    * <span data-ttu-id="b4da5-142">`_modelPath`는 학습된 모델의 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-142">`_modelPath` is the file path of the trained model.</span></span>
    * <span data-ttu-id="b4da5-143">`FeatureLength`는 모델에 필요한 정수 기능 배열의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-143">`FeatureLength` is the length of the integer feature array that the model is expecting.</span></span>

### <a name="model-the-data"></a><span data-ttu-id="b4da5-144">데이터 모델링</span><span class="sxs-lookup"><span data-stu-id="b4da5-144">Model the data</span></span>

<span data-ttu-id="b4da5-145">영화 리뷰는 자유 형식 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-145">Movie reviews are free form text.</span></span> <span data-ttu-id="b4da5-146">이 애플리케이션은 여러 불연속 단계에서 모델에 필요한 입력 형식으로 텍스트를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-146">Your application converts the text into the input format expected by the model in a number of discrete stages.</span></span>

<span data-ttu-id="b4da5-147">우선 텍스트를 개별 단어로 분할하고 제공된 매핑 파일을 사용하여 각 단어를 정수 인코딩으로 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-147">The first is to split the text into separate words and use the provided mapping file to map each word onto an integer encoding.</span></span> <span data-ttu-id="b4da5-148">이 변환의 결과는 문장의 단어 수에 해당하는 길이의 가변 길이 정수 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-148">The result of this transformation is a variable length integer array with a length corresponding to the number of words in the sentence.</span></span>

|<span data-ttu-id="b4da5-149">속성</span><span class="sxs-lookup"><span data-stu-id="b4da5-149">Property</span></span>| <span data-ttu-id="b4da5-150">값</span><span class="sxs-lookup"><span data-stu-id="b4da5-150">Value</span></span>|<span data-ttu-id="b4da5-151">형식</span><span class="sxs-lookup"><span data-stu-id="b4da5-151">Type</span></span>|
|-------------|-----------------------|------|
|<span data-ttu-id="b4da5-152">ReviewText</span><span class="sxs-lookup"><span data-stu-id="b4da5-152">ReviewText</span></span>|<span data-ttu-id="b4da5-153">this film is really good</span><span class="sxs-lookup"><span data-stu-id="b4da5-153">this film is really good</span></span>|<span data-ttu-id="b4da5-154">string</span><span class="sxs-lookup"><span data-stu-id="b4da5-154">string</span></span>|
|<span data-ttu-id="b4da5-155">VariableLengthFeatures</span><span class="sxs-lookup"><span data-stu-id="b4da5-155">VariableLengthFeatures</span></span>|<span data-ttu-id="b4da5-156">14,22,9,66,78,...</span><span class="sxs-lookup"><span data-stu-id="b4da5-156">14,22,9,66,78,...</span></span> |<span data-ttu-id="b4da5-157">int[]</span><span class="sxs-lookup"><span data-stu-id="b4da5-157">int[]</span></span>|

<span data-ttu-id="b4da5-158">그러면 가변 길이 기능 배열의 크기가 고정 길이 600으로 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-158">The variable length feature array is then resized to a fixed length of 600.</span></span> <span data-ttu-id="b4da5-159">이것이 TensorFlow 모델에 필요한 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-159">This is the length that the TensorFlow model expects.</span></span>

|<span data-ttu-id="b4da5-160">속성</span><span class="sxs-lookup"><span data-stu-id="b4da5-160">Property</span></span>| <span data-ttu-id="b4da5-161">값</span><span class="sxs-lookup"><span data-stu-id="b4da5-161">Value</span></span>|<span data-ttu-id="b4da5-162">형식</span><span class="sxs-lookup"><span data-stu-id="b4da5-162">Type</span></span>|
|-------------|-----------------------|------|
|<span data-ttu-id="b4da5-163">ReviewText</span><span class="sxs-lookup"><span data-stu-id="b4da5-163">ReviewText</span></span>|<span data-ttu-id="b4da5-164">this film is really good</span><span class="sxs-lookup"><span data-stu-id="b4da5-164">this film is really good</span></span>|<span data-ttu-id="b4da5-165">string</span><span class="sxs-lookup"><span data-stu-id="b4da5-165">string</span></span>|
|<span data-ttu-id="b4da5-166">VariableLengthFeatures</span><span class="sxs-lookup"><span data-stu-id="b4da5-166">VariableLengthFeatures</span></span>|<span data-ttu-id="b4da5-167">14,22,9,66,78,...</span><span class="sxs-lookup"><span data-stu-id="b4da5-167">14,22,9,66,78,...</span></span> |<span data-ttu-id="b4da5-168">int[]</span><span class="sxs-lookup"><span data-stu-id="b4da5-168">int[]</span></span>|
|<span data-ttu-id="b4da5-169">기능</span><span class="sxs-lookup"><span data-stu-id="b4da5-169">Features</span></span>|<span data-ttu-id="b4da5-170">14,22,9,66,78,...</span><span class="sxs-lookup"><span data-stu-id="b4da5-170">14,22,9,66,78,...</span></span> |<span data-ttu-id="b4da5-171">int[600]</span><span class="sxs-lookup"><span data-stu-id="b4da5-171">int[600]</span></span>|

1. <span data-ttu-id="b4da5-172">`Main` 메서드 다음에 입력 데이터에 대한 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-172">Create a class for your input data, after the `Main` method:</span></span>

    [!code-csharp[MovieReviewClass](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#MovieReviewClass "Declare movie review type")]

    <span data-ttu-id="b4da5-173">입력 데이터 클래스 `MovieReview`에는 사용자 댓글(`ReviewText`)의 `string`이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-173">The input data class, `MovieReview`, has a `string` for user comments (`ReviewText`).</span></span>

1. <span data-ttu-id="b4da5-174">`Main` 메서드 다음에 가변 길이 기능에 대한 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-174">Create a class for the variable length features, after the `Main` method:</span></span>

    [!code-csharp[VariableLengthFeatures](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#VariableLengthFeatures "Declare variable length features type")]

    <span data-ttu-id="b4da5-175">`VariableLengthFeatures` 속성에는 이를 벡터로 지정하기 위한 [VectorType](xref:Microsoft.ML.Data.VectorTypeAttribute.%23ctor%2A) 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-175">The `VariableLengthFeatures` property has a [VectorType](xref:Microsoft.ML.Data.VectorTypeAttribute.%23ctor%2A) attribute to designate it as a vector.</span></span>  <span data-ttu-id="b4da5-176">모든 벡터 요소는 같은 유형이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-176">All of the vector elements must be the same type.</span></span> <span data-ttu-id="b4da5-177">열 수가 많은 데이터 세트에서 여러 열을 단일 벡터로 로드하면 데이터 변환을 적용할 때 데이터 전달 횟수가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-177">In data sets with a large number of columns, loading multiple columns as a single vector reduces the number of data passes when you apply data transformations.</span></span>

    <span data-ttu-id="b4da5-178">이 클래스는 `ResizeFeatures` 작업에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-178">This class is used in the `ResizeFeatures` action.</span></span> <span data-ttu-id="b4da5-179">해당 속성(이 경우에는 하나뿐)의 이름은 사용자 지정 매핑 동작에 대한 _입력_으로 사용할 수 있는 DataView의 열을 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-179">The names of its properties (in this case only one) are used to indicate which columns in the DataView can be used as the _input_ to the custom mapping action.</span></span>

1. <span data-ttu-id="b4da5-180">`Main` 메서드 다음에 고정 길이 기능에 대한 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-180">Create a class for the fixed length features, after the `Main` method:</span></span>

    [!code-csharp[FixedLengthFeatures](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#FixedLengthFeatures)]

    <span data-ttu-id="b4da5-181">이 클래스는 `ResizeFeatures` 작업에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-181">This class is used in the `ResizeFeatures` action.</span></span> <span data-ttu-id="b4da5-182">해당 속성(이 경우에는 하나뿐)의 이름은 사용자 지정 매핑 동작에 대한 _출력_으로 사용할 수 있는 DataView의 열을 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-182">The names of its properties (in this case only one) are used to indicate which columns in the DataView can be used as the _output_ of the custom mapping action.</span></span>

    <span data-ttu-id="b4da5-183">`Features` 속성의 이름은 TensorFlow 모델에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-183">Note that the name of the property `Features` is determined by the TensorFlow model.</span></span> <span data-ttu-id="b4da5-184">이 속성 이름은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-184">You cannot change this property name.</span></span>

1. <span data-ttu-id="b4da5-185">`Main` 메서드 다음에 예측에 대한 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-185">Create a class for the prediction after the `Main` method:</span></span>

    [!code-csharp[Prediction](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#Prediction "Declare prediction class")]

    <span data-ttu-id="b4da5-186">`MovieReviewSentimentPrediction`은 모델 학습 후 사용되는 예측 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-186">`MovieReviewSentimentPrediction` is the prediction class used after the model training.</span></span> <span data-ttu-id="b4da5-187">`MovieReviewSentimentPrediction`에는 단일 `float` 배열(`Prediction`)과 `VectorType` 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-187">`MovieReviewSentimentPrediction` has a single `float` array (`Prediction`) and a `VectorType` attribute.</span></span>

### <a name="create-the-mlcontext-lookup-dictionary-and-action-to-resize-features"></a><span data-ttu-id="b4da5-188">MLContext, 조회 사전 및 기능 크기 조정 작업 만들기</span><span class="sxs-lookup"><span data-stu-id="b4da5-188">Create the MLContext, lookup dictionary, and action to resize features</span></span>

<span data-ttu-id="b4da5-189">[MLContext 클래스](xref:Microsoft.ML.MLContext)는 모든 ML.NET 작업의 시작 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-189">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations.</span></span> <span data-ttu-id="b4da5-190">`mlContext`를 초기화하면 모델 생성 워크플로 개체 간에 공유할 수 있는 새 ML.NET 환경이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-190">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="b4da5-191">개념적으로 Entity Framework의 `DBContext`와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-191">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

1. <span data-ttu-id="b4da5-192">`Main` 메서드의 `Console.WriteLine("Hello World!")` 줄을 다음 코드로 바꾸어 mlContext 변수를 선언하고 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-192">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the mlContext variable:</span></span>

   [!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreateMLContext "Create the ML Context")]

1. <span data-ttu-id="b4da5-193">다음 표에 표시된 것처럼 [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A) 메서드를 사용하여 파일에서 매핑 데이터를 로드하여 단어를 정수로 인코딩하는 사전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-193">Create a dictionary to encode words as integers by using the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A) method to load mapping data from a file, as seen in the following table:</span></span>

    |<span data-ttu-id="b4da5-194">단어</span><span class="sxs-lookup"><span data-stu-id="b4da5-194">Word</span></span>     |<span data-ttu-id="b4da5-195">Index</span><span class="sxs-lookup"><span data-stu-id="b4da5-195">Index</span></span>    |
    |---------|---------|
    |<span data-ttu-id="b4da5-196">kids</span><span class="sxs-lookup"><span data-stu-id="b4da5-196">kids</span></span>     |  <span data-ttu-id="b4da5-197">362</span><span class="sxs-lookup"><span data-stu-id="b4da5-197">362</span></span>    |
    |<span data-ttu-id="b4da5-198">want</span><span class="sxs-lookup"><span data-stu-id="b4da5-198">want</span></span>     |  <span data-ttu-id="b4da5-199">181</span><span class="sxs-lookup"><span data-stu-id="b4da5-199">181</span></span>    |
    |<span data-ttu-id="b4da5-200">wrong</span><span class="sxs-lookup"><span data-stu-id="b4da5-200">wrong</span></span>    |  <span data-ttu-id="b4da5-201">355</span><span class="sxs-lookup"><span data-stu-id="b4da5-201">355</span></span>    |
    |<span data-ttu-id="b4da5-202">effects</span><span class="sxs-lookup"><span data-stu-id="b4da5-202">effects</span></span>  |  <span data-ttu-id="b4da5-203">302</span><span class="sxs-lookup"><span data-stu-id="b4da5-203">302</span></span>    |
    |<span data-ttu-id="b4da5-204">feeling</span><span class="sxs-lookup"><span data-stu-id="b4da5-204">feeling</span></span>  |  <span data-ttu-id="b4da5-205">547</span><span class="sxs-lookup"><span data-stu-id="b4da5-205">547</span></span>    |

    <span data-ttu-id="b4da5-206">아래 코드를 추가하여 조회 맵을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-206">Add the code below to create the lookup map:</span></span>

    [!code-csharp[CreateLookupMap](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreateLookupMap)]

1. <span data-ttu-id="b4da5-207">다음 코드 줄을 사용하여 가변 길이 단어 정수 배열의 크기를 고정 크기 정수 배열로 조정하는 `Action`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-207">Add an `Action` to resize the variable length word integer array to an integer array of fixed size, with the next lines of code:</span></span>

   [!code-csharp[ResizeFeatures](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#ResizeFeatures)]

## <a name="load-the-pre-trained-tensorflow-model"></a><span data-ttu-id="b4da5-208">미리 학습된 TensorFlow 모델 로드</span><span class="sxs-lookup"><span data-stu-id="b4da5-208">Load the pre-trained TensorFlow model</span></span>

1. <span data-ttu-id="b4da5-209">코드를 추가하여 TensorFlow 모델을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-209">Add code to load the TensorFlow model:</span></span>

    [!code-csharp[LoadTensorFlowModel](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#LoadTensorFlowModel)]

    <span data-ttu-id="b4da5-210">모델이 로드되면 해당 입력 및 출력 스키마를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-210">Once the model is loaded, you can extract its input and output schema.</span></span> <span data-ttu-id="b4da5-211">스키마는 관심 및 학습 전용으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-211">The schemas are displayed for interest and learning only.</span></span> <span data-ttu-id="b4da5-212">최종 애플리케이션이 작동하기 위해 이 코드가 필요하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-212">You do not need this code for the final application to function:</span></span>

    [!code-csharp[GetModelSchema](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#GetModelSchema)]

    <span data-ttu-id="b4da5-213">입력 스키마는 정수 인코딩 단어의 고정 길이 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-213">The input schema is the fixed-length array of integer encoded words.</span></span> <span data-ttu-id="b4da5-214">출력 스키마는 리뷰의 감정이 부정적인지 또는 긍정적인지를 나타내는 확률의 부동 소수점 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-214">The output schema is a float array of probabilities indicating whether a review's sentiment is negative, or positive .</span></span> <span data-ttu-id="b4da5-215">긍정적 감정의 확률과 부정적 감정의 확률은 보수이므로 이들 값의 합은 1입니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-215">These values sum to 1, as the probability of being positive is the complement of the probability of the sentiment being negative.</span></span>

## <a name="create-the-mlnet-pipeline"></a><span data-ttu-id="b4da5-216">ML.NET 파이프라인 만들기</span><span class="sxs-lookup"><span data-stu-id="b4da5-216">Create the ML.NET pipeline</span></span>

1. <span data-ttu-id="b4da5-217">파이프라인을 만들고 다음 코드 줄과 같이 [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) 변환을 사용하여 텍스트를 단어로 분할해 입력 텍스트를 단어로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-217">Create the pipeline and split the input text into words using [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) transform to break the text into words as the next line of code:</span></span>

   [!code-csharp[TokenizeIntoWords](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#TokenizeIntoWords)]

   <span data-ttu-id="b4da5-218">[TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) 변환은 공백을 사용하여 텍스트/문자열을 단어로 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-218">The [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) transform uses spaces to parse the text/string into words.</span></span> <span data-ttu-id="b4da5-219">새 열을 만들고 각 입력 문자열을 사용자 정의 구분 기호를 기반으로 하는 부분 문자열의 벡터로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-219">It creates a new column and splits each input string to a vector of substrings based on the user-defined separator.</span></span>

1. <span data-ttu-id="b4da5-220">위에서 선언한 조회 테이블을 사용하여 단어를 해당 정수 인코딩으로 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-220">Map the words onto their integer encoding using the lookup table that you declared above:</span></span>

    [!code-csharp[MapValue](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#MapValue)]

1. <span data-ttu-id="b4da5-221">가변 길이 정수 인코딩의 크기를 모델에 필요한 고정 길이에 맞게 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-221">Resize the variable length integer encodings to the fixed-length one required by the model:</span></span>

    [!code-csharp[CustomMapping](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CustomMapping)]

1. <span data-ttu-id="b4da5-222">로드된 TensorFlow 모델을 사용하여 입력을 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-222">Classify the input with the loaded TensorFlow model:</span></span>

    [!code-csharp[ScoreTensorFlowModel](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#ScoreTensorFlowModel)]

    <span data-ttu-id="b4da5-223">TensorFlow 모델 출력은 `Prediction/Softmax`입니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-223">The TensorFlow model output is called `Prediction/Softmax`.</span></span> <span data-ttu-id="b4da5-224">`Prediction/Softmax`은 TensorFlow 모델에 의해 결정된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-224">Note that the name `Prediction/Softmax` is determined by the TensorFlow model.</span></span> <span data-ttu-id="b4da5-225">이 이름은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-225">You cannot change this name.</span></span>

1. <span data-ttu-id="b4da5-226">출력 예측에 대한 새 열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-226">Create a new column for the output prediction:</span></span>

    [!code-csharp[SnippetCopyColumns](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#SnippetCopyColumns)]

    <span data-ttu-id="b4da5-227">`Prediction/Softmax` 열을 C# 클래스에서 속성으로 사용할 수 있는 이름을 가진 열로 복사해야 합니다. `Prediction`.</span><span class="sxs-lookup"><span data-stu-id="b4da5-227">You need to copy the `Prediction/Softmax` column into one with a name that can be used as a property in a C# class: `Prediction`.</span></span> <span data-ttu-id="b4da5-228">C# 속성 이름에 `/` 문자는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-228">The `/` character is not allowed in a C# property name.</span></span>

## <a name="create-the-mlnet-model-from-the-pipeline"></a><span data-ttu-id="b4da5-229">파이프라인에서 ML.NET 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="b4da5-229">Create the ML.NET model from the pipeline</span></span>

1. <span data-ttu-id="b4da5-230">코드를 추가하여 파이프라인에서 모델을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-230">Add the code to create the model from the pipeline:</span></span>

    [!code-csharp[SnippetCreateModel](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#SnippetCreateModel)]

    <span data-ttu-id="b4da5-231">ML.NET 모델은 `Fit` 메서드를 호출하여 파이프라인의 추정기 체인에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-231">An ML.NET model is created from the chain of estimators in the pipeline by calling the `Fit` method.</span></span> <span data-ttu-id="b4da5-232">이 경우에는 TensorFlow 모델이 이미 학습되었으므로 모델을 만들기 위해 데이터 맞춤을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-232">In this case, we are not fitting any data to create the model, as the TensorFlow model has already been previously trained.</span></span> <span data-ttu-id="b4da5-233">`Fit` 메서드의 요구 사항을 충족하기 위해 빈 데이터 보기 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-233">We supply an empty data view object to satisfy the requirements of the `Fit` method.</span></span>

## <a name="use-the-model-to-make-a-prediction"></a><span data-ttu-id="b4da5-234">모델로 예측 수행</span><span class="sxs-lookup"><span data-stu-id="b4da5-234">Use the model to make a prediction</span></span>

1. <span data-ttu-id="b4da5-235">`Main` 메서드 아래에 `PredictSentiment` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-235">Add the `PredictSentiment` method below the `Main` method:</span></span>

    ```csharp
    public static void PredictSentiment(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. <span data-ttu-id="b4da5-236">`PredictSentiment()` 메서드의 첫째 줄과 같이 다음 코드를 추가하여 `PredictionEngine`을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-236">Add the following code to create the `PredictionEngine` as the first line in the `PredictSentiment()` method:</span></span>

    [!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreatePredictionEngine)]

    <span data-ttu-id="b4da5-237">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602)은 데이터의 단일 인스턴스에 대한 예측을 수행할 수 있는 편리한 API입니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-237">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="b4da5-238">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)은 스레드로부터 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-238">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="b4da5-239">단일 스레드 또는 프로토타입 환경에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-239">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="b4da5-240">프로덕션 환경에서 성능 및 스레드 보안을 개선하려면 `PredictionEnginePool` 서비스를 사용합니다. 이 서비스는 애플리케이션 전체에서 사용할 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) 개체의 [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-240">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="b4da5-241">[ASP.NET Core Web API에서 `PredictionEnginePool`을 사용하는 방법](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application)에 대한 이 가이드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b4da5-241">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

    > [!NOTE]
    > <span data-ttu-id="b4da5-242">`PredictionEnginePool` 서비스 확장은 현재 미리 보기 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-242">`PredictionEnginePool` service extension is currently in preview.</span></span>

1. <span data-ttu-id="b4da5-243">`MovieReview` 인스턴스를 만들어 댓글을 추가하여 `Predict()` 메서드에서 학습된 모델의 예측을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-243">Add a comment to test the trained model's prediction in the `Predict()` method by creating an instance of `MovieReview`:</span></span>

    [!code-csharp[CreateTestData](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CreateTestData)]

1. <span data-ttu-id="b4da5-244">`PredictSentiment()` 메서드의 다음 코드 줄을 추가하여 테스트 댓글 데이터를 `Prediction Engine`에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-244">Pass the test comment data to the `Prediction Engine` by adding the next lines of code in the `PredictSentiment()` method:</span></span>

    [!code-csharp[Predict](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#Predict)]

1. <span data-ttu-id="b4da5-245">[Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) 함수는 단일 데이터 행에 대한 예측을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-245">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data:</span></span>

    |<span data-ttu-id="b4da5-246">속성</span><span class="sxs-lookup"><span data-stu-id="b4da5-246">Property</span></span>| <span data-ttu-id="b4da5-247">값</span><span class="sxs-lookup"><span data-stu-id="b4da5-247">Value</span></span>|<span data-ttu-id="b4da5-248">형식</span><span class="sxs-lookup"><span data-stu-id="b4da5-248">Type</span></span>|
    |-------------|-----------------------|------|
    |<span data-ttu-id="b4da5-249">예측</span><span class="sxs-lookup"><span data-stu-id="b4da5-249">Prediction</span></span>|<span data-ttu-id="b4da5-250">[0.5459937, 0.454006255]</span><span class="sxs-lookup"><span data-stu-id="b4da5-250">[0.5459937, 0.454006255]</span></span>|<span data-ttu-id="b4da5-251">float[]</span><span class="sxs-lookup"><span data-stu-id="b4da5-251">float[]</span></span>|

1. <span data-ttu-id="b4da5-252">다음 코드를 사용하여 감정 예측을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-252">Display sentiment prediction using the following code:</span></span>

    [!code-csharp[DisplayPredictions](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#DisplayPredictions)]

1. <span data-ttu-id="b4da5-253">`Main` 메서드의 끝에 `PredictSentiment` 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-253">Add a call to `PredictSentiment` at the end of the `Main` method:</span></span>

    [!code-csharp[CallPredictSentiment](~/samples/machine-learning/tutorials/TextClassificationTF/Program.cs#CallPredictSentiment)]

## <a name="results"></a><span data-ttu-id="b4da5-254">결과</span><span class="sxs-lookup"><span data-stu-id="b4da5-254">Results</span></span>

<span data-ttu-id="b4da5-255">애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-255">Build and run your application.</span></span>

<span data-ttu-id="b4da5-256">다음과 같은 결과가 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-256">Your results should be similar to the following.</span></span> <span data-ttu-id="b4da5-257">처리 중 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-257">During processing, messages are displayed.</span></span> <span data-ttu-id="b4da5-258">경고 또는 메시지 처리를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-258">You may see warnings, or processing messages.</span></span> <span data-ttu-id="b4da5-259">이해하기 쉽도록 이러한 메시지는 다음 결과에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-259">These messages have been removed from the following results for clarity.</span></span>

```console
Number of classes: 2
Is sentiment/review positive ? Yes
```

<span data-ttu-id="b4da5-260">지금까지</span><span class="sxs-lookup"><span data-stu-id="b4da5-260">Congratulations!</span></span> <span data-ttu-id="b4da5-261">이제 ML.NET에서 미리 학습된 `TensorFlow` 모델을 재사용하여 메시지 감정을 분류하고 예측하기 위한 기계 학습 모델을 성공적으로 빌드했습니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-261">You've now successfully built a machine learning model for classifying and predicting messages sentiment by reusing a pre-trained `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="b4da5-262">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-262">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF) repository.</span></span>

<span data-ttu-id="b4da5-263">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="b4da5-263">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="b4da5-264">미리 학습된 TensorFlow 모델 로드</span><span class="sxs-lookup"><span data-stu-id="b4da5-264">Load a pre-trained TensorFlow model</span></span>
> * <span data-ttu-id="b4da5-265">웹 사이트 댓글 텍스트를 모델에 적합한 기능으로 변환</span><span class="sxs-lookup"><span data-stu-id="b4da5-265">Transform website comment text into features suitable for the model</span></span>
> * <span data-ttu-id="b4da5-266">모델로 예측 수행</span><span class="sxs-lookup"><span data-stu-id="b4da5-266">Use the model to make a prediction</span></span>
