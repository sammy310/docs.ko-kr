---
title: 클라우드 네이티브 서비스에 대 한 컨테이너 및 서버를 사용 하지 않는 방식 조합
description: 서버를 사용 하지 않는 방법으로 컨테이너와 Kubernetes 결합
ms.date: 05/13/2020
ms.openlocfilehash: 67eee89659026db06eb16ef6f1154ab6935725a4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614203"
---
# <a name="combining-containers-and-serverless-approaches"></a>컨테이너 및 서버리스 접근 방식 결합

클라우드 네이티브 응용 프로그램은 일반적으로 컨테이너 및 오케스트레이션을 활용 하는 서비스를 구현 합니다. 응용 프로그램의 서비스를 Azure Functions로 노출 하는 경우가 종종 있습니다. 그러나 Kubernetes에 배포 된 클라우드 네이티브 앱을 사용 하는 경우이 동일한 도구 집합 내에서 Azure Functions를 활용 하는 것이 좋습니다. 다행히 Kubernetes 기반 앱의 나머지와 동일한 프로세스 및 도구를 사용 하 여 Docker 컨테이너 내 Azure Functions을 래핑하고 배포할 수 있습니다.

## <a name="when-does-it-make-sense-to-use-containers-with-serverless"></a>서버를 사용 하지 않는 컨테이너를 사용 하는 경우는 언제 인가요?

Azure 함수는 배포 되는 플랫폼에 대해 알지 못합니다. 일부 시나리오에서는 특정 요구 사항이 있을 수 있으며 함수 코드가 실행 될 환경을 사용자 지정 해야 합니다. 종속성 또는 기본 이미지에서 지원 하지 않는 구성을 지 원하는 사용자 지정 이미지가 필요 합니다. 이러한 경우 사용자 지정 Docker 컨테이너에 함수를 배포 하는 것이 좋습니다.

## <a name="when-should-you-avoid-using-containers-with-azure-functions"></a>Azure Functions 컨테이너를 사용 하지 않는 경우는 언제 인가요?

소비 청구를 사용 하려는 경우에는 컨테이너에서 함수를 실행할 수 없습니다. 또한 Kubernetes 클러스터에 함수를 배포 하는 경우에는 Azure Functions에서 제공 하는 기본 제공 크기 조정을 더 이상 활용 하지 못합니다. 이 챕터의 앞부분에서 설명한 Kubernetes의 크기 조정 기능을 사용 해야 합니다.

## <a name="how-to-combine-serverless-and-docker-containers"></a>서버 리스 및 Docker 컨테이너를 결합 하는 방법

Docker 컨테이너에서 Azure 함수를 래핑하려면 [Azure Functions Core Tools](https://github.com/Azure/azure-functions-core-tools) 를 설치한 후 다음 명령을 실행 합니다.

```console
func init ProjectName --worker-runtime dotnet --docker
```

프로젝트를 만들 때 Dockerfile 및에 구성 된 작업자 런타임이 포함 됩니다 `dotnet` . 이제 함수를 로컬에서 만들고 테스트할 수 있습니다. 및 명령을 사용 하 여 빌드하고 `docker build` 실행 `docker run` 합니다. Docker 지원을 사용 하 여 Azure Functions 빌드를 시작 하는 자세한 단계는 [사용자 지정 이미지를 사용 하 여 Linux에서 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image) 자습서를 참조 하세요.

## <a name="how-to-combine-serverless-and-kubernetes-with-keda"></a>서버 리스 및 Kubernetes를 KEDA와 결합 하는 방법

이 장에서는 Azure Functions의 플랫폼이 수요를 충족 하도록 자동으로 확장 됨을 확인 했습니다. 그러나 컨테이너 화 된 함수를 AKS에 배포 하는 경우 기본 제공 되는 크기 조정 기능이 손실 됩니다. 그러면 [KEDA (Kubernetes 기반 이벤트 기반)](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)가 제공 됩니다. 컨테이너 화 된 함수를 포함 하기 위해 세부적인 자동 크기 조정을 사용할 수 있습니다 `event-driven Kubernetes workloads,` .

KEDA는 Docker 컨테이너의 함수 런타임에 대 한 이벤트 기반 크기 조정 기능을 제공 합니다. KEDA는 로드에 따라 0 개 인스턴스 (이벤트가 발생 하지 않는 경우)에서로 확장 될 수 있습니다 `n instances` . Kubernetes autoscaler (수평 Pod Autoscaler)에 사용자 지정 메트릭을 노출 하 여 자동 크기 조정을 가능 하 게 합니다. KEDA에서 함수 컨테이너를 사용 하면 Kubernetes 클러스터에서 서버를 사용 하지 않는 함수 기능을 복제할 수 있습니다.

이제 KEDA 프로젝트를 CNCF (Cloud Native 컴퓨팅 Foundation)에서 관리 하는 것이 좋습니다.

>[!div class="step-by-step"]
>[이전](leverage-serverless-functions.md)
>[다음](deploy-containers-azure.md)
