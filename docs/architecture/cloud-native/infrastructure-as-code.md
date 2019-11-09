---
title: 코드로 서의 인프라
description: Azure 용 클라우드 네이티브 .NET 앱 설계 | 코드로 서의 인프라
ms.date: 06/30/2019
ms.openlocfilehash: 3957da68ac28774f899f49fb181a29c2435902f8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841782"
---
# <a name="infrastructure-as-code"></a>코드로 서의 인프라

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

클라우드 네이티브 응용 프로그램은 모든 종류의 환상적인 PaaS (platform as a service) 구성 요소를 활용 하는 경향이 있습니다. Azure와 같은 클라우드 플랫폼에서 이러한 구성 요소에는 storage, Service Bus 및 SignalR 서비스와 같은 항목이 포함 될 수 있습니다. 응용 프로그램이 점점 복잡해 지 면 사용 중인 이러한 서비스 수가 증가할 수 있습니다. 지속적인 업데이트를 환경에 수동으로 배포 하는 일반적인 모델을 중단 하는 것과 마찬가지로 신속한 변경으로 인해 중앙 집중식 IT 그룹이 환경을 관리 하는 모델이 중단 됩니다.

빌드 환경도 자동화 될 수 있습니다. 프로세스를 간편 하 게 만들 수 있는 다양 한 기능을 잘 생각 하 고 있습니다.

## <a name="azure-resource-manager-templates"></a>Azure Resource Manager 템플릿

Azure Resource Manager 템플릿은 Azure에서 다양 한 리소스를 정의 하는 데 사용 되는 JSON 기반 언어입니다. 기본 스키마는 그림 11-10와 같습니다.

```json
{
  "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentTemplate.json#",
  "contentVersion": "",
  "apiProfile": "",
  "parameters": {  },
  "variables": {  },
  "functions": [  ],
  "resources": [  ],
  "outputs": {  }
}
```

**그림 11-10** -리소스 관리자 템플릿에 대 한 스키마

이 템플릿 내에서 다음과 같이 리소스 섹션 안에 저장소 컨테이너를 정의할 수 있습니다.

```json
"resources": [
    {
      "type": "Microsoft.Storage/storageAccounts",
      "name": "[variables('storageAccountName')]",
      "location": "[parameters('location')]",
      "apiVersion": "2018-07-01",
      "sku": {
        "name": "[parameters('storageAccountType')]"
      },
      "kind": "StorageV2",
      "properties": {}
    }
  ],
```

**그림 11-11** -리소스 관리자 템플릿에 정의 된 저장소 계정의 예

템플릿을 매개 변수화 하 여 개발, QA 및 프로덕션 환경을 정의 하는 다른 설정으로 하나의 템플릿을 재사용할 수 있습니다. 이렇게 하면 낮은 환경과 다르게 설정 된 더 높은 환경으로 마이그레이션할 때 예상치 않게 됩니다. 템플릿에 정의 된 리소스는 일반적으로 Azure의 단일 리소스 그룹 내에 생성 됩니다 (단일 리소스 관리자 템플릿에서 여러 리소스 그룹을 정의할 수 있지만 비정상적인). 이렇게 하면 리소스 그룹 전체를 삭제 하 여 환경을 매우 쉽게 삭제할 수 있습니다. 비용 분석은 리소스 그룹 수준에서 실행 될 수도 있으므로 각 환경의 비용을 신속 하 게 확인할 수 있습니다.

새 템플릿에서 시작 하거나 기존 템플릿에서 추가할 때 레그를 제공 하는 GitHub의 [Azure 빠른 시작 템플릿](https://github.com/Azure/azure-quickstart-templates) 프로젝트에 정의 된 많은 예제 템플릿이 있습니다.

리소스 관리자 템플릿은 다양 한 방법으로 실행할 수 있습니다. 가장 간단한 방법은 단순히 Azure Portal에 붙여 넣는 것입니다. 실험적 배포의 경우이 방법은 매우 빠르게 수행할 수 있습니다. Azure DevOps에서 빌드 또는 릴리스 프로세스의 일부로 실행 될 수도 있습니다. Azure에 대 한 연결을 활용 하 여 템플릿을 실행 하는 작업이 있습니다. 리소스 관리자 템플릿에 대 한 변경 내용은 증분 방식으로 적용 됩니다. 즉, 새 리소스를 추가 하려면 단순히 템플릿에 추가 해야 합니다. 도구는 템플릿에 정의 된 원하는 리소스 그룹을 사용 하 여 현재 리소스 그룹의 diff를 처리 합니다. 그러면 리소스는 템플릿에 정의 된 것과 일치 하도록 만들어지거나 변경 됩니다.  

## <a name="terraform"></a>Terraform

리소스 관리자 템플릿의 인식 단점은 Azure 클라우드와 관련 된 것입니다. 둘 이상의 클라우드에서 리소스를 포함 하는 응용 프로그램을 만드는 것은 드뭅니다. 그러나 비즈니스에서 화려하 작동 시간을 사용 하는 경우 여러 클라우드를 지 원하는 비용이 유용할 수 있습니다. 모든 클라우드에서 사용할 수 있는 하나의 템플릿 언어가 있다면 개발자 기술도 훨씬 더 이식할 수 있습니다.

이 작업을 수행 하는 몇 가지 기술이 있습니다. 해당 공간에서 가장 성숙한 제품을 [Terraform](https://www.terraform.io/)이라고 합니다. Terraform은 Azure, Google Cloud Platform, AWS 및 AliCloud와 같은 모든 주요 클라우드 플레이어를 지원 하며 Heroku 및 DigitalOcean와 같은 수십 개의 사소한 플레이어도 지원 합니다. JSON을 템플릿 정의 언어로 사용 하는 대신 약간 더 간결한 YAML을 사용 합니다.

이전 리소스 관리자 템플릿과 동일한 작업을 수행 하는 예제 Terraform 파일 (그림 11-11)은 그림 11-12에 나와 있습니다.

```terraform
provider "azurerm" {
  version = "=1.28.0"
}

resource "azurerm_resource_group" "test" {
  name     = "production"
  location = "West US"
}

resource "azurerm_storage_account" "testsa" {
  name                     = "${var.storageAccountName}"
  resource_group_name      = "${azurerm_resource_group.testrg.name}"
  location                 = "${var.region}"
  account_tier             = "${var.tier}"
  account_replication_type = "${var.replicationType}"

}
```

**그림 11-12** -리소스 관리자 템플릿의 예

Terraform은 템플릿에 오류가 발생 하 여 리소스를 배포할 수 없는 경우 적절 한 오류 메시지를 제공 하는 데 더 나은 작업을 수행 합니다. 리소스 관리자 템플릿에 몇 가지 지속적인 과제가 있는 영역입니다. 빌드 단계에서 초기에 템플릿 오류를 catch 하는 데 사용할 수 있는 매우 편리한 유효성 검사 작업도 있습니다.

리소스 관리자 템플릿과 마찬가지로 Terraform 템플릿을 배포 하는 데 사용할 수 있는 명령줄 도구가 있습니다. Terraform 템플릿을 확인 하 고 적용할 수 있는 Azure Pipelines에 커뮤니티에서 만든 작업도 있습니다.

Terraform 또는 리소스 관리자 템플릿이 새로 만든 데이터베이스에 대 한 연결 문자열과 같은 흥미로운 값을 출력 하는 경우 빌드 파이프라인에서 캡처되고 후속 작업에 사용 될 수 있습니다.

>[!div class="step-by-step"]
>[이전](devops.md)
>[다음](application-bundles.md)
