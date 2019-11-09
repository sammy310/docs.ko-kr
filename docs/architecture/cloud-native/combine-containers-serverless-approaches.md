---
title: 컨테이너 및 서버리스 접근 방식 결합
description: 서버를 사용 하지 않는 방법으로 컨테이너와 Kubernetes 결합
ms.date: 06/30/2019
ms.openlocfilehash: 58aff43adbdd2e629370cc685f32c7b61c25f85e
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840594"
---
# <a name="combining-containers-and-serverless-approaches"></a>컨테이너 및 서버리스 접근 방식 결합

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

주로 마이크로 서비스 기반 응용 프로그램은 노드 간 통신을 위해 컨테이너, 오케스트레이션 및 메시지 전달에 크게 의존 합니다. 이 메시징은 Azure Functions에 이상적인 작업 이지만 응용 프로그램의 나머지 부분을 Kubernetes 및 관련 도구를 사용 하 여 구성 하 고 배포한 후에는이 동일한 도구 집합 내에서 Azure Functions를 활용할 수 있는 것이 좋습니다. 다행히 Kubernetes 기반 앱의 나머지와 동일한 프로세스와 도구를 사용 하 여 Docker 컨테이너에 Azure Functions을 래핑하고 배포할 수 있습니다.

## <a name="when-does-it-make-sense-to-use-containers-with-serverless"></a>서버를 사용 하지 않는 컨테이너를 사용 하는 경우는 언제 인가요?

기본적으로 서버를 사용 하지 않는 함수는 실행 되는 플랫폼에 대해 알지 못합니다. 그러나 경우에 따라 코드를 실행할 컨테이너 이미지를 사용자 지정 하는 것이 중요 한 특정 요구 사항이 있을 수 있습니다. 함수가 특정 언어 버전을 사용 하거나 기본 이미지에서 지원 하지 않는 종속성 또는 구성 요구 사항이 있으므로 사용자 지정 이미지를 사용 하는 것이 좋습니다. 이러한 경우 사용자 고유의 컨테이너를 사용자 지정 하 고 사용자 지정 Docker 컨테이너에 함수를 배포 하는 것이 적합할 수 있습니다.

## <a name="when-should-you-avoid-using-containers-with-azure-functions"></a>Azure Functions 컨테이너를 사용 하지 않는 경우는 언제 인가요?

사용자 고유의 컨테이너를 사용 하는 경우 함수에 대 한 소비 계획 청구를 활용 하는 것이 도움이 될 수 있습니다. 또한 Docker 컨테이너를 사용 하는 것 외에 함수를 고유한 Kubernetes 클러스터에 배포 하는 경우에는 Azure Functions에서 제공 하는 기본 제공 크기 조정을 더 이상 활용 하지 않아도 됩니다. 아래에 설명 된 Kubernetes ' 크기 조정 기능을 사용 해야 합니다.

## <a name="how-to-combine-serverless-and-docker-containers"></a>서버 리스 및 Docker 컨테이너를 결합 하는 방법

Docker 컨테이너에서 Azure 함수를 래핑하려면 Azure Functions Core Tools를 설치한 후 다음 명령을 실행 합니다.

```console
func init ProjectName --docker
```

다음 옵션 중에서 원하는 작업자 런타임을 선택 합니다.

- `dotnet`(C#)
- `node`(JavaScript)
- `python`

프로젝트를 만들 때 Dockerfile이 포함 됩니다. 이제 함수를 로컬에서 만들고 테스트할 수 있습니다. `docker build` 및 `docker run` 명령을 사용 하 여 빌드하고 실행 합니다. Docker 지원을 사용 하 여 Azure Functions 빌드를 시작 하는 자세한 단계는 [사용자 지정 이미지를 사용 하 여 Linux에서 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image) 자습서를 참조 하세요.

## <a name="how-to-combine-serverless-and-kubernetes-with-keda"></a>서버 리스 및 Kubernetes를 KEDA와 결합 하는 방법

Azure 함수는 지정 된 함수를 대상으로 하는 이벤트 비율에 따라 수요를 충족 하도록 자동으로 확장 됩니다. 또한 Kubernetes를 활용 하 여 함수를 호스팅하고 Kubernetes 기반 이벤트 기반 자동 크기 조정 또는 KEDA를 사용할 수 있습니다. 이벤트가 발생 하지 않을 때 KEDA는 0 개의 인스턴스로 확장 될 수 있으며, 이벤트에 대 한 응답으로 수평 pod autoscaler를 사용 하 여 요청에 맞게 컨테이너 수를 확장할 수 있습니다. [KEDA를 사용 하 여 Azure 함수 크기 조정에 대해 자세히 알아보세요](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda).

## <a name="references"></a>참조 항목

- [Docker 컨테이너에서 Azure Functions 실행](https://markheath.net/post/azure-functions-docker)
- [사용자 지정 이미지를 사용 하 여 Linux에서 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)
- [Kubernetes 이벤트 기반 자동 크기 조정을 사용 하는 Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)

>[!div class="step-by-step"]
>[이전](leverage-serverless-functions.md)
>[다음](deploy-containers-azure.md)
