---
title: Azure에 eShopOnContainers 배포
description: Azure Kubernetes Service, 투구 및 DevSpaces를 사용 하 여 eShopOnContainers 응용 프로그램을 배포 합니다.
ms.date: 04/20/2020
ms.openlocfilehash: a3eacedac946cb25cf3cced305d7921e29f0d204
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895590"
---
# <a name="deploying-eshoponcontainers-to-azure"></a>Azure에 eShopOnContainers 배포

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

EShopOnContainers 응용 프로그램은 다양 한 Azure 플랫폼에 배포할 수 있습니다. Azure Kubernetes Services (AKS)에 응용 프로그램을 배포 하는 것이 좋습니다. Kubernetes 배포 도구인 투구를 사용 하 여 배포 복잡성을 줄일 수 있습니다. 개발자는 필요에 따라 Kubernetes에 대 한 Azure Dev Spaces를 구현 하 여 개발 프로세스를 간소화할 수 있습니다.

## <a name="azure-kubernetes-service"></a>Azure Kubernetes Service

AKS에서 eShop를 호스트 하기 위해 첫 번째 단계는 AKS 클러스터를 만드는 것입니다. 이렇게 하려면 Azure Portal를 사용할 수 있습니다. 그러면 필요한 단계를 안내 합니다. Azure CLI에서 클러스터를 만들어 RBAC (역할 기반 Access Control) 및 응용 프로그램 라우팅을 사용 하도록 설정할 수도 있습니다. EShopOnContainers ' 설명서에서는 고유한 AKS 클러스터를 만드는 단계에 대해 자세히 설명 합니다. 만든 후에는 Kubernetes 대시보드에서 클러스터에 액세스 하 고 관리할 수 있습니다.

이제 투구와 Tiller를 활용 하 여 클러스터에 eShop 응용 프로그램을 배포할 수 있습니다.

## <a name="deploying-to-azure-kubernetes-service-using-helm"></a>투구를 사용 하 여 Azure Kubernetes Service에 배포

투구는 Kubernetes에서 직접 작동 하는 응용 프로그램 패키지 관리자 도구입니다. Kubernetes 응용 프로그램을 정의, 설치 및 업그레이드 하는 데 도움이 됩니다. 간단한 앱은 사용자 지정 CLI 스크립트 또는 간단한 배포 파일을 사용 하 여 AKS에 배포할 수 있지만 복잡 한 앱은 여러 Kubernetes 개체를 포함 하 고 투구의 이점을 누릴 수 있습니다.

투구를 사용 하는 응용 프로그램에는 투구 패키지의 응용 프로그램 및 구성을 선언적으로 설명 하는 투구 차트 라는 텍스트 기반 구성 파일이 포함 되어 있습니다. 차트는 표준 YAML 형식 파일을 사용 하 여 관련 된 Kubernetes 리소스 집합을 설명 합니다. 설명 하는 응용 프로그램 코드와 함께 버전이 지정 됩니다. 투구 차트는 설명 하는 설치 요구 사항에 따라 단순에서 복잡 하 게 됩니다.

투구는 투구 차트를 사용 하 고 Tiller 라는 서버 구성 요소에 명령을 시작 하는 명령줄 클라이언트 도구로 구성 됩니다. Tiller는 Kubernetes API와 통신 하 여 컨테이너 화 된 워크 로드의 올바른 프로 비전을 보장 합니다. 투구는 클라우드 기본 컴퓨팅 기반에 의해 유지 관리 됩니다.

다음 yaml 파일은 투구 템플릿을 제공 합니다.

```yaml
apiVersion: v1
kind: Service
metadata:
  name: {{ .Values.app.svc.marketing }}
  labels:
    app: {{ template "marketing-api.name" . }}
    chart: {{ template "marketing-api.chart" . }}
    release: {{ .Release.Name }}
    heritage: {{ .Release.Service }}
spec:
  type: {{ .Values.service.type }}
  ports:
    - port: {{ .Values.service.port }}
      targetPort: http
      protocol: TCP
      name: http
  selector:
    app: {{ template "marketing-api.name" . }}
    release: {{ .Release.Name }}
```

템플릿에서 키/값 쌍의 동적 집합을 설명 하는 방법을 확인 합니다. 템플릿이 호출 되 면 다른 yaml 기반 구성 파일에서 중괄호로 묶인 값을 가져옵니다.

/K8s/helm 폴더에서 eShopOnContainers 투구 차트를 찾을 수 있습니다. 그림 2-6에서는 응용 프로그램의 다양 한 구성 요소가 투구에서 사용 되는 폴더 구조로 구성 되 고, 관리 되는 배포를 정의 하는 방법을 보여 줍니다.

![eShopOnContainers 아키텍처](./media/eshoponcontainers-helm-folder.png)
**그림 2-6**. EShopOnContainers 투구 폴더입니다.

각 개별 구성 요소는 `helm install` 명령을 사용 하 여 설치 됩니다. eShop에는 각 투구 차트를 사용 하 여 구성 요소를 반복 하 고 설치 하는 "모두 배포" 스크립트가 포함 되어 있습니다. 그 결과, 팀의 모든 사용자가 한 줄 스크립트 명령을 사용 하 여 AKS 클러스터에 배포할 수 있는 반복 가능한 프로세스가 소스 제어에서 응용 프로그램과 함께 사용 됩니다.

