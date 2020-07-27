---
title: 모델 작성기 Azure 학습 리소스
description: Azure Machine Learning에 대한 리소스 가이드
ms.topic: reference
ms.date: 06/01/2020
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 8622b580b7925adfd7895317815021f57960e9ee
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86924580"
---
# <a name="model-builder-azure-training-resources"></a>모델 작성기 Azure 학습 리소스

다음은 모델 작성기를 사용하여 Azure에서 모델을 학습시키는 데 사용되는 리소스에 대해 자세히 알아보는 데 유용한 가이드입니다.

## <a name="what-is-an-azure-machine-learning-experiment"></a>Azure Machine Learning 실험이란?

Azure Machine Learning 실험은 Azure에서 모델 작성기 학습을 실행하기 전에 만들어야 하는 리소스입니다.

실험은 하나 이상의 기계 학습 실행에 대한 구성 및 결과를 캡슐화합니다. 실험은 특정 작업 영역에 속합니다. 처음 실험을 만들면 해당 이름이 작업 영역에 등록됩니다. 모든 후속 실행(같은 실험 이름이 사용되는 경우)은 같은 실험의 일부로 기록됩니다. 같은 실험 이름이 사용되지 않으면 새 실험이 만들어집니다.

## <a name="what-is-an-azure-machine-learning-workspace"></a>Azure Machine Learning 작업 영역이란?

작업 영역은 학습 실행의 일부로 생성된 모든 Azure Machine Learning 리소스 및 아티팩트에 대한 중앙 환경을 제공하는 Azure Machine Learning 리소스입니다.

Azure Machine Learning 작업 영역을 만들려면 다음이 필요합니다.

- 이름: 3~33자 길이의 작업 영역 이름입니다. 이름은 영숫자 문자와 하이픈만 포함할 수 있습니다.
- 지역: 작업 영역 및 리소스가 배포되는 데이터 센터의 지리적 위치입니다. 귀하 또는 귀하의 고객이 있는 위치와 가까운 위치를 선택하는 것이 좋습니다.
- 리소스 그룹: Azure 솔루션의 모든 관련 리소스를 포함하는 컨테이너입니다.

## <a name="what-is-an-azure-machine-learning-compute"></a>Azure Machine Learning 컴퓨팅이란?

Azure Machine Learning 컴퓨팅은 학습에 사용되는 클라우드 기반 Linux VM입니다.

Azure Machine Learning 작업 영역을 만들려면 다음이 필요합니다.

- 이름: 2~16자 길이의 작업 영역 이름입니다. 이름은 영숫자 문자와 하이픈만 포함할 수 있습니다.
- 컴퓨팅 크기

    모델 작성기는 다음과 같은 GPU 최적화 컴퓨팅 형식 중 하나를 사용할 수 있습니다.

    | Size | vCPU | 메모리: GiB | 임시 스토리지(SSD) GiB | GPU | GPU 메모리: GiB | 최대 데이터 디스크 수 | 최대 NIC 수 |
    |---|---|---|---|---|---|---|---|
    | Standard_NC12   | 12 | 112 | 680  | 2 | 24 | 48 | 2 |
    | Standard_NC24   | 24 | 224 | 1440 | 4 | 48 | 64 | 4 |

    GPU 최적화 컴퓨팅 형식에 대한 자세한 내용은 [NC 시리즈 Linux VM 설명서](https://docs.microsoft.com/azure/virtual-machines/nc-series?toc=/azure/virtual-machines/linux/toc.json&bc=/azure/virtual-machines/linux/breadcrumb/toc.json)를 참조하세요.
- 컴퓨팅 우선 순위

  - 낮은 우선 순위: 실행 시간이 짧은 작업에 적합합니다. 중단 및 가용성 부족의 영향을 받을 수 있습니다. Azure에서 여분의 용량을 활용하므로 일반적으로 비용이 절감됩니다.
  - 전용: 모든 기간의 작업에 적합하지만 장기 실행 작업에 특히 적합합니다. 중단 또는 가용성 부족의 영향을 받지 않습니다. 작업에 대해 Azure의 전용 컴퓨팅 리소스 세트를 예약하므로 일반적으로 비용이 더 많이 듭니다.

## <a name="training"></a>교육

Azure에 대한 학습은 모델 작성기 이미지 분류 시나리오에만 사용할 수 있습니다. 이 모델을 학습시키는 데 사용되는 알고리즘은 ResNet50 아키텍처를 기반으로 한 심층 신경망입니다. 학습 프로세스에는 어느 정도 시간이 걸리며, 선택한 컴퓨팅 크기 및 데이터의 양에 따라 걸리는 시간이 달라질 수 있습니다. Visual Studio에서 “Monitor current run in Azure portal”(Azure Portal에서 현재 실행 모니터링) 링크를 선택하여 실행의 진행률을 추적할 수 있습니다.

## <a name="results"></a>결과

학습이 완료되면 다음 접미사가 사용된 두 개의 프로젝트가 솔루션에 추가됩니다.

- *ConsoleApp*: 예측 파이프라인을 빌드하고 예측을 수행하기 위한 시작 코드를 제공하는 C# .NET Core 콘솔 애플리케이션입니다.
- *모델*: 입력 및 출력 모델 데이터의 스키마와 다음 자산을 정의하는 데이터 모델이 포함된 C# .NET Standard 애플리케이션입니다.

  - bestModel.onnx: ONNX(Open Neural Network Exchange) 형식으로 된 모델의 직렬화된 버전입니다. ONNX는 ML.NET, PyTorch, TensorFlow 등의 프레임워크 간 상호 운용성을 지원하는 AI 모델의 오픈 소스 형식입니다.
  - bestModelMap.json: 예측을 만들어 모델 출력을 텍스트 범주에 매핑할 때 사용되는 범주 목록입니다.
  - MLModel.zip: *bestModel.onnx* 모델의 직렬화된 버전을 사용하여 예측하고 `bestModelMap.json` 파일을 사용하여 출력을 매핑하는 ML.NET 예측 파이프라인의 직렬화된 버전입니다.

## <a name="use-the-machine-learning-model"></a>기계 학습 모델 사용

*Model* 프로젝트의 `ModelInput` 및 `ModelOutput` 클래스는 각각 모델의 필요한 입력 및 출력 스키마를 정의합니다.

이미지 분류 시나리오에서 `ModelInput`은 다음과 같은 두 개의 열을 포함합니다.

- `ImageSource`: 이미지 위치의 문자열 경로입니다.
- `Label`: 이미지가 속하는 실제 범주입니다. `Label`은 학습 시 입력으로만 사용되며 예측할 때 제공할 필요가 없습니다.

`ModelOutput`은 다음과 같은 두 개의 열을 포함합니다.

- `Prediction`: 이미지의 예측 범주입니다.
- `Score`: 모든 범주에 대한 확률 목록입니다(가장 높은 확률이 `Prediction`에 속함).

## <a name="troubleshooting"></a>문제 해결

### <a name="cannot-create-compute"></a>컴퓨팅을 만들 수 없음

Azure Machine Learning 컴퓨팅을 생성하는 동안 오류가 발생하는 경우, 그런데도 컴퓨팅 리소스가 존재할 수는 있습니다(단, 오류 상태). 같은 이름으로 컴퓨팅 리소스를 다시 만들려고 하면 작업이 실패합니다. 이 오류를 해결하려면 다음 중 하나를 수행합니다.

- 다른 이름으로 새 컴퓨팅 만들기
- Azure Portal로 이동하여 원래 컴퓨팅 리소스 제거
