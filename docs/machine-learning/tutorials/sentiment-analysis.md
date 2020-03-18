---
title: '자습서: 웹 사이트 주석 분석 -이진 분류'
description: 이 자습서에서는 웹 사이트 주석에서 감정을 분류하고 적절한 조치를 취하는 .NET Core 콘솔 애플리케이션을 만드는 방법을 보여 줍니다. 감정 이진 분류자는 Visual Studio에서 C#을 사용합니다.
ms.date: 09/30/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 47b9a9fe37cbcacab3797ed7fb1398b0c524d746
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "78241132"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-with-binary-classification-in-mlnet"></a><span data-ttu-id="8f957-104">자습서: ML.NET에서 이진 분류를 사용하여 웹 사이트 주석의 감정 분석</span><span class="sxs-lookup"><span data-stu-id="8f957-104">Tutorial: Analyze sentiment of website comments with binary classification in ML.NET</span></span>

<span data-ttu-id="8f957-105">이 자습서에서는 웹 사이트 주석에서 감정을 분류하고 적절한 조치를 취하는 .NET Core 콘솔 애플리케이션을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-105">This tutorial shows you how to create a .NET Core console application that classifies sentiment from website comments and takes the appropriate action.</span></span> <span data-ttu-id="8f957-106">이 감정 이진 분류자는 Visual Studio 2017에서 C#을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-106">The binary sentiment classifier uses C# in Visual Studio 2017.</span></span>

<span data-ttu-id="8f957-107">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="8f957-108">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="8f957-108">Create a console application</span></span>
> - <span data-ttu-id="8f957-109">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="8f957-109">Prepare data</span></span>
> - <span data-ttu-id="8f957-110">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="8f957-110">Load the data</span></span>
> - <span data-ttu-id="8f957-111">모델 빌드 및 학습</span><span class="sxs-lookup"><span data-stu-id="8f957-111">Build and train the model</span></span>
> - <span data-ttu-id="8f957-112">모델 평가</span><span class="sxs-lookup"><span data-stu-id="8f957-112">Evaluate the model</span></span>
> - <span data-ttu-id="8f957-113">모델로 예측 수행</span><span class="sxs-lookup"><span data-stu-id="8f957-113">Use the model to make a prediction</span></span>
> - <span data-ttu-id="8f957-114">결과 보기</span><span class="sxs-lookup"><span data-stu-id="8f957-114">See the results</span></span>

<span data-ttu-id="8f957-115">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-115">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8f957-116">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f957-116">Prerequisites</span></span>

- <span data-ttu-id="8f957-117">“.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 버전 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)</span><span class="sxs-lookup"><span data-stu-id="8f957-117">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed</span></span>

