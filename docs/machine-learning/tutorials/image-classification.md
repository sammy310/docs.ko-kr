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
# <a name="tutorial-retrain-a-tensorflow-image-classifier-with-transfer-learning-and-mlnet"></a>자습서: 전이 학습 및 ML.NET을 사용하여 TensorFlow 이미지 분류자 재학습

전이 학습 및 ML.NET을 사용하여 이미지 분류 TensorFlow 모델을 재학습하는 방법을 알아봅니다. 원래 모델은 개별 이미지를 분류하도록 학습되었습니다. 재학습 후에는 새 모델이 이미지를 광범위한 범주로 구성합니다. 

[이미지 분류](https://en.wikipedia.org/wiki/Outline_of_object_recognition) 모델을 처음부터 학습시키려면 수백만 개의 매개 변수, 많은 레이블 지정 학습 데이터 및 많은 양의 컴퓨팅 리소스(수백 시간의 GPU 시간)를 설정해야 합니다. 사용자 지정 모델을 처음부터 학습시키는 것만큼 효과적이지는 않지만, 전이 학습을 사용하면 수천 개 이미지 및 수백만 개 레이블 지정 이미지를 사용하여 이 프로세스를 간소화하고 사용자 지정 모델을 매우 빠르게 빌드할 수 있습니다(GPU가 없는 머신에서는 1시간 안에 가능).

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.
> [!div class="checklist"]
>
> * 문제 이해
> * 미리 학습된 모델 다시 사용 및 조정
> * 이미지 분류

## <a name="what-is-transfer-learning"></a>전이 학습이란?

유사한 문제를 해결하도록 미리 학습된 모델을 다시 사용하고 문제를 해결할 수 있도록 해당 모델 계층의 전부 또는 일부를 다시 학습시킬 수 있다면 어떻게 될까요? 이미 학습된 모델의 일부를 다시 사용하여 새 모델을 빌드하는 기술을 [전이 학습](https://en.wikipedia.org/wiki/Transfer_learning)이라고 합니다.

## <a name="image-classification-sample-overview"></a>이미지 분류 샘플 개요

이 샘플은 미리 학습된 모델을 다시 사용하여 적은 양의 학습 데이터가 포함된 이미지를 분류하는 방식으로 ML.NET을 사용하여 이미지를 분류하는 콘솔 애플리케이션입니다.

[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다. 기본적으로 이 자습서의 .NET 프로젝트 구성은 .NET Core 2.2를 대상으로 합니다.

## <a name="prerequisites"></a>전제 조건

* “.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017). 

* Microsoft.ML 1.0.0 Nuget 패키지
* Microsoft.ML.ImageAnalytics 1.0.0 Nuget 패키지
* Microsoft.ML.TensorFlow 0.12.0 Nuget 패키지

* [자습서 자산 디렉터리 .ZIP 파일](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)

* [InceptionV1 기계 학습 모델](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-appropriate-machine-learning-task"></a>적절한 기계 학습 작업 선택

[딥 러닝](https://en.wikipedia.org/wiki/Deep_learning)은 Computer Vision 및 음성 인식 같은 혁신적인 영역인 기계 학습의 하위 집합입니다.

딥 러닝 모델은 여러 학습 계층이 포함된 대규모 [레이블 지정 데이터](https://en.wikipedia.org/wiki/Labeled_data) 및 [신경망](https://en.wikipedia.org/wiki/Artificial_neural_network) 세트를 사용하여 학습됩니다. 딥 러닝

* Computer Vision 같은 일부 작업에서 더 효과적으로 작동합니다.

* 엄청난 데이터양에서도 잘 작동합니다.

이미지 분류는 다음과 같은 여러 범주로 이미지를 자동으로 분류할 수 있는 일반적인 기계 학습 작업입니다.

* 이미지에서 사람 얼굴을 인식하는지 여부.
* 고양이 및 개 인식.

 또는 다음 이미지와 같이 이미지가 음식, 장난감 또는 어플라이언스인지 확인:

![피자 이미지](./media/image-classification/220px-Pepperoni_pizza.jpg)
![테디 베어 이미지](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![토스터 이미지](./media/image-classification/193px-Broodrooster.jpg)

>[!Note]
> 앞의 이미지는 Wikimedia Commons에 속하고 다음 특성을 사용합니다.
>
> * “220px-Pepperoni_pizza.jpg” 공용 도메인, https://commons.wikimedia.org/w/index.php?curid=79505,
> * “119px-Nalle_-_a_small_brown_teddy_bear.jpg” 작성자: [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - 직접 사진 촬영, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.
> * “193px-Broodrooster.jpg” 작성자: [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - 직접 작업, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403

전이 학습에는 모든 계층 다시 학습 및 끝에서 두 번째 계층과 같은 몇 가지 전략이 포함됩니다.   이 자습서에서는 끝에서 두 번째 계층 전략을 사용하는 방법을 설명하고 보여 줍니다.  끝에서 두 번째 계층 전략에서는 특정 문제를 해결하기 위해 미리 학습된 모델을 다시 사용합니다.  그런 다음, 새 문제를 해결할 수 있도록 해당 모델의 마지막 계층을 다시 학습시킵니다. 미리 학습된 모델을 새 모델의 일부로 다시 사용하면 상당한 시간과 리소스가 절약됩니다.

이 이미지 분류 모델의 경우 TensorFlow 모델에서 전체 이미지를 “우산”, “저지” 및 “식기 세척기” 같은 수천 개의 클래스로 분류하려고 시도하는 `ImageNet` 데이터 세트를 기반으로 학습된 널리 사용되는 이미지 인식 모델인 [Inception 모델](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)을 다시 사용합니다.

`Inception v1 model`은 [심층 나선형 신경망](https://en.wikipedia.org/wiki/Convolutional_neural_network)으로 분류될 수 있고, 일부 도메인의 인간 수행능력과 일치하거나 이를 초과하는 합리적인 성과를 어려운 시각적 인식 작업에서 달성할 수 있습니다. 모델/알고리즘은 여러 연구원에 의해 개발되었고 다음 원본 논문을 기반으로 합니다. [“Rethinking the Inception Architecture for Computer Vision” by Szegedy, et. al.](https://arxiv.org/abs/1512.00567)(Computer Vision에 대한 Inception 아키텍처 재고려, 작성자: Szegedy 외)

`Inception model`은 수천 개의 이미지를 기반으로 미리 학습되었으므로 이미지 식별에 필요한 [이미지 기능](https://en.wikipedia.org/wiki/Feature_(computer_vision))을 포함합니다. 하위 이미지 기능 계층은 간단한 기능(예: 가장자리)을 인식하고 상위 계층은 더 복잡한 기능(예: 셰이프)을 인식합니다. 이미지 분류 방법을 이미 이해하는 미리 학습된 모델로 시작하므로 마지막 계층은 훨씬 더 작은 데이터 세트를 기반으로 학습됩니다. 모델을 사용하여 세 개 이상의 범주를 분류할 수 있으므로 이 예제는 [다중 클래스 분류자](../resources/tasks.md#multiclass-classification)의 예입니다. 

`TensorFlow`는 심층 신경망(및 일반 숫자 계산)을 학습할 수 있는 널리 사용되는 딥 러닝 및 기계 학습 도구 키트로서, ML.NET에서 `transformer`로 구현됩니다. 이 자습서에서는 이 도구 키트를 사용하여 `Inception model`을 다시 사용합니다.

다음 다이어그램과 같이 .NET Core 또는 .NET Framework 애플리케이션에서 ML.NET NuGet 패키지에 대한 참조를 추가합니다. 기본적으로 ML.NET은 점수를 매기기 위해 기존 학습된 `TensorFlow` 모델 파일을 로드하는 코드를 작성하는 데 사용할 수 있는 네이티브 `TensorFlow` 라이브러리를 포함하고 참조합니다.  

![TensorFlow 변환 ML.NET 아키텍처 다이어그램](./media/image-classification/tensorflow-mlnet.png)

`Inception model`은 이미지를 천 개의 범주로 분류하도록 학습되지만, 더 작은 범주 세트 및 해당 범주로만 이미지를 분류해야 합니다. `transfer learning`의 `transfer` 부분을 입력합니다. 이미지를 인식하고 사용자 지정 이미지 분류자의 제한된 새 범주로 분류하는 `Inception model`의 기능을 전이할 수 있습니다.  

 다음 세 가지 범주 세트를 사용하여 해당 모델의 마지막 계층을 다시 학습시키려고 합니다.

* 음식
* 장난감
* 어플라이언스

계층은 [다항 로지스틱 회귀 분석 알고리즘](https://en.wikipedia.org/wiki/Multinomial_logistic_regression)을 사용하여 최대한 빨리 올바른 범주를 찾습니다. 이 알고리즘은 올바른 범주에 하나의 값을 제공하고 다른 범주에 0 값을 제공하여 응답을 결정하기 위해 확률을 사용하여 분류합니다.  

### <a name="dataset"></a>데이터 세트

두 개의 데이터 소스인 `.tsv` 파일 및 이미지 파일이 있습니다.  `tags.tsv` 파일에는 두 개의 열이 있습니다. 첫 번째 열은 `ImagePath`로 정의되고 두 번째 열은 이미지에 해당하는 `Label`입니다. 다음 예제 파일에는 머리글 행이 없고 다음과 같이 표시됩니다.

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

학습 및 테스트 이미지는 zip 파일로 다운로드할 수 있는 자산 폴더에 있습니다. 이 이미지는 Wikimedia Commons에 속합니다.
> *[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), 무료 미디어 리포지토리.* 2018년 10월 17일 10시 48분 검색된 위치:  
> https://commons.wikimedia.org/wiki/Pizza  
> https://commons.wikimedia.org/wiki/Toaster  
> https://commons.wikimedia.org/wiki/Teddy_bear  

## <a name="create-a-console-application"></a>콘솔 애플리케이션 만들기

### <a name="create-a-project"></a>프로젝트 만들기

1. "TransferLearningTF"라는 **.NET Core 콘솔 애플리케이션**을 만듭니다.

2. **Microsoft.ML NuGet 패키지**를 설치합니다.

    솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다. 패키지 소스로 “nuget.org”를 선택하고, [찾아보기] 탭을 선택하고, **Microsoft.ML**을 검색합니다. **버전** 드롭다운을 클릭하고, 목록에서 **1.0.0** 패키지를 선택하고, **설치** 단추를 선택합니다. **변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다. **Microsoft.ML.ImageAnalytics v1.0.0** 및 **Microsoft.ML.TensorFlow v0.12.0**에 대해 이 단계를 반복합니다.

### <a name="prepare-your-data"></a>데이터 준비

1. [프로젝트 자산 디렉터리 zip 파일](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)을 다운로드하고 압축을 풉니다.

2. `assets` 디렉터리를 *TransferLearningTF* 프로젝트 디렉터리에 복사합니다. 이 디렉터리 및 해당 하위 디렉터리에는 이 자습서에 필요한 데이터 및 지원 파일이 포함되어 있습니다(다음 단계에서 다운로드 및 추가하는 Inception 모델 제외).

3. [Inception 모델](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)을 다운로드하고 압축을 풉니다.

4. 방금 *TransferLearningTF* 프로젝트 `assets\inputs-train\inception` 디렉터리에 압축을 푼 `inception5h` 디렉터리의 콘텐츠를 복사합니다. 이 디렉터리에는 다음 이미지와 같이 이 자습서에 필요한 모델 및 추가 지원 파일이 포함되어 있습니다.

   ![Inception 디렉터리 콘텐츠](./media/image-classification/inception-files.png)

5. 솔루션 탐색기에서 자산 디렉터리 및 하위 디렉터리의 각 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다. **고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.

### <a name="create-classes-and-define-paths"></a>클래스 만들기 및 경로 정의

*Program.cs* 파일 맨 위에 다음 추가 `using` 문을 추가합니다.

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

다양한 자산의 경로를 저장할 전역 필드와 `LabelTokey`, `ImageReal` 및 `PredictedLabelValue`에 대한 전역 변수를 만듭니다.

* `_assetsPath`에는 자산 경로가 포함됩니다.
* `_trainTagsTsv`에는 학습 이미지 데이터 태그 tsv 파일의 경로가 포함됩니다.
* `_predictTagsTsv`에는 예측 이미지 데이터 태그 tsv 파일의 경로가 포함됩니다.
* `_trainImagesFolder`에는 모델을 학습시키는 데 사용되는 이미지의 경로가 포함됩니다.
* `_predictImagesFolder`에는 학습된 모델별로 분류할 이미지의 경로가 포함됩니다.
* `_inceptionPb`에는 모델을 다시 학습시키는 데 다시 사용되는 미리 학습된 Inception 모델의 경로가 포함됩니다.
* `_inputImageClassifierZip`에는 학습된 모델이 로드되는 소스 경로가 포함됩니다.
* `_outputImageClassifierZip`에는 학습된 모델이 저장되는 경로가 포함됩니다.
* `LabelTokey`는 키에 매핑된 `Label` 값입니다.
* `ImageReal`은 예측된 이미지 값을 포함하는 열입니다.
* `PredictedLabelValue`는 예측된 레이블 값을 포함하는 열입니다.

`Main` 메서드 바로 위의 줄에 다음 코드를 추가하여 해당 경로와 다른 변수를 지정합니다.

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

입력 데이터 및 예측에 대한 일부 클래스를 만듭니다. 새 클래스를 프로젝트에 추가합니다.

1. **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.

1. **새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *ImageData.cs*로 변경합니다. 그런 다음, **추가** 단추를 선택합니다.

    *ImageData.cs* 파일이 코드 편집기에서 열립니다. 다음 `using` 문을 *ImageData.cs*의 맨 위에 추가합니다.

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#AddUsings)]

기존 클래스 정의를 제거하고 `ImageData` 클래스에 대한 다음 코드를 *ImageData.cs* 파일에 추가합니다.

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#DeclareTypes)]

`ImageData`는 입력 이미지 데이터 클래스이며 다음 <xref:System.String> 필드를 포함합니다.

* `ImagePath`에는 이미지 파일 이름이 포함됩니다.
* `Label`에는 이미지 레이블의 값이 포함됩니다.

`ImagePrediction`의 새 클래스를 프로젝트에 추가합니다.

1. **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.

1. **새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *ImagePrediction.cs*로 변경합니다. 그런 다음, **추가** 단추를 선택합니다.

    *ImagePrediction.cs* 파일이 코드 편집기에서 열립니다. *ImagePrediction.cs* 맨 위에서 `System.Collections.Generic` 및 `System.Text` `using` 문을 모두 제거합니다.

기존 클래스 정의를 제거하고 `ImagePrediction` 클래스가 포함된 다음 코드를 *ImagePrediction.cs* 파일에 추가합니다.

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/ImagePrediction.cs#DeclareTypes)]

`ImagePrediction`은 이미지 예측 클래스이며 다음 필드를 포함합니다.

* `Score`에는 지정된 이미지 분류를 위한 신뢰율이 포함됩니다.
* `PredictedLabelValue`에는 예측된 이미지 분류 레이블의 값이 포함됩니다.

`ImagePrediction`은 모델이 학습된 후 예측에 사용되는 클래스입니다. 이 클래스에는 이미지 경로의 `string`(`ImagePath`)이 포함됩니다. `Label`은 모델을 다시 사용하고 다시 학습시키는 데 사용됩니다. `PredictedLabelValue`은 예측 및 평가 중에 사용됩니다. 평가를 위해 학습 데이터가 있는 입력, 예측 값 및 모델이 사용됩니다.

[MLContext 클래스](xref:Microsoft.ML.MLContext)는 모든 ML.NET 작업의 시작점이며, `mlContext`를 초기화하면 모델 생성 워크플로 개체 간에 공유할 수 있는 새 ML.NET 환경이 생성됩니다. 개념적으로 Entity Framework의 `DBContext`와 유사합니다.

### <a name="initialize-variables-in-main"></a>Main에서 변수 초기화

`MLContext`의 새 인스턴스를 사용하여 `mlContext` 변수를 초기화합니다.  `Main` 메서드에서 `Console.WriteLine("Hello World!")` 줄을 다음 코드로 바꿉니다.

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

### <a name="create-a-struct-for-default-parameters"></a>기본 매개 변수의 구조체 만들기

Inception 모델에는 전달해야 하는 여러 가지 기본 매개 변수가 있습니다. `Main()` 메서드 바로 뒤에서 다음 코드를 사용하여 기본 매개 변수 값을 친숙한 이름에 매핑하는 구조체를 만듭니다.

[!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a>표시 유틸리티 메서드 만들기

이미지 데이터와 관련 예측을 여러 번 표시하므로 표시 유틸리티 메서드를 만들어 이미지 및 예측 결과 표시를 처리합니다.

`DisplayResults()` 메서드는 다음 작업을 실행합니다.

* 예측 결과를 표시합니다.

다음 코드를 사용하여 `InceptionSettings` 구조체 바로 뒤에 `DisplayResults()` 메서드를 만듭니다.

```csharp
private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
{

}
```

`Transform()` 메서드는 예측 필드와 함께 `ImagePrediction`에서 `ImagePath`를 채웁니다. ML.NET 프로세스를 진행하면서 각 구성 요소가 열을 추가하므로 결과를 쉽게 표시합니다.

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

두 이미지 분류 메서드에서 `DisplayResults()` 메서드를 호출합니다.

### <a name="create-a-tsv-file-utility-method"></a>.tsv 파일 유틸리티 메서드 만들기

`ReadFromTsv()` 메서드는 다음 작업을 실행합니다.

* 이미지 데이터 `tags.tsv` 파일을 읽습니다.
* 이미지 파일 이름에 파일 경로를 추가합니다.
* 파일 데이터를 IEnumerable`ImageData` 개체로 로드합니다.

다음 코드를 사용하여 `PairAndDisplayResults()` 메서드 바로 뒤에 `ReadFromTsv()` 메서드를 만듭니다.

```csharp
public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
{

}
```

다음 코드는 `tags.tsv` 파일을 구문 분석하여 `ImagePath` 속성의 이미지 파일 이름에 파일 경로를 추가하고 로드한 다음, `Label`을 `ImageData` 개체로 로드합니다. `ReadFromTsv()` 메서드의 첫 번째 줄로 추가합니다.  예측 결과를 표시하려면 정규화된 파일 경로가 필요합니다.

[!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]
ML.NET에는 세 가지 주요 개념이 있습니다. [데이터](../resources/glossary.md#data), [변환기](../resources/glossary.md#transformer) 및 [평가자](../resources/glossary.md#estimator).

## <a name="reuse-and-tune-pre-trained-model"></a>미리 학습된 모델 다시 사용 및 조정

`ReuseAndTuneInceptionModel()` 메서드에 다음 호출을 `Main()` 메서드의 다음 코드 줄로 추가합니다.

[!code-csharp[CallReuseAndTuneInceptionModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReuseAndTuneInceptionModel)]

`ReuseAndTuneInceptionModel()` 메서드는 다음 작업을 실행합니다.

* 데이터를 로드합니다.
* 데이터를 추출하고 변환합니다.
* TensorFlow 모델에 점수를 매깁니다.
* 모델을 조정(다시 학습)합니다.
* 모델 결과를 표시합니다.
* 모델을 평가합니다.
* 모델을 반환합니다.

다음 코드를 사용하여 `InceptionSettings` 구조체 바로 뒤 및 `DisplayResults()` 메서드 바로 앞에 `ReuseAndTuneInceptionModel()` 메서드를 만듭니다.

```csharp
public static ITransformer ReuseAndTuneInceptionModel(MLContext mlContext, string dataLocation, string imagesFolder, string inputModelLocation, string outputModelLocation)
{

}
```

### <a name="load-the-data"></a>데이터 로드

ML.NET의 데이터는 [IDataView 클래스](xref:Microsoft.ML.IDataView)로 표시됩니다. `IDataView`는 표 형식 데이터(숫자 및 텍스트)를 유연하고 효율적으로 설명하는 방법입니다. 데이터를 텍스트 파일 또는 실시간(예: SQL 데이터베이스 또는 로그 파일)에서 `IDataView` 개체로 로드할 수 있습니다.

`MLContext.Data.LoadFromTextFile` 래퍼를 사용하여 데이터를 로드합니다. `ReuseAndTuneInceptionModel()` 메서드에 아래 코드를 다음 줄로 추가합니다.

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

### <a name="extract-features-and-transform-the-data"></a>기능 추출 및 데이터 변환

데이터 전처리 및 정리는 데이터 세트가 기계 학습에 효과적으로 사용되기 전에 수행되는 중요한 작업입니다.  이러한 모델링 작업 없이 데이터를 사용하면 잘못된 결과를 얻을 수 있습니다.

기계 학습 알고리즘은 [기능화된](../resources/glossary.md#feature) 데이터를 인식하며, 심층 신경망을 처리할 때 네트워크에 필요한 형식에 맞게 이미지를 조정해야 합니다. 해당 형식은 [숫자 벡터](../resources/glossary.md#numerical-feature-vector)입니다.

학습 및 평가 후에 **레이블** 열 값을 사용하여 예측합니다. 미리 학습된 모델을 사용하므로 [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) 메서드를 사용하여 새 모델에 필드를 매핑합니다. 이 메서드는 `Label`을 숫자 키 형식(`LabelTokey`) 열로 변환하고 새 데이터 세트 열로 추가합니다.  강사를 추가할 때 이 열의 이름을 `estimator`로 지정합니다. 다음 코드 줄을 추가합니다.

[!code-csharp[MapValueToKey1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey1)]

이미지 처리 평가자는 기능 추출에 미리 학습된 [DNN(심층 신경망)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) featurizer를 사용합니다. 심층 신경망을 처리할 때 필요한 네트워크 형식에 맞게 이미지를 조정합니다. 이런 이유로 여러 가지 이미지 변환을 사용하여 모델에 필요한 형식으로 이미지 데이터를 가져옵니다.

1. `LoadImages` 변환 이미지는 비트맵 형식으로 메모리에 로드됩니다.
2. 미리 학습된 모델에 정의된 입력 이미지 너비 및 높이가 포함되므로 `ResizeImages` 변환은 이미지 크기를 조정합니다.
3. `ExtractPixels` 변환은 입력 이미지에서 픽셀을 추출하고 숫자 벡터로 변환합니다.

이 이미지 변환을 다음 코드 줄로 추가합니다.

[!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

`LoadTensorFlowModel`은 `TensorFlow` 모델이 한 번 로드되도록 허용한 다음, `ScoreTensorFlowModel`을 사용하여 `TensorFlowEstimator`를 만드는 간편 메서드입니다. `ScoreTensorFlowModel`은 지정된 출력(`Inception model`의 이미지 기능 `softmax2_pre_activation`)을 추출하고 미리 학습된 `TensorFlow` 모델을 사용하여 데이터 세트의 점수를 매깁니다.

`softmax2_pre_activation`은 이미지가 속한 클래스를 판별하여 모델을 지원합니다. `softmax2_pre_activation`은 각 이미지 범주의 확률을 반환하고, 모든 해당 확률의 합계는 1이어야 합니다. 다음 예제와 같이 이미지가 하나의 범주에만 속한다고 가정합니다.

| 클래스         | 확률   |
| ------------- | ------------- |
| `Food`        |  0.001        |
| `Toy`         |  0.95         |
| `Appliance`   |  0.06         |

다음 코드 줄을 사용하여 `TensorFlowTransform`을 `estimator`에 추가합니다.

[!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

### <a name="choose-a-training-algorithm"></a>학습 알고리즘 선택

학습 알고리즘을 추가하려면 `mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()` 래퍼 메서드를 호출합니다.  [LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer)는 `estimator`에 추가되고 Inception 이미지 기능(`softmax2_pre_activation`) 및 `Label` 입력 매개 변수를 수락하여 기록 데이터를 기반으로 학습합니다.  다음 코드를 사용하여 강사를 추가합니다.

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

또한 `predictedlabel`을 `predictedlabelvalue`에 매핑해야 합니다.

[!code-csharp[MapValueToKey2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey2)]

`Fit()` 메서드는 데이터 세트를 변환하고 학습을 적용하여 모델을 학습합니다. 모델을 학습 데이터 세트에 맞추고 `ReuseAndTuneInceptionModel()` 메서드에서 다음 줄로 다음 항목을 추가하여 학습된 모델을 반환합니다.

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

[Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 메서드는 테스트 데이터 세트의 여러 입력 행을 예측합니다.  `ReuseAndTuneInceptionModel()`에 다음 코드를 추가하여 `Training`데이터를 변환합니다.

[!code-csharp[TransformData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TransformData)]

보다 쉽게 표시할 수 있도록 이미지 데이터와 예측 `DataViews`를 강력한 형식의 `IEnumerables`로 변환하여 쌍으로 연결합니다. 다음 코드를 사용하여 `MLContext.CreateEnumerable()` 메서드를 통해 작업을 수행합니다.

[!code-csharp[EnumerateDataViews](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#EnumerateDataViews)]

다음 코드를 추가하여 데이터 및 예측을 `ReuseAndTuneInceptionModel()` 메서드의 다음 줄과 같이 표시합니다.

[!code-csharp[CallDisplayResults1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults1)]

예측 세트가 있으면 [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) 메서드가 다음을 수행합니다.

* 모델을 평가합니다(예측 값을 실제 데이터 세트 `Labels`와 비교).

* 모델 성능 메트릭을 반환합니다.

`ReuseAndTuneInceptionModel()` 메서드에 아래 코드를 다음 줄로 추가합니다.

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

이미지 분류를 위해 다음 메트릭이 평가됩니다.

* `Log-loss` - [로그 손실](../resources/glossary.md#log-loss)을 참조하세요. 로그 손실을 가능한 한 0에 가깝게 합니다.

* `Per class Log-loss`. 클래스별 로그 손실을 가능한 한 0에 가깝게 합니다.

다음 코드를 사용하여 메트릭을 표시하고, 결과를 공유한 다음, 작업을 수행합니다.

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

 다음 코드를 추가하여 학습된 모델을 다음 줄로 반환합니다.

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReturnModel)]

## <a name="classify-images-with-a-loaded-model"></a>로드된 모델을 통해 이미지 분류

`ClassifyImages()` 메서드에 아래 호출을 `Main` 메서드의 다음 코드 줄로 추가합니다.

[!code-csharp[CallClassifyImages](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifyImages)]

`ClassifyImages()` 메서드는 다음 작업을 실행합니다.

* .TSV 파일을 `IEnumerable`로 읽습니다.
* 테스트 데이터를 기반으로 이미지 분류를 예측합니다.

다음 코드를 사용하여 `ReuseAndTuneInceptionModel()` 메서드 바로 뒤 및 `PairAndDisplayResults()` 메서드 바로 앞에 `ClassifyImages()` 메서드를 만듭니다.

```csharp
public static void ClassifyImages(MLContext mlContext, string dataLocation, string imagesFolder, string outputModelLocation, ITransformer model)
{

}
```

먼저 `ReadFromTsv()` 메서드를 호출하여 각 `ImagePath`의 정규화된 경로를 포함하는 `IEnumerable<ImageData>` 클래스를 만듭니다. 데이터와 예측 결과를 쌍으로 연결하려면 파일 경로가 필요합니다. 또한 예측하는 데 사용할 `IDataView`로 `IEnumerable<ImageData>` 클래스를 변환해야 합니다. `ClassifyImages()` 메서드의 다음 두 줄로 아래 코드를 추가합니다.

[!code-csharp[CallReadFromTSV](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReadFromTSV)]

이전에 학습 이미지 데이터를 예측한 것처럼 전달된 모델의 [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 메서드를 사용하여 테스트 이미지 데이터의 범주를 예측합니다. 예측을 위해 다음 코드를 `ClassifyImages()` 메서드에 추가하고, 쌍 연결 및 표시를 위해 `predictions` `IDataView`를 `IEnumerable`로 변환합니다.

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Predict)]

테스트 이미지 데이터 및 예측을 쌍으로 연결하고 표시하려면 다음 코드를 추가하여 `DisplayResults()` 메서드의 다음 줄로 이전에 만들어진 `ClassifyImages()` 메서드를 호출합니다.

[!code-csharp[CallDisplayResults2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults2)]

## <a name="classify-a-single-image-with-a-loaded-model"></a>로드된 모델을 통해 단일 이미지 분류

`ClassifySingleImage()` 메서드에 아래 호출을 `Main` 메서드의 다음 코드 줄로 추가합니다.

[!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

`ClassifySingleImage()` 메서드는 다음 작업을 실행합니다.

* `ImageData` 인스턴스를 로드합니다.
* 테스트 데이터를 기반으로 이미지 분류를 예측합니다.

다음 코드를 사용하여 `ClassifyImages()` 메서드 바로 뒤 및 `PairAndDisplayResults()` 메서드 바로 앞에 `ClassifySingleImage()` 메서드를 만듭니다.

```csharp
public static void ClassifySingleImage(MLContext mlContext, string imagePath, string outputModelLocation, ITransformer model)
{

}
```

먼저 단일 `ImagePath`의 정규화된 경로 및 이미지 파일 이름을 포함하는 `ImageData` 클래스를 만듭니다. `ClassifySingleImage()` 메서드의 다음 줄로 아래 코드를 추가합니다.

[!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

[PredictionEngine 클래스](xref:Microsoft.ML.PredictionEngine%602)는 단일 데이터 인스턴스에 대한 예측을 수행하는 편리한 API입니다. [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) 함수는 단일 데이터 열의 대한 예측을 수행합니다. `ClassifySingleImage()`에 다음 코드를 추가하여 이미지 범주를 예측하는 `PredictionEngine`에 `imageData`를 전달합니다.

[!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

예측 결과를 `ClassifySingleImage()` 메서드의 다음 코드 줄로 표시합니다.

[!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="results"></a>결과

이전 단계를 수행한 후 콘솔 앱을 실행합니다(Ctrl+F5). 다음 출력과 같은 결과가 나타나야 합니다.  경고 또는 처리 메시지가 표시될 수 있지만, 이해하기 쉽도록 이러한 메시지는 다음 결과에서 제거되었습니다.

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

지금까지 이제 ML.NET에서 미리 학습된 `TensorFlow` 모델을 다시 사용하여 이미지 분류를 위한 기계 학습 모델을 성공적으로 빌드했습니다.

[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.

본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.
> [!div class="checklist"]
>
> * 문제 이해
> * 미리 학습된 모델 다시 사용 및 조정
> * 로드된 모델을 통해 이미지 분류

기계 학습 샘플 GitHub 리포지토리를 확인하여 확장된 이미지 분류 샘플을 살펴보세요.
> [!div class="nextstepaction"]
> [dotnet/machinelearning-samples GitHub 리포지토리](https://github.com/dotnet/machinelearning-samples/)
