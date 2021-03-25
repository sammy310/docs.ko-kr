---
title: '자습서: Model Builder를 사용하여 이미지에서 개체 검색'
description: 이 자습서에서는 ML.NET Model Builder 및 Azure ML을 사용하여 이미지에서 정지 표지판을 검색하는 개체 검색 모델을 빌드하는 방법을 보여 줍니다.
author: briacht
ms.author: brachtma
ms.date: 03/12/2021
ms.topic: tutorial
ms.custom: mlnet-tooling
ms.openlocfilehash: 21b672b84c7f55578a76459fa9f02aca3455d719
ms.sourcegitcommit: 1dbe25ff484a02025d5c34146e517c236f7161fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "104658385"
---
# <a name="tutorial-detect-stop-signs-in-images-with-model-builder"></a>자습서: Model Builder를 사용하여 이미지에서 정지 표지판 검색

ML.NET Model Builder 및 Azure ML을 사용하여 이미지에서 정지 표지판을 찾는 개체 검색 모델을 빌드하는 방법을 알아봅니다.

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.

> [!div class="checklist"]
>
> - 데이터 준비 및 이해
> - 시나리오 선택
> - 학습 환경 선택
> - 데이터 로드
> - 모델 학습
> - 모델 평가
> - 예측에 모델 사용

> [!NOTE]
> 모델 작성기는 현재 미리 보기로 제공됩니다.

## <a name="prerequisites"></a>사전 요구 사항

필수 구성 요소 및 설치 지침 목록을 보려면 [모델 작성기 설치 가이드](../how-to-guides/install-model-builder.md)를 방문하세요.

## <a name="model-builder-object-detection-overview"></a>Model Builder 개체 검색 개요

개체 검색은 컴퓨터 비전 문제입니다. 개체 검색은 이미지 분류와 밀접하게 관련된 반면, 보다 세부적인 규모에서 이미지 분류를 수행합니다. 개체 검색에서는 이미지에서 엔터티 찾기 _및_ 분류를 둘 다 수행합니다. 이미지에 서로 다른 유형의 개체가 여러 개 포함되어 있는 경우 개체 검색을 사용합니다.

![이미지 분류 및 개체 분류를 보여 주는 스크린샷](./media/object-detection-onnx/img-classification-obj-detection.PNG)

개체 검색의 몇 가지 사용 사례는 다음과 같습니다.

- 자동 주행 자동차
- Robotics
- 얼굴 감지
- 작업 영역 안전성
- 개체 수 계산
- 활동 인식

이 샘플은 Model Builder로 빌드된 기계 학습 모델을 사용하여 이미지에서 정지 표지판을 검색하는 C# .NET Core 콘솔 애플리케이션을 만듭니다. [dotnet/samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/modelbuilder/ObjectDetection_StopSigns) GitHub 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.

## <a name="prepare-and-understand-the-data"></a>데이터 준비 및 이해

