---
title: 클라우드 네이티브 애플리케이션 번들
description: Azure 용 클라우드 네이티브 .NET 앱 설계 | 클라우드 네이티브 응용 프로그램 번들
ms.date: 06/30/2019
ms.openlocfilehash: 6f85ca14ff4d17f9c7a90a9ace51a1448b89fcb3
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895675"
---
# <a name="cloud-native-application-bundles"></a>클라우드 네이티브 애플리케이션 번들

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

클라우드 네이티브 응용 프로그램의 핵심 속성은 클라우드의 속성을 활용 하 여 개발 속도를 높이는 것입니다. 이는 대개 전체 응용 프로그램에서 다양 한 종류의 기술을 사용 하는 것을 의미 합니다. 응용 프로그램은 Docker 컨테이너에 제공 될 수 있으며, 일부 서비스는 Azure Functions 사용할 수 있는 반면, 다른 부분은 하드웨어 GPU 가속을 사용 하 여 대량 금속 서버에 할당 된 가상 컴퓨터에서 직접 실행 될 수 있습니다. 두 클라우드 네이티브 응용 프로그램이 동일 하지 않으므로 제공 하는 단일 메커니즘을 제공 하기가 어렵습니다.

Docker 컨테이너는 배포에 대 한 투구 차트를 사용 하 여 Kubernetes에서 실행 될 수 있습니다. Terraform 템플릿을 사용 하 여 Azure Functions을 할당할 수 있습니다. 마지막으로, 가상 머신은 Terraform을 사용 하 여 할당 될 수 있지만 Ansible를 사용 하 여 빌드됩니다. 이는 기술이 많은 기술 이며, 모든 것을 적절 한 패키지로 함께 패키지할 방법이 없었습니다. 지금까지.

CNABs (Cloud Native Application 번들)는 배포 된 응용 프로그램을 패키지 하는 사양을 개발 하기 위해 Microsoft, Docker 및 HashiCorp와 같은 다양 한 커뮤니티 관심이 있는 회사의 공동 작업입니다.

이 활동은 2018 년 12 월에 발표 되었으므로 더 큰 커뮤니티에 활동을 노출 하기 위해 수행 해야 하는 작업은 여전히 있습니다. 그러나 이미 [개방 된 사양과](https://github.com/deislabs/cnab-spec) [duffle](https://duffle.sh/)이라는 참조 구현이 있습니다. Go로 작성 된이 도구는 Docker와 Microsoft 간의 공동 작업입니다.

CNABs에는 여러 종류의 설치 기술이 포함 될 수 있습니다. 이를 통해 투구 차트, Terraform 템플릿, Ansible 플레이 북 등을 동일한 패키지에 함께 사용할 수 있습니다. 작성 된 패키지는 자체 포함 되 고 이식 가능 합니다. USB 스틱에서 설치할 수 있습니다.  패키지는 자신이 주장 하는 당사자 로부터 온 것임을 확인 하기 위해 암호화 서명 됩니다.

CNAB의 핵심은 라는 `bundle.json`파일입니다. 이 파일은 번들의 콘텐츠를 정의 합니다. 즉, Terraform 또는 이미지나 기타 항목입니다. 그림 11-9에서는 Terraform을 호출 하는 CNAB를 정의 합니다. 하지만 실제로는 Terraform을 호출 하는 데 사용 되는 호출 이미지를 정의 합니다. 패키지를 만들면 *cnab* 디렉터리에 있는 Docker 파일이 docker 이미지에 기본 제공 됩니다 .이 이미지는 번들에 포함 됩니다. 번들의 Docker 컨테이너 내부에 Terraform을 설치 하는 것은 사용자가 번들을 실행 하기 위해 컴퓨터에 Terraform을 설치 하지 않아도 된다는 것을 의미 합니다.

```json
{
    "name": "terraform",
    "version": "0.1.0",
    "schemaVersion": "v1.0.0-WD",
    "parameters": {
        "backend": {
            "type": "boolean",
            "defaultValue": false,
            "destination": {
                "env": "TF_VAR_backend"
            }
        }
    },
    "invocationImages": [
        {
        "imageType": "docker",
        "image": "cnab/terraform:latest"
        }
    ],
    "credentials": {
        "tenant_id": {
            "env": "TF_VAR_tenant_id"
        },
        "client_id": {
            "env": "TF_VAR_client_id"
        },
        "client_secret": {
            "env": "TF_VAR_client_secret"
        },
        "subscription_id": {
            "env": "TF_VAR_subscription_id"
        },
        "ssh_authorized_key": {
            "env": "TF_VAR_ssh_authorized_key"
        }
    },
    "actions": {
        "status": {
            "modifies": true
        }
    }
}
```

**그림 11-13** -예제 Terraform 파일

또한 `bundle.json` 는 Terraform으로 전달 되는 매개 변수 집합을 정의 합니다. 번들의 매개 변수화를 사용 하면 다양 한 환경에서 설치할 수 있습니다.

CNAB 형식만 유연 하 여 모든 클라우드에 사용할 수 있습니다. [Openstack](https://www.openstack.org/)과 같은 온-프레미스 솔루션에도 사용할 수 있습니다.

## <a name="devops-decisions"></a>DevOps 결정

이러한 도구는 DevOps 공간에 몇 가지 훌륭한 도구를 포함 하 고 있으며 성공 하는 방법에 대 한 방대한 서적 및 백서도 있습니다. DevOps 여행에서 시작 하기 위한 즐겨 찾는 책은 가상 회사가 NoOps에서 DevOps로 변환 하는 것을 따르는 [Phoenix 프로젝트](https://www.oreilly.com/library/view/the-phoenix-project/9781457191350/)입니다. 특정 한 가지 사항은 다음과 같습니다. DevOps는 복잡 한 클라우드 네이티브 응용 프로그램을 배포할 때 더 이상 "바람직한" 것은 아닙니다. 이는 요구 사항이 며 프로젝트를 시작할 때 계획 하 고이에 대해 자원을 지정 해야 합니다.

>[!div class="step-by-step"]
>[이전](infrastructure-as-code.md)
>[다음](summary.md)