- <span data-ttu-id="8f957-118">[UCI Sentiment Labeled Sentences 데이터 세트](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)(zip 파일)</span><span class="sxs-lookup"><span data-stu-id="8f957-118">[UCI Sentiment Labeled Sentences dataset](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (ZIP file)</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="8f957-119">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="8f957-119">Create a console application</span></span>

1. <span data-ttu-id="8f957-120">"SentimentAnalysis"라고 하는 **.NET Core 콘솔 애플리케이션**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-120">Create a **.NET Core Console Application** called "SentimentAnalysis".</span></span>

2. <span data-ttu-id="8f957-121">프로젝트에서 *Data* 디렉터리를 만들어 데이터 세트 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-121">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="8f957-122">**Microsoft.ML NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="8f957-123">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="8f957-124">패키지 소스로 "nuget.org"를 선택하고 **찾아보기** 탭을 선택합니다. **Microsoft.ML**을 검색하고 원하는 패키지를 선택한 다음, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-124">Choose "nuget.org" as the package source, and then select the **Browse** tab. Search for **Microsoft.ML**, select the package you want, and then select the **Install** button.</span></span> <span data-ttu-id="8f957-125">선택한 패키지의 사용 조건에 동의하여 설치를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-125">Proceed with the installation by agreeing to the license terms for the package you choose.</span></span> <span data-ttu-id="8f957-126">**Microsoft.ML.FastTree** NuGet 패키지에 대해 동일한 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-126">Do the same for the **Microsoft.ML.FastTree** NuGet package.</span></span>

## <a name="prepare-your-data"></a><span data-ttu-id="8f957-127">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="8f957-127">Prepare your data</span></span>

> [!NOTE]
> <span data-ttu-id="8f957-128">이 자습서의 데이터 세트는 ‘From Group to Individual Labels using Deep Features’(Kotzias</span><span class="sxs-lookup"><span data-stu-id="8f957-128">The datasets for this tutorial are from the 'From Group to Individual Labels using Deep Features', Kotzias et.</span></span> <span data-ttu-id="8f957-129">외,</span><span class="sxs-lookup"><span data-stu-id="8f957-129">al,.</span></span> <span data-ttu-id="8f957-130">KDD 2015)에서 제공되고 UCI Machine Learning Repository(Dua, D. 및 Karra Taniskidou, E. (2017))에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-130">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="8f957-131">UCI Machine Learning Repository[http://archive.ics.uci.edu/ml ].</span><span class="sxs-lookup"><span data-stu-id="8f957-131">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="8f957-132">Irvine, CA: University of California, School of Information and Computer Science.</span><span class="sxs-lookup"><span data-stu-id="8f957-132">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

1. <span data-ttu-id="8f957-133">[UCI Sentiment Labeled Sentences 데이터 세트 ZIP 파일](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)을 다운로드하여 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-133">Download [UCI Sentiment Labeled Sentences dataset ZIP file](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip.</span></span>

2. <span data-ttu-id="8f957-134">만든 *Data* 디렉터리에 `yelp_labelled.txt` 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-134">Copy the `yelp_labelled.txt` file into the *Data* directory you created.</span></span>

3. <span data-ttu-id="8f957-135">솔루션 탐색기에서 `yelp_labeled.txt` 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-135">In Solution Explorer, right-click the `yelp_labeled.txt` file and select **Properties**.</span></span> <span data-ttu-id="8f957-136">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-136">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="8f957-137">클래스 만들기 및 경로 정의</span><span class="sxs-lookup"><span data-stu-id="8f957-137">Create classes and define paths</span></span>

1. <span data-ttu-id="8f957-138">*Program.cs* 파일 맨 위에 다음 추가 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-138">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="8f957-139">`Main` 메서드 바로 위의 줄에 다음 코드를 추가하여 최근에 다운로드한 파일을 유지하는 필드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-139">Add the following code to the line right above the `Main` method, to create a field to hold the recently downloaded dataset file path:</span></span>

    [!code-csharp[Declare global variables](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

1. <span data-ttu-id="8f957-140">이제 입력 데이터 및 예측에 대한 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-140">Next, create classes for your input data and predictions.</span></span> <span data-ttu-id="8f957-141">새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-141">Add a new class to your project:</span></span>

    - <span data-ttu-id="8f957-142">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-142">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

    - <span data-ttu-id="8f957-143">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentData.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-143">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="8f957-144">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-144">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="8f957-145">*SentimentData.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-145">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="8f957-146">다음 `using` 문을 *SentimentData.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-146">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

    [!code-csharp[AddUsings](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/SentimentData.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="8f957-147">기존 클래스 정의를 제거하고 두 개의 클래스 `SentimentData` 및 `SentimentPrediction`가 있는 다음 코드를 *SentimentData.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-147">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

    [!code-csharp[DeclareTypes](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/SentimentData.cs#DeclareTypes "Declare data record types")]

### <a name="how-the-data-was-prepared"></a><span data-ttu-id="8f957-148">데이터를 준비하는 방법</span><span class="sxs-lookup"><span data-stu-id="8f957-148">How the data was prepared</span></span>

<span data-ttu-id="8f957-149">입력 데이터 세트 클래스 `SentimentData`는 사용자 주석에 대한 `string`(`SentimentText`) 및 감정에 대해 1(긍정) 또는 0(부정) 값을 갖는 `bool`(`Sentiment`) 값을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-149">The input dataset class, `SentimentData`, has a `string` for user comments (`SentimentText`) and a `bool` (`Sentiment`) value of either 1 (positive) or 0 (negative) for sentiment.</span></span> <span data-ttu-id="8f957-150">두 필드에는 각 필드의 데이터 파일 순서를 설명하는 [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) 특성이 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-150">Both fields have [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attributes attached to them, which describes the data file order of each field.</span></span>  <span data-ttu-id="8f957-151">또한 `Sentiment` 속성에는 `Label` 필드로 지정하는 [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-151">In addition, the `Sentiment` property has a [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) attribute to designate it as the `Label` field.</span></span> <span data-ttu-id="8f957-152">다음 예제 파일에는 머리글 행이 없고 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-152">The following example file doesn't have a header row, and looks like this:</span></span>

|<span data-ttu-id="8f957-153">SentimentText</span><span class="sxs-lookup"><span data-stu-id="8f957-153">SentimentText</span></span>                         |<span data-ttu-id="8f957-154">감정(레이블)</span><span class="sxs-lookup"><span data-stu-id="8f957-154">Sentiment (Label)</span></span> |
|--------------------------------------|----------|
|<span data-ttu-id="8f957-155">웨이트리스의 서비스가 좀 느렸습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-155">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="8f957-156">0</span><span class="sxs-lookup"><span data-stu-id="8f957-156">0</span></span>     |
|<span data-ttu-id="8f957-157">모양이 별로 였습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-157">Crust is not good.</span></span>                    |    <span data-ttu-id="8f957-158">0</span><span class="sxs-lookup"><span data-stu-id="8f957-158">0</span></span>     |
|<span data-ttu-id="8f957-159">우와... 여기가 좋았습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-159">Wow... Loved this place.</span></span>              |    <span data-ttu-id="8f957-160">1</span><span class="sxs-lookup"><span data-stu-id="8f957-160">1</span></span>     |
|<span data-ttu-id="8f957-161">서비스가 매우 신속합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-161">Service was very prompt.</span></span>              |    <span data-ttu-id="8f957-162">1</span><span class="sxs-lookup"><span data-stu-id="8f957-162">1</span></span>     |

<span data-ttu-id="8f957-163">`SentimentPrediction`은 모델 학습 후에 사용되는 예측 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-163">`SentimentPrediction` is the prediction class used after model training.</span></span> <span data-ttu-id="8f957-164">출력 예측과 함께 입력 `SentimentText`를 표시할 수 있도록 `SentimentData`에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-164">It inherits from `SentimentData` so that the input `SentimentText` can be displayed along with the output prediction.</span></span> <span data-ttu-id="8f957-165">`Prediction` 부울은 새 입력 `SentimentText`와 함께 제공될 때 모델이 예측하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-165">The `Prediction` boolean is the value that the model predicts when supplied with new input `SentimentText`.</span></span>

<span data-ttu-id="8f957-166">출력 클래스 `SentimentPrediction`에는 `Score`(모델에서 계산한 원시 점수) 및 `Probability`(긍정적인 감정이 있는 텍스트의 가능성에 따라 조정된 점수)가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-166">The output class `SentimentPrediction` contains two other properties calculated by the model: `Score` - the raw score calculated by the model, and `Probability` - the score calibrated to the likelihood of the text having positive sentiment.</span></span>

<span data-ttu-id="8f957-167">이 자습서에서 가장 중요한 속성은 `Prediction`입니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-167">For this tutorial, the most important property is `Prediction`.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="8f957-168">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="8f957-168">Load the data</span></span>

<span data-ttu-id="8f957-169">ML.NET의 데이터는 [IDataView 클래스](xref:Microsoft.ML.IDataView)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-169">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="8f957-170">`IDataView`는 표 형식 데이터(숫자 및 텍스트)를 유연하고 효율적으로 설명하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-170">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="8f957-171">데이터를 텍스트 파일 또는 실시간(예: SQL 데이터베이스 또는 로그 파일)에서 `IDataView` 개체로 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-171">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="8f957-172">[MLContext 클래스](xref:Microsoft.ML.MLContext)는 모든 ML.NET 작업의 시작 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-172">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations.</span></span> <span data-ttu-id="8f957-173">`mlContext`를 초기화하면 모델 생성 워크플로 개체 간에 공유할 수 있는 새 ML.NET 환경이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-173">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="8f957-174">개념적으로 Entity Framework의 `DBContext`와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-174">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="8f957-175">앱을 준비한 다음, 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-175">You prepare the app, and then load data:</span></span>

1. <span data-ttu-id="8f957-176">`Main` 메서드의 `Console.WriteLine("Hello World!")` 줄을 다음 코드로 바꾸어 mlContext 변수를 선언하고 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-176">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the mlContext variable:</span></span>

    [!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreateMLContext "Create the ML Context")]

2. <span data-ttu-id="8f957-177">`Main()` 메서드에 아래 코드를 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-177">Add the following as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallLoadData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallLoadData)]

3. <span data-ttu-id="8f957-178">다음 코드를 사용하여 `Main()` 메서드 바로 뒤에 `LoadData()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-178">Create the `LoadData()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static TrainTestData LoadData(MLContext mlContext)
    {

    }
    ```

    <span data-ttu-id="8f957-179">`LoadData()` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-179">The `LoadData()` method executes the following tasks:</span></span>

    - <span data-ttu-id="8f957-180">데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-180">Loads the data.</span></span>
    - <span data-ttu-id="8f957-181">로드된 데이터 세트를 학습 및 테스트 세트로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-181">Splits the loaded dataset into train and test datasets.</span></span>
    - <span data-ttu-id="8f957-182">분할된 학습 및 테스트 데이터 세트를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-182">Returns the split train and test datasets.</span></span>

4. <span data-ttu-id="8f957-183">다음 코드를 `LoadData()` 메서드의 첫 번째 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-183">Add the following code as the first line of the `LoadData()` method:</span></span>

    [!code-csharp[LoadData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#LoadData "loading dataset")]

    <span data-ttu-id="8f957-184">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)은 데이터 스키마를 정의하고 파일에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-184">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="8f957-185">데이터 경로 변수를 가져와서 `IDataView`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-185">It takes in the data path variables and returns an `IDataView`.</span></span>

### <a name="split-the-dataset-for-model-training-and-testing"></a><span data-ttu-id="8f957-186">데이터 세트를 모델 학습 및 테스트용으로 분할</span><span class="sxs-lookup"><span data-stu-id="8f957-186">Split the dataset for model training and testing</span></span>

<span data-ttu-id="8f957-187">모델을 준비할 때는 일부 데이터 세트는 학습에, 일부 데이터 세트는 모델 정확도 테스트에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-187">When preparing a model, you use part of the dataset to train it and part of the dataset to test the model's accuracy.</span></span>

1. <span data-ttu-id="8f957-188">로드된 데이터를 필요한 데이터 세트로 분할하려면 `LoadData()` 메서드에 아래 코드를 다음 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-188">To split the loaded data into the needed datasets, add the following code as the next line in the `LoadData()` method:</span></span>

    [!code-csharp[SplitData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#SplitData "Split the Data")]

    <span data-ttu-id="8f957-189">앞의 코드는 [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) 메서드를 사용하여 로드된 데이터 세트를 학습으로 분할하고 데이터 세트를 테스트하며 [TrainTestData](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) 클래스에 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-189">The previous code uses the [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) method to split the loaded dataset into train and test datasets and return them in the [TrainTestData](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) class.</span></span> <span data-ttu-id="8f957-190">`testFraction` 매개 변수로 데이터의 테스트 집합 백분율을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-190">Specify the test set percentage of data with the `testFraction`parameter.</span></span> <span data-ttu-id="8f957-191">기본값은 10%이며, 여기서는 20%를 사용하여 데이터를 더 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-191">The default is 10%, in this case you use 20% to evaluate more data.</span></span>

2. <span data-ttu-id="8f957-192">`splitDataView` 메서드의 끝에 `LoadData()`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-192">Return the `splitDataView` at the end of the `LoadData()` method:</span></span>

    [!code-csharp[ReturnSplitData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a><span data-ttu-id="8f957-193">모델 빌드 및 학습</span><span class="sxs-lookup"><span data-stu-id="8f957-193">Build and train the model</span></span>

1. <span data-ttu-id="8f957-194">`BuildAndTrainModel` 메서드에 다음 호출을 `Main()` 메서드의 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-194">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallBuildAndTrainModel](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallBuildAndTrainModel)]

    <span data-ttu-id="8f957-195">`BuildAndTrainModel()` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-195">The `BuildAndTrainModel()` method executes the following tasks:</span></span>

    - <span data-ttu-id="8f957-196">데이터를 추출하고 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-196">Extracts and transforms the data.</span></span>
    - <span data-ttu-id="8f957-197">모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-197">Trains the model.</span></span>
    - <span data-ttu-id="8f957-198">테스트 데이터를 기반으로 감정을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-198">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="8f957-199">모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-199">Returns the model.</span></span>

2. <span data-ttu-id="8f957-200">다음 코드를 사용하여 `Main()` 메서드 바로 뒤에 `BuildAndTrainModel()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-200">Create the `BuildAndTrainModel()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
    {

    }
    ```

### <a name="extract-and-transform-the-data"></a><span data-ttu-id="8f957-201">데이터 추출 및 변환</span><span class="sxs-lookup"><span data-stu-id="8f957-201">Extract and transform the data</span></span>

1. <span data-ttu-id="8f957-202">`FeaturizeText`를 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-202">Call `FeaturizeText` as the next line of code:</span></span>

    [!code-csharp[FeaturizeText](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#FeaturizeText "Featurize the text")]

    <span data-ttu-id="8f957-203">이전 코드의 `FeaturizeText()` 메서드는 텍스트 열(`SentimentText`)을 기계 학습 알고리즘에서 사용하는 숫자 키 형식 `Features` 열로 변환하여 새 데이터 세트 열로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-203">The `FeaturizeText()` method in the previous code converts the text column (`SentimentText`) into a numeric key type `Features` column used by the machine learning algorithm and adds it as a new dataset column:</span></span>

    |<span data-ttu-id="8f957-204">SentimentText</span><span class="sxs-lookup"><span data-stu-id="8f957-204">SentimentText</span></span>                         |<span data-ttu-id="8f957-205">감정</span><span class="sxs-lookup"><span data-stu-id="8f957-205">Sentiment</span></span> |<span data-ttu-id="8f957-206">기능</span><span class="sxs-lookup"><span data-stu-id="8f957-206">Features</span></span>              |
    |--------------------------------------|----------|----------------------|
    |<span data-ttu-id="8f957-207">웨이트리스의 서비스가 좀 느렸습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-207">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="8f957-208">0</span><span class="sxs-lookup"><span data-stu-id="8f957-208">0</span></span>     |<span data-ttu-id="8f957-209">[0.76, 0.65, 0.44, …]</span><span class="sxs-lookup"><span data-stu-id="8f957-209">[0.76, 0.65, 0.44, …]</span></span> |
    |<span data-ttu-id="8f957-210">모양이 별로 였습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-210">Crust is not good.</span></span>                    |    <span data-ttu-id="8f957-211">0</span><span class="sxs-lookup"><span data-stu-id="8f957-211">0</span></span>     |<span data-ttu-id="8f957-212">[0.98, 0.43, 0.54, …]</span><span class="sxs-lookup"><span data-stu-id="8f957-212">[0.98, 0.43, 0.54, …]</span></span> |
    |<span data-ttu-id="8f957-213">우와... 여기가 좋았습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-213">Wow... Loved this place.</span></span>              |    <span data-ttu-id="8f957-214">1</span><span class="sxs-lookup"><span data-stu-id="8f957-214">1</span></span>     |<span data-ttu-id="8f957-215">[0.35, 0.73, 0.46, …]</span><span class="sxs-lookup"><span data-stu-id="8f957-215">[0.35, 0.73, 0.46, …]</span></span> |
    |<span data-ttu-id="8f957-216">서비스가 매우 신속합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-216">Service was very prompt.</span></span>              |    <span data-ttu-id="8f957-217">1</span><span class="sxs-lookup"><span data-stu-id="8f957-217">1</span></span>     |<span data-ttu-id="8f957-218">[0.39, 0, 0.75, …]</span><span class="sxs-lookup"><span data-stu-id="8f957-218">[0.39, 0, 0.75, …]</span></span>    |

### <a name="add-a-learning-algorithm"></a><span data-ttu-id="8f957-219">학습 알고리즘 추가</span><span class="sxs-lookup"><span data-stu-id="8f957-219">Add a learning algorithm</span></span>

<span data-ttu-id="8f957-220">이 앱은 항목 또는 데이터 행을 분류하는 분류 알고리즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-220">This app uses a classification algorithm that categorizes items or rows of data.</span></span> <span data-ttu-id="8f957-221">앱은 웹 사이트 주석을 긍정 또는 부정으로 분류하므로 이진 분류 작업을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-221">The app categorizes website comments as either positive or negative, so use the binary classification task.</span></span>

<span data-ttu-id="8f957-222">`BuildAndTrainModel()`의 다음 코드 줄로 다음을 추가하여 데이터 변환 정의에 기계 학습 작업을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-222">Append the machine learning task to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[SdcaLogisticRegressionBinaryTrainer](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#AddTrainer "Add a SdcaLogisticRegressionBinaryTrainer")]

<span data-ttu-id="8f957-223">[SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer)는 분류 학습 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-223">The [SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) is your classification training algorithm.</span></span> <span data-ttu-id="8f957-224">이것은 `estimator`에 추가되며, 기록 데이터에서 학습할 기능화된 `SentimentText`(`Features`) 및 `Label` 입력 매개 변수를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-224">This is appended to the `estimator` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="8f957-225">모델 학습</span><span class="sxs-lookup"><span data-stu-id="8f957-225">Train the model</span></span>

<span data-ttu-id="8f957-226">모델을 `splitTrainSet` 데이터에 맞추고 `BuildAndTrainModel()` 메서드에서 다음 줄의 코드로 다음 항목을 추가하여 학습된 모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-226">Fit the model to the `splitTrainSet` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[TrainModel](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#TrainModel "Train the model")]

<span data-ttu-id="8f957-227">[Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) 메서드는 데이터 세트를 변환하고 학습을 적용하여 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-227">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model by transforming the dataset and applying the training.</span></span>

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="8f957-228">평가에 사용하기 위해 학습된 모델 반환</span><span class="sxs-lookup"><span data-stu-id="8f957-228">Return the model trained to use for evaluation</span></span>

 <span data-ttu-id="8f957-229">`BuildAndTrainModel()` 메서드의 끝에 모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-229">Return the model at the end of the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[ReturnModel](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="8f957-230">모델 평가</span><span class="sxs-lookup"><span data-stu-id="8f957-230">Evaluate the model</span></span>

<span data-ttu-id="8f957-231">모델을 학습한 후 테스트 데이터를 사용하여 모델의 성능 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-231">After your model is trained, use your test data validate the model's performance.</span></span>

1. <span data-ttu-id="8f957-232">다음 코드로 `BuildAndTrainModel()` 바로 뒤에 `Evaluate()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-232">Create the `Evaluate()` method, just after `BuildAndTrainModel()`, with the following code:</span></span>

    ```csharp
    public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
    {

    }
    ```

    <span data-ttu-id="8f957-233">`Evaluate()` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-233">The `Evaluate()` method executes the following tasks:</span></span>

    - <span data-ttu-id="8f957-234">테스트 데이터 세트를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-234">Loads the test dataset.</span></span>
    - <span data-ttu-id="8f957-235">BinaryClassification 평가자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-235">Creates the BinaryClassification evaluator.</span></span>
    - <span data-ttu-id="8f957-236">모델을 평가하고 메트릭을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-236">Evaluates the model and creates metrics.</span></span>
    - <span data-ttu-id="8f957-237">메트릭을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-237">Displays the metrics.</span></span>

2. <span data-ttu-id="8f957-238">다음 코드를 사용하여 `BuildAndTrainModel()` 메서드 호출 바로 아래에 `Main()` 메서드의 새 메서드 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-238">Add a call to the new method from the `Main()` method, right under the `BuildAndTrainModel()` method call, using the following code:</span></span>

    [!code-csharp[CallEvaluate](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallEvaluate "Call the Evaluate method")]

3. <span data-ttu-id="8f957-239">`Evaluate()`에 다음 코드를 추가하여 `splitTestSet`데이터를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-239">Transform the `splitTestSet` data by adding the following code to `Evaluate()`:</span></span>

    [!code-csharp[PredictWithTransformer](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#TransformData "Predict using the Transformer")]

    <span data-ttu-id="8f957-240">이전 코드는 [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 메서드를 사용하여 여러 제공된 테스트 데이터 세트 입력 행에 대한 예측을 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-240">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple provided input rows of a test dataset.</span></span>

4. <span data-ttu-id="8f957-241">`Evaluate()` 메서드에서 다음 코드 줄로 다음 항목을 추가하여 모델을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-241">Evaluate the model by adding the following as the next line of code in the `Evaluate()` method:</span></span>

    [!code-csharp[ComputeMetrics](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#Evaluate "Compute Metrics")]

<span data-ttu-id="8f957-242">예측 집합(`predictions`)이 있으면 [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) 메서드는 모델을 평가하여 예측된 값을 테스트 데이터 세트의 실제 `Labels`와 비교하고, 모델 수행 방법에 대한 [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-242">Once you have the prediction set (`predictions`), the [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns a [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) object on how the model is performing.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="8f957-243">모델 유효성 검사를 위해 메트릭 표시</span><span class="sxs-lookup"><span data-stu-id="8f957-243">Displaying the metrics for model validation</span></span>

<span data-ttu-id="8f957-244">다음 코드를 사용하여 메트릭을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-244">Use the following code to display the metrics:</span></span>

[!code-csharp[DisplayMetrics](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#DisplayMetrics "Display selected metrics")]

- <span data-ttu-id="8f957-245">`Accuracy` 메트릭은 테스트 세트에서 정확한 예측의 비율인 모델 정확도를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-245">The `Accuracy` metric gets the accuracy of a model, which is the proportion of correct predictions in the test set.</span></span>

- <span data-ttu-id="8f957-246">`AreaUnderRocCurve` 메트릭은 모델이 긍정 및 부정 클래스 분류의 정확도를 자신하는 정도를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-246">The `AreaUnderRocCurve` metric indicates how confident the model is correctly classifying the positive and negative classes.</span></span> <span data-ttu-id="8f957-247">`AreaUnderRocCurve`를 가능한 근접하게 하고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-247">You want the `AreaUnderRocCurve` to be as close to one as possible.</span></span>

- <span data-ttu-id="8f957-248">`F1Score` 메트릭은 모델의 F1 점수를 가져옵니다. [정밀도](../resources/glossary.md#precision)와 [회수](../resources/glossary.md#recall) 사이의 균형을 측정한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-248">The `F1Score` metric gets the model's F1 score, which is a measure of balance between [precision](../resources/glossary.md#precision) and [recall](../resources/glossary.md#recall).</span></span>  <span data-ttu-id="8f957-249">`F1Score`를 가능한 근접하게 하고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-249">You want the `F1Score` to be as close to one as possible.</span></span>

### <a name="predict-the-test-data-outcome"></a><span data-ttu-id="8f957-250">테스트 데이터 결과 예측</span><span class="sxs-lookup"><span data-stu-id="8f957-250">Predict the test data outcome</span></span>

1. <span data-ttu-id="8f957-251">다음 코드를 사용하여 `Evaluate()` 메서드 바로 뒤에 `UseModelWithSingleItem()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-251">Create the `UseModelWithSingleItem()` method, just after the `Evaluate()` method, using the following code:</span></span>

    ```csharp
    private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="8f957-252">`UseModelWithSingleItem()` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-252">The `UseModelWithSingleItem()` method executes the following tasks:</span></span>

    - <span data-ttu-id="8f957-253">테스트 데이터의 단일 댓글을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-253">Creates a single comment of test data.</span></span>
    - <span data-ttu-id="8f957-254">테스트 데이터를 기반으로 감정을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-254">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="8f957-255">보고를 위해 테스트 데이터 및 예측을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-255">Combines test data and predictions for reporting.</span></span>
    - <span data-ttu-id="8f957-256">예측 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-256">Displays the predicted results.</span></span>

2. <span data-ttu-id="8f957-257">다음 코드를 사용하여 `Evaluate()` 메서드 호출 바로 아래에 `Main()` 메서드의 새 메서드 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-257">Add a call to the new method from the `Main()` method, right under the `Evaluate()` method call, using the following code:</span></span>

    [!code-csharp[CallUseModelWithSingleItem](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

3. <span data-ttu-id="8f957-258">다음 코드를 추가하여 `UseModelWithSingleItem()` 메서드의 첫 줄로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-258">Add the following code to create as the first line in the `UseModelWithSingleItem()` Method:</span></span>

    [!code-csharp[CreatePredictionEngine](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]

    <span data-ttu-id="8f957-259">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602)은 데이터의 단일 인스턴스에 대한 예측을 수행할 수 있는 편리한 API입니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-259">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="8f957-260">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)은 스레드로부터 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-260">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="8f957-261">단일 스레드 또는 프로토타입 환경에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-261">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="8f957-262">프로덕션 환경에서 성능 및 스레드 보안을 개선하려면 `PredictionEnginePool` 서비스를 사용합니다. 이 서비스는 애플리케이션 전체에서 사용할 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) 개체의 [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-262">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="8f957-263">[ASP.NET Core Web API에서 `PredictionEnginePool`을 사용하는 방법](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application)에 대한 이 가이드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f957-263">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

    > [!NOTE]
    > <span data-ttu-id="8f957-264">`PredictionEnginePool` 서비스 확장은 현재 미리 보기 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-264">`PredictionEnginePool` service extension is currently in preview.</span></span>

4. <span data-ttu-id="8f957-265">`SentimentData` 인스턴스를 만들어 댓글을 추가하여 `UseModelWithSingleItem()` 메서드에서 학습된 모델의 예측을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-265">Add a comment to test the trained model's prediction in the `UseModelWithSingleItem()` method by creating an instance of `SentimentData`:</span></span>

    [!code-csharp[PredictionData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

5. <span data-ttu-id="8f957-266">다음을 `UseModelWithSingleItem()` 메서드의 다음 코드 줄로 추가하여 테스트 주석 데이터를 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-266">Pass the test comment data to the [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) by adding the following as the next lines of code in the `UseModelWithSingleItem()` method:</span></span>

    [!code-csharp[Predict](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#Predict "Create a prediction of sentiment")]

    <span data-ttu-id="8f957-267">[Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) 함수는 단일 데이터 행에 대한 예측을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-267">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data.</span></span>

6. <span data-ttu-id="8f957-268">다음 코드를 사용하여 `SentimentText` 및 해당 감정 예측을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-268">Display `SentimentText` and corresponding sentiment prediction using the following code:</span></span>

    [!code-csharp[OutputPrediction](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#OutputPrediction "Display prediction output")]

## <a name="use-the-model-for-prediction"></a><span data-ttu-id="8f957-269">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="8f957-269">Use the model for prediction</span></span>

### <a name="deploy-and-predict-batch-items"></a><span data-ttu-id="8f957-270">일괄 처리 항목 배포 및 예측</span><span class="sxs-lookup"><span data-stu-id="8f957-270">Deploy and predict batch items</span></span>

1. <span data-ttu-id="8f957-271">다음 코드를 사용하여 `UseModelWithSingleItem()` 메서드 바로 뒤에 `UseModelWithBatchItems()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-271">Create the `UseModelWithBatchItems()` method, just after the `UseModelWithSingleItem()` method, using the following code:</span></span>

    ```csharp
    public static void UseModelWithBatchItems(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="8f957-272">`UseModelWithBatchItems()` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-272">The `UseModelWithBatchItems()` method executes the following tasks:</span></span>

    - <span data-ttu-id="8f957-273">일괄 처리 테스트 데이터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-273">Creates batch test data.</span></span>
    - <span data-ttu-id="8f957-274">테스트 데이터를 기반으로 감정을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-274">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="8f957-275">보고를 위해 테스트 데이터 및 예측을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-275">Combines test data and predictions for reporting.</span></span>
    - <span data-ttu-id="8f957-276">예측 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-276">Displays the predicted results.</span></span>

2. <span data-ttu-id="8f957-277">다음 코드를 사용하여 `UseModelWithSingleItem()` 메서드 호출 바로 아래에 `Main` 메서드의 새 메서드 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-277">Add a call to the new method from the `Main` method, right under the `UseModelWithSingleItem()` method call, using the following code:</span></span>

    [!code-csharp[CallPredictModelBatchItems](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallUseModelWithBatchItems "Call the CallUseModelWithBatchItems method")]

3. <span data-ttu-id="8f957-278">몇몇 댓글을 추가하여 `UseModelWithBatchItems()` 메서드에서 학습된 모델의 예측을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-278">Add some comments to test the trained model's predictions in the `UseModelWithBatchItems()` method:</span></span>

    [!code-csharp[PredictionData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreateTestIssues "Create test data for predictions")]

### <a name="predict-comment-sentiment"></a><span data-ttu-id="8f957-279">주석 감정 예측</span><span class="sxs-lookup"><span data-stu-id="8f957-279">Predict comment sentiment</span></span>

<span data-ttu-id="8f957-280">모델을 사용하여 [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 메서드를 통한 주석 데이터 감정 예측:</span><span class="sxs-lookup"><span data-stu-id="8f957-280">Use the model to predict the comment data sentiment using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method:</span></span>

[!code-csharp[Predict](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="combine-and-display-the-predictions"></a><span data-ttu-id="8f957-281">예측 결합 및 표시</span><span class="sxs-lookup"><span data-stu-id="8f957-281">Combine and display the predictions</span></span>

<span data-ttu-id="8f957-282">다음 코드를 사용하여 예측에 대한 헤더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-282">Create a header for the predictions using the following code:</span></span>

[!code-csharp[OutputHeaders](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#AddInfoMessage "Display prediction outputs")]

<span data-ttu-id="8f957-283">`SentimentPrediction`은 `SentimentData`에서 상속되므로 `Transform()` 메서드가 예측된 필드로 `SentimentText`를 입력했습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-283">Because `SentimentPrediction` is inherited from `SentimentData`, the `Transform()` method populated `SentimentText` with the predicted fields.</span></span> <span data-ttu-id="8f957-284">ML.NET 프로세스를 처리하면서 각 구성 요소가 열을 추가하므로 결과를 쉽게 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-284">As the ML.NET process processes, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#DisplayResults "Display the predictions")]

## <a name="results"></a><span data-ttu-id="8f957-285">결과</span><span class="sxs-lookup"><span data-stu-id="8f957-285">Results</span></span>

<span data-ttu-id="8f957-286">다음과 같은 결과가 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-286">Your results should be similar to the following.</span></span> <span data-ttu-id="8f957-287">처리 중 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-287">During processing, messages are displayed.</span></span> <span data-ttu-id="8f957-288">경고 또는 메시지 처리를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-288">You may see warnings, or processing messages.</span></span> <span data-ttu-id="8f957-289">이해하기 쉽도록 이러한 결과는 다음 결과에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-289">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 83.96%
Auc: 90.51%
F1Score: 84.04%

=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.1027377
=============== End of Predictions ===============

=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1369192
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9960636
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

<span data-ttu-id="8f957-290">지금까지</span><span class="sxs-lookup"><span data-stu-id="8f957-290">Congratulations!</span></span> <span data-ttu-id="8f957-291">이제 메시지 감정을 분류하고 예측하기 위한 기계 학습 모델을 성공적으로 빌드했습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-291">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span>

<span data-ttu-id="8f957-292">성공한 모델 빌드하는 것은 반복적인 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-292">Building successful models is an iterative process.</span></span> <span data-ttu-id="8f957-293">자습서에서는 작은 데이터 세트를 사용하여 빠른 모델 학습을 제공하므로 이 모델은 초기 품질이 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-293">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="8f957-294">모델 품질에 만족하지 않는 경우 더 큰 학습 데이터 세트를 제공하거나 각 알고리즘에 대한 다양한 [하이퍼 매개 변수](../resources/glossary.md#hyperparameter)와 함께 다양한 학습 알고리즘을 선택하여 모델 품질을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-294">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different [hyper-parameters](../resources/glossary.md#hyperparameter) for each algorithm.</span></span>

<span data-ttu-id="8f957-295">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-295">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8f957-296">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8f957-296">Next steps</span></span>

<span data-ttu-id="8f957-297">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="8f957-297">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="8f957-298">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="8f957-298">Create a console application</span></span>
> - <span data-ttu-id="8f957-299">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="8f957-299">Prepare data</span></span>
> - <span data-ttu-id="8f957-300">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="8f957-300">Load the data</span></span>
> - <span data-ttu-id="8f957-301">모델 빌드 및 학습</span><span class="sxs-lookup"><span data-stu-id="8f957-301">Build and train the model</span></span>
> - <span data-ttu-id="8f957-302">모델 평가</span><span class="sxs-lookup"><span data-stu-id="8f957-302">Evaluate the model</span></span>
> - <span data-ttu-id="8f957-303">모델로 예측 수행</span><span class="sxs-lookup"><span data-stu-id="8f957-303">Use the model to make a prediction</span></span>
> - <span data-ttu-id="8f957-304">결과 보기</span><span class="sxs-lookup"><span data-stu-id="8f957-304">See the results</span></span>

<span data-ttu-id="8f957-305">다음 자습서로 이동하여 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="8f957-305">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="8f957-306">문제 분류</span><span class="sxs-lookup"><span data-stu-id="8f957-306">Issue Classification</span></span>](github-issue-classification.md)