정지 표지판 데이터 세트는 [Unsplash](https://unsplash.com/)에서 다운로드한 50개 이미지로 구성되며 각 이미지에는 하나 이상의 정지 표지판이 포함되어 있습니다.

가장 먼저 할 일은 이미지에 주석을 추가하거나 각 이미지에서 정지 표지판 주위에 경계 상자를 그리는 것입니다. 이 자습서에서는 [VoTT](https://github.com/microsoft/VoTT)라는 도구를 사용하여 이미지에 주석을 추가합니다.

> 아래의 데이터 레이블 지정 단계를 건너뛰려면 [이 버전의 데이터 세트를 다운로드](https://aka.ms/mlnet-object-detection-tutorial-assets)하여 [콘솔 애플리케이션 만들기](object-detection-model-builder.md#create-a-console-application)로 건너뛸 수 있습니다.

### <a name="create-a-new-vott-project"></a>새 VoTT 프로젝트 만들기

1. 50개 정지 표지판 이미지의 [데이터 세트를 다운로드](https://aka.ms/mlnet-object-detection-tutorial-dataset)하고 압축을 해제합니다.
1. [VoTT](https://github.com/Microsoft/VoTT/releases)(시각적 개체 태그 지정 도구)를 다운로드합니다.
1. VoTT를 열고 **새 프로젝트** 를 선택합니다.

    ![VoTT 홈 화면](./media/object-detection-model-builder/vott.png)

1. **프로젝트 설정** 에서 **표시 이름** 을 ‘StopSignObjDetection’으로 변경합니다.
1. **보안 토큰** 을 새 보안 토큰 생성으로 변경합니다.
1. **원본 연결** 옆에서 **연결 추가** 를 선택합니다.
1. **연결 설정** 에서 원본 연결의 **표시 이름** 을 ‘StopSignImages’로 변경하고 로컬 파일 시스템을 **공급자** 로 선택합니다. **폴더 경로** 에서 50개 학습 이미지가 들어 있는 *Stop-Signs* 폴더를 선택한 다음 **연결 저장** 을 선택합니다.

    ![VoTT 새 연결 대화 상자](./media/object-detection-model-builder/vott-new-connection.png)

1. **프로젝트 설정** 에서 **원본 연결** 을 *StopSignImages*(방금 만든 연결)로 변경합니다.
1. **대상 연결** 도 *StopSignImages* 로 변경합니다. 이제 **프로젝트 설정** 은 다음과 유사하게 표시됩니다.

    ![VoTT 프로젝트 설정 대화 상자](./media/object-detection-model-builder/vott-new-project.png)

1. **프로젝트 저장** 을 선택합니다.

### <a name="add-tag-and-label-images"></a>태그 추가 및 이미지 레이블링

이제 왼쪽에 모든 학습 이미지의 미리 보기 이미지가 표시되고, 가운데에 선택한 이미지의 미리 보기가 표시되고, 오른쪽에 **태그** 열이 표시된 창이 나타납니다. 이 화면은 **태그 편집기** 입니다.

1. **태그** 도구 모음에서 첫 번째(더하기 모양) 아이콘을 선택하여 새 태그를 추가합니다.

    ![VoTT 새 태그 아이콘](./media/object-detection-model-builder/vott-new-tag-icon.png)

1. 태그 이름을 ‘Stop-Sign’으로 지정하고 키보드에서 <kbd>Enter</kbd> 키를 누릅니다.

    ![VoTT 새 태그](./media/object-detection-model-builder/vott-new-tag.png)

1. 클릭하고 끌어 이미지의 각 정지 표지판 주위에 사각형을 그립니다. 커서를 사용하여 사각형을 그릴 수 없는 경우 위쪽의 도구 모음에서 **사각형 그리기** 도구를 선택하거나 바로 가기 키 <kbd>R</kbd>을 사용합니다.
1. 사각형을 그린 후 이전 단계에서 만든 **Stop-Sign** 태그를 선택하여 경계 상자에 태그를 추가합니다.
1. 데이터 세트의 다음 이미지에 대한 미리 보기 이미지를 클릭하고 이 프로세스를 반복합니다.
1. 모든 이미지의 모든 정지 표지판에 대해 3~4단계를 계속합니다.

    ![VoTT 이미지 주석 달기](./media/object-detection-model-builder/vott-annotating.gif)

### <a name="export-your-vott-json"></a>VoTT JSON 내보내기

모든 학습 이미지에 레이블을 지정한 후에는 Model Builder에서 학습에 사용할 파일을 내보낼 수 있습니다.

1. 왼쪽 도구 모음의 네 번째 아이콘(상자 안에 대각선 화살표가 있는 모양)을 선택하여 **내보내기 설정** 으로 이동합니다.
1. **공급자** 를 *VoTT JSON* 으로 그대로 둡니다.
1. **자산 상태** 를 태그가 지정된 자산만으로 변경합니다.
1. **이미지 포함** 을 선택 취소합니다. 이미지를 포함시킬 경우 학습 이미지가 생성되는 내보내기 폴더로 복사됩니다. 이는 필요하지 않습니다.
1. **내보내기 설정 저장** 을 선택합니다.

    ![VoTT 내보내기 설정](./media/object-detection-model-builder/vott-export.png)

1. **태그 편집기** 로 돌아갑니다(왼쪽 도구 모음에서 리본 모양의 두 번째 아이콘). 상단 도구 모음에서 **프로젝트 내보내기** 아이콘(상자 안에 화살표가 있는 모양의 마지막 아이콘)을 선택하거나 바로 가기 키 <kbd>Ctrl</kbd>+<kbd>E</kbd>를 사용합니다.

    ![VoTT 내보내기 단추](./media/object-detection-model-builder/vott-export-button.png)

이 내보내기는 *Stop-Sign-Images* 폴더에 *vott-json-export* 라는 새 폴더를 만들고 그 안에 *StopSignObjDetection-export* 라는 JSON 파일을 생성합니다. Model Builder에서 개체 검색 모델을 학습시키는 다음 단계에서 이 JSON 파일을 사용합니다.

## <a name="create-a-console-application"></a>콘솔 애플리케이션 만들기

1. Visual Studio에서 *StopSignDetection* 이라는 **C# .NET Core 콘솔 애플리케이션** 을 만듭니다.

## <a name="choose-a-scenario"></a>시나리오 선택

1. **솔루션 탐색기** 에서 *StopSignDetection* 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **기계 학습** 을 선택하여 Model Builder UI를 엽니다.
1. 이 샘플에서는 시나리오가 개체 검색입니다. Model Builder의 **시나리오** 단계에서 **개체 검색** 시나리오를 선택합니다.

![Visual Studio의 모델 작성기 마법사](./media/object-detection-model-builder/obj-det-scenario.png)

> 시나리오 목록에 개체 감지가 표시되지 않는 경우 [Model Builder의 버전을 업데이트](https://marketplace.visualstudio.com/items?itemName=MLNET.07)해야 할 수 있습니다.

## <a name="choose-the-training-environment"></a>학습 환경 선택

현재 Model Builder는 Azure Machine Learning을 사용하는 개체 검색 모델 학습만 지원하므로 Azure 학습 환경이 기본적으로 선택됩니다.

![Azure 학습 환경 선택](./media/object-detection-model-builder/obj-det-environment.png)

Azure ML을 사용하여 모델을 학습시키려면 Model Builder에서 Azure ML 실험을 만들어야 합니다.

**Azure ML 실험** 은 하나 이상의 기계 학습 학습 실행에 대한 구성 및 결과를 캡슐화하는 리소스입니다.

Azure ML 실험을 만들려면 먼저 Azure에서 환경을 구성해야 합니다. 실험을 실행하려면 다음이 필요합니다.

- Azure 구독
- **작업 영역**: 학습 실행의 일부로 생성된 모든 Azure ML 리소스 및 아티팩트에 대한 중앙 위치를 제공하는 Azure ML 리소스입니다.
- **컴퓨팅**: Azure Machine Learning 컴퓨팅은 학습에 사용되는 클라우드 기반 Linux VM입니다. [Model Builder에서 지원하는 컴퓨팅 형식](../resources/azure-training-concepts-model-builder.md#what-is-an-azure-machine-learning-compute)에 대해 자세히 알아보세요.

### <a name="set-up-an-azure-ml-workspace"></a>Azure ML 작업 영역 설정

환경을 구성하려면 다음을 수행합니다.

1. **작업 영역 설정** 단추를 선택합니다.
1. **새 실험 만들기** 대화 상자에서 Azure 구독을 선택합니다.
1. 기존 작업 영역을 선택하거나 새 Azure ML 작업 영역을 만듭니다.

    새 작업 영역을 만들면 다음 리소스가 프로비저닝됩니다.

    - Azure Machine Learning 작업 영역
    - Azure Storage
    - Azure Application Insights
    - Azure Container Registry
    - Azure Key Vault

    그러므로 이 프로세스에 몇 분 정도 걸릴 수 있습니다.

1. 기존 컴퓨팅을 선택하거나 새 Azure ML 컴퓨팅을 만듭니다. 이 프로세스에 몇 분 정도 걸릴 수 있습니다.
1. 기본 실험 이름은 그대로 두고 **만들기** 를 선택합니다.

    ![Azure 작업 영역 설정 대화 상자](./media/object-detection-model-builder/azure-dialog.png)

처음 실험이 만들어지고 작업 영역에 실험 이름이 등록됩니다. 모든 후속 실행(같은 실험 이름을 사용하는 경우)은 같은 실험의 일부로 기록됩니다. 같은 실험 이름이 사용되지 않으면 새 실험이 만들어집니다.

구성에 만족하는 경우 Model Builder에서 **다음 단계** 단추를 선택하여 **데이터** 단계로 이동합니다.

## <a name="load-the-data"></a>데이터 로드

Model Builder의 **데이터** 단계에서는 학습 데이터 세트를 선택합니다.

>Model Builder는 현재 VoTT에서 생성된 JSON 형식만 허용하지만 향후 더 많은 형식에 대한 지원을 추가할 계획입니다. Model Builder가 지원하기를 희망하는 개체 검색용 데이터 세트 형식이 있는 경우 [GitHub](https://github.com/dotnet/machinelearning-modelbuilder/issues/new?assignees=&labels=&template=data_suggestion.md&title=)에 피드백을 남겨주세요.

1. **폴더 선택** 텍스트 상자 옆에 있는 단추를 선택하고 파일 탐색기를 사용하여 *Stop-Signs/vott-json-export* 디렉터리에 있는 `StopSignObjDetection-export.json`을 찾습니다.

    ![Model Builder 데이터 단계](./media/object-detection-model-builder/obj-det-data.png)

1. **데이터 미리 보기** 에서 데이터가 올바르게 표시되면 **다음 단계** 를 선택하여 **학습** 단계로 이동합니다.

## <a name="train-the-model"></a>모델 학습

다음 단계는 모델 학습입니다.

Model Builder **학습** 화면에서 **학습 시작** 단추를 선택합니다.

이제 데이터가 Azure Storage에 업로드되고 Azure ML에서 학습 프로세스가 시작됩니다.

>학습 프로세스에는 어느 정도 시간이 걸리며, 선택한 컴퓨팅 크기 및 데이터의 양에 따라 걸리는 시간이 달라질 수 있습니다. Azure에서 처음 모델을 학습시킬 때는 리소스를 프로비저닝해야 하므로 학습 시간이 약간 길어질 수 있습니다. 이 50개 이미지 샘플의 경우 학습에 16분 정도 걸렸습니다.

Visual Studio에서 **Azure Portal에서 현재 실행 모니터링** 링크를 선택하여 Azure Machine Learning 포털에서 실행의 진행률을 추적할 수 있습니다.

학습이 완료되면 **다음 단계** 단추를 선택하여 **평가** 단계로 이동합니다.

## <a name="evaluate-the-model"></a>모델 평가

평가 화면에서 모델 정확도를 포함하여 학습 프로세스의 결과에 대한 개요를 볼 수 있습니다.

![Model Builder 평가 단계](./media/object-detection-model-builder/obj-det-evaluate.png)

이 경우 정확도가 100%로 표시됩니다. 즉, 데이터 세트에 이미지가 너무 적어서 모델이 과잉 맞춤된 것으로 보입니다.

**모델 사용해 보기** 환경을 사용하여 모델이 예상대로 작동하는지 빠르게 확인할 수 있습니다.

**이미지 찾아보기** 를 선택하고 테스트 이미지를 제공합니다. 이러한 이미지는 모델이 학습에 사용하지 않은 것이 좋습니다.

![Model Builder 모델 사용해 보기](./media/object-detection-model-builder/obj-det-try-model.png)

검색된 각 경계 상자에 표시되는 점수는 검색된 개체의 **신뢰도** 를 나타냅니다. 예를 들어 위의 스크린샷에서 정지 표지판 주위의 경계 상자 점수는 모델이 검색된 개체가 정지 표지판임을 99% 확신하는 것을 나타냅니다.

임계값 슬라이더를 사용하여 높이거나 낮출 수 있는 **점수 임계값** 은 해당 점수에 따라 검색된 개체를 추가 또는 제거합니다. 예를 들어 임계값이 .51인 경우 모델은 신뢰도 점수가 .51 이상인 개체만 표시합니다. 임계값을 높이면 검색된 개체가 줄어듭니다. 임계값을 낮추면 검색된 개체가 늘어납니다.

정확도 메트릭이 만족스럽지 않을 경우 모델 정확도를 개선하기 위한 간단한 방법 하나는 더 많은 데이터를 사용하는 것입니다. 그렇지 않으면 **다음 단계** 링크를 선택하여 Model Builder의 **코드** 단계로 이동합니다.

## <a name="add-the-code-to-make-predictions"></a>코드를 추가하여 예측하기

학습 프로세스의 결과로 두 개의 프로젝트가 만들어집니다.

- *StopSignDetectionML.ConsoleApp*: 모델 학습 코드 및 샘플 소비 코드가 포함된 C# .NET Core 콘솔 애플리케이션입니다.
- *StopSignDetectionML.Model*: 입력 및 출력 모델 데이터의 스키마를 정의하는 데이터 모델, 학습 중 가장 성능이 뛰어난 모델의 저장된 버전, 예측을 위한 `ConsumeModel`이라는 도우미 클래스를 포함하는 .NET Standard 클래스 라이브러리입니다.

1. Model Builder의 코드 단계에서 **프로젝트 추가** 를 선택하여 자동 생성된 프로젝트를 솔루션에 추가합니다.
1. *StopSignDetection* 프로젝트에서 *Program.cs* 파일을 열고 다음 using 문을 파일 맨 위에 추가하여 *StopSignDetectionML.Model* 프로젝트를 참조합니다.

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/modelbuilder/ObjectDetection_StopSigns/StopSignDetection/Program.cs#L2)]

1. 다음 [테스트 이미지](~/machinelearning-samples/samples/modelbuilder/ObjectDetection_StopSigns/StopSignDetection/test-image1.jpeg)를 다운로드합니다.
1. 애플리케이션의 `Main` 메서드 내에서 `ImageSource` 속성을 테스트 이미지의 filepath로 설정하여 `ModelInput` 클래스의 새 인스턴스를 만듭니다. ‘Hello World’ 문을 다음 코드로 바꿉니다.

    [!code-csharp [InputData](~/machinelearning-samples/samples/modelbuilder/ObjectDetection_StopSigns/StopSignDetection/Program.cs#L10-L15)]

1. `ConsumeModel` 클래스의 `Predict` 메서드를 사용하여 학습된 모델을 로드하고, 모델에 대한 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)을 만들고, 새 데이터에 대한 예측을 만듭니다. `ModelInput` 문에 다음 코드를 추가합니다.

    [!code-csharp [Prediction](~/machinelearning-samples/samples/modelbuilder/ObjectDetection_StopSigns/StopSignDetection/Program.cs#L15)]

1. 다음 코드를 추가하여 레이블, 좌표, 점수를 포함한 예측의 출력을 인쇄합니다.

    [!code-csharp [PrintResults](~/machinelearning-samples/samples/modelbuilder/ObjectDetection_StopSigns/StopSignDetection/Program.cs#L17-L18)]

1. 애플리케이션을 실행합니다.

    프로그램에서 생성된 출력은 아래 코드 조각과 유사해야 합니다.

    ```bash
    Predicted Boxes:
    
    Top: 89.453415, Left: 481.95343, Right: 724.8073, Bottom: 388.32385, Label: Stop-Sign, Score: 0.99539465
    ```

축하합니다! Model Builder를 사용하여 이미지에서 정지 표지판을 검색하는 기계 학습 모델을 성공적으로 빌드했습니다. [dotnet/samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/modelbuilder/ObjectDetection_StopSigns) GitHub 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.

## <a name="additional-resources"></a>추가 리소스

이 자습서에서 언급한 항목에 대한 자세한 내용은 다음 리소스를 참조하세요.

- [모델 작성기 시나리오](../automate-training-with-model-builder.md#scenario)
- [ML.NET에서 ONNX를 사용하여 개체 검색](object-detection-onnx.md)