> 투구 버전 3은 공식적으로 Tiller 서버 구성 요소에 대 한 필요성을 제거 합니다. 이 개선 사항에 대 한 자세한 내용은 [여기](https://medium.com/better-programming/why-is-tiller-missing-in-helm-3-2347c446714)를 참조 하세요.

## <a name="azure-dev-spaces"></a>Azure Dev 공간

클라우드 네이티브 응용 프로그램을 신속 하 게 확장 하 여 큰 계산 리소스를 실행 해야 할 수 있습니다. 이러한 시나리오에서는 전체 응용 프로그램을 개발 컴퓨터 (특히 랩톱)에서 호스팅할 수 없습니다. Azure Dev Spaces AKS를 사용 하 여이 문제를 해결 하도록 설계 되었습니다. 개발자는이를 통해 AKS development 클러스터에 응용 프로그램의 나머지 부분을 호스트 하는 동안 로컬 버전의 서비스를 사용할 수 있습니다.

개발자는 전체 컨테이너 화 된 응용 프로그램을 포함 하는 AKS 클러스터에서 실행 중인 (개발) 인스턴스를 공유 합니다. 그러나 해당 컴퓨터에 설정 된 개인 공간을 사용 하 여 로컬에서 서비스를 개발 합니다. 준비가 되 면 종속성을 복제 하지 않고 AKS 클러스터에서 종단 간 테스트를 진행 합니다. Azure Dev Spaces AKS의 서비스를 사용 하 여 로컬 컴퓨터의 코드를 병합 합니다. 팀 멤버는 실제 AKS 환경에서 변경 내용의 동작을 확인할 수 있습니다. 개발자는 Visual Studio 2017 또는 Visual Studio Code를 사용 하 여 Kubernetes에서 직접 코드를 신속 하 게 반복 하 고 디버그할 수 있습니다.

그림 2-7에서 개발자 Susie가 개발 공간에 업데이트 된 버전의 Bikes 마이크로 서비스를 배포한 것을 볼 수 있습니다. 그런 다음 사용자의 스페이스 이름으로 시작 하는 사용자 지정 URL을 사용 하 여 변경 내용을 테스트할 수 있습니다 (susie.s.dev.myapp.eus.azds.io).

![eShopOnContainers 아키텍처](./media/azure-devspaces-one.png)
**그림 2-7**. 개발자 Susie 자신의 자전거 마이크로 서비스 버전을 배포 하 고 테스트 합니다.

동시에 개발자 John은 예약 마이크로 서비스 사용자 지정 하 고 변경 내용을 테스트 해야 합니다. 그림 2-8에 표시 된 것 처럼 Susie의 변경 내용과 충돌 하지 않고 자신의 개발자 공간에 변경 내용을 배포 합니다. 그런 다음 John은 자신의 URL (john.s.dev.myapp.eus.azds.io) 이름 앞에 접두사를 사용 하 여 변경 내용을 테스트 합니다.

![eShopOnContainers 아키텍처](./media/azure-devspaces-two.png)
**그림 2-8**. 개발자는 자신의 예약 마이크로 서비스 버전을 배포 하 고 다른 개발자와 충돌 하지 않고 테스트 합니다.

Azure Dev Spaces를 사용 하 여 팀은 변경 내용을 독립적으로 변경, 배포 및 테스트 하는 동시에 AKS를 사용 하 여 직접 작업할 수 있습니다. 이 방법은 모든 개발자가 자신의 AKS 환경을 효과적으로 사용 하기 때문에 별도의 전용 호스팅 환경에 대 한 필요성을 줄입니다. 개발자는 CLI를 사용 하 여 Azure Dev Spaces 작업 하거나 응용 프로그램을 시작 하 여 Visual Studio에서 직접 Azure Dev Spaces 수 있습니다. [Azure Dev Spaces 작동 하 고 구성 되는 방법에 대해 자세히 알아보세요.](https://docs.microsoft.com/azure/dev-spaces/how-dev-spaces-works)

## <a name="azure-functions-and-logic-apps-serverless"></a>Azure Functions 및 Logic Apps (서버 리스)

EShopOnContainers 샘플에는 온라인 마케팅 캠페인을 추적 하는 기능이 포함 되어 있습니다. Azure Function은 지정 된 캠페인 ID에 대 한 마케팅 캠페인 세부 정보를 추적 하는 데 사용 됩니다. 전체 마이크로 서비스을 만드는 대신 단일 Azure 함수는 더 간단 하 고 충분 합니다. 특히 Kubernetes에서 실행 되도록 구성 된 경우 간단한 빌드 및 배포 모델이 Azure Functions. 함수 배포는 ARM (Azure Resource Manager) 템플릿 및 Azure CLI를 사용 하 여 스크립팅됩니다. 이 캠페인 서비스는 고객에 게는 없으며 단일 작업을 호출 하 여 Azure Functions에 대 한 훌륭한 후보가 됩니다. 함수에는 데이터베이스 연결 문자열 데이터 및 이미지 기본 URI 설정을 포함 하 여 최소한의 구성이 필요 합니다. Azure Portal에서 Azure Functions를 구성 합니다.

>[!div class="step-by-step"]
>[이전](map-eshoponcontainers-azure-services.md)
>[다음](centralized-configuration.md)
