---
title: 코드 제공 인프라(Infrastructure as code)
description: 클라우드 네이티브 응용 프로그램을 사용 하 여 IaC (Infrastructure as Code) 수용
ms.date: 05/13/2020
ms.openlocfilehash: cfc9e1f0b2733048d5921de5a0400998c282b1fa
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613956"
---
# <a name="infrastructure-as-code"></a>코드 제공 인프라(Infrastructure as code)

클라우드 네이티브 시스템은 마이크로 서비스, 컨테이너 및 최신 시스템 디자인을 도입 하 여 속도와 민첩성을 구현 합니다. 일관 되 고 품질 코드를 보장 하는 자동화 된 빌드 및 릴리스 단계를 제공 합니다. 그러나이는 스토리의 일부일 뿐입니다. 이러한 시스템이 실행 되는 클라우드 환경을 프로 비전 하려면 어떻게 해야 하나요?

최신 클라우드 네이티브 응용 프로그램은 인프라를 코드로, 또는 [로](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)널리 승인 된 사례를 수용 합니다 `IaC` .  IaC를 사용 하면 플랫폼 프로 비전을 자동화할 수 있습니다. 기본적으로 DevOps 사례에 테스트 및 버전 관리와 같은 소프트웨어 엔지니어링 사례를 적용 합니다. 인프라 및 배포는 자동화 되 고 일관 되며 반복 가능 합니다. 지속적인 배달과 수동 배포의 기존 모델을 자동화 하는 것 처럼, IaC (Infrastructure as Code)는 응용 프로그램 환경을 관리 하는 방식으로 발전 하 고 있습니다.

ARM (Azure Resource Manager), Terraform 및 Azure CLI (명령줄 인터페이스)와 같은 도구를 사용 하 여 필요한 클라우드 인프라를 선언적으로 스크립팅할 수 있습니다.

## <a name="azure-resource-manager-templates"></a>Azure 리소스 관리자 템플릿

ARM은 [Azure Resource Manager](https://azure.microsoft.com/documentation/articles/resource-group-overview/)를 나타냅니다. Azure에 기본 제공 되 고 API 서비스로 노출 되는 API 프로 비전 엔진입니다. ARM을 사용 하면 조정 된 단일 작업에서 Azure 리소스 그룹에 포함 된 리소스를 배포, 업데이트, 삭제 및 관리할 수 있습니다. 필요한 리소스와 해당 구성을 지정 하는 JSON 기반 템플릿을 엔진에 제공 합니다. ARM은 종속성의 올바른 순서에 따라 배포를 자동으로 오케스트레이션 합니다. 엔진은 멱 등 성를 확인 합니다. 동일한 구성으로 원하는 리소스가 이미 존재 하는 경우 프로 비전은 무시 됩니다.

Azure Resource Manager 템플릿은 Azure에서 다양 한 리소스를 정의 하는 데 사용 되는 JSON 기반 언어입니다. 기본 스키마는 그림 10-14와 같습니다.

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

**그림 10-14** -리소스 관리자 템플릿에 대 한 스키마

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

**그림 10-15** -리소스 관리자 템플릿에 정의 된 저장소 계정의 예

ARM 템플릿은 동적 환경 및 구성 정보를 사용 하 여 매개 변수화 할 수 있습니다. 이렇게 하면 개발, QA, 프로덕션 등의 다른 환경을 정의 하는 데 다시 사용할 수 있습니다. 일반적으로 템플릿은 단일 Azure 리소스 그룹 내에 모든 리소스를 만듭니다. 필요한 경우 단일 리소스 관리자 템플릿에서 여러 리소스 그룹을 정의할 수 있습니다. 리소스 그룹 자체를 삭제 하 여 환경의 모든 리소스를 삭제할 수 있습니다. 비용 분석은 리소스 그룹 수준에서 실행 될 수도 있으므로 각 환경의 비용을 신속 하 게 확인할 수 있습니다.

GitHub의 [Azure 빠른 시작 템플릿](https://github.com/Azure/azure-quickstart-templates) 프로젝트에서 사용할 수 있는 많은 예제 또는 ARM 템플릿이 있습니다. 새 템플릿을 만들거나 기존 템플릿을 수정 하는 데 도움이 될 수 있습니다.

리소스 관리자 템플릿은 다양 한 방법으로 실행할 수 있습니다. 가장 간단한 방법은 단순히 Azure Portal에 붙여 넣는 것입니다. 실험적 배포의 경우이 방법은 빠르게 수행할 수 있습니다. Azure DevOps에서 빌드 또는 릴리스 프로세스의 일부로 실행 될 수도 있습니다. Azure에 대 한 연결을 활용 하 여 템플릿을 실행 하는 작업이 있습니다. 리소스 관리자 템플릿에 대 한 변경 내용은 증분 방식으로 적용 됩니다. 즉, 새 리소스를 추가 하려면 단순히 템플릿에 추가 해야 합니다. 도구는 현재 리소스와 템플릿에 정의 된 리소스 간의 차이점을 조정 합니다. 그러면 리소스는 템플릿에 정의 된 것과 일치 하도록 만들어지거나 변경 됩니다.  

## <a name="terraform"></a>Terraform

클라우드 네이티브 응용 프로그램은 종종로 생성 됩니다 `cloud agnostic` . 즉, 응용 프로그램이 특정 클라우드 공급 업체와 긴밀 하 게 결합 되지 않으며 공용 클라우드에 배포할 수 있습니다.

[Terraform](https://www.terraform.io/) 은 모든 주요 클라우드 플레이어에서 클라우드 네이티브 응용 프로그램을 프로 비전 할 수 있는 상용 템플릿 도구입니다. Azure, GOOGLE CLOUD PLATFORM, AWS 및 alicloud. JSON을 템플릿 정의 언어로 사용 하는 대신 약간 더 간결한 YAML을 사용 합니다.

이전 리소스 관리자 템플릿과 동일한 작업을 수행 하는 예제 Terraform 파일 (그림 10-15)은 그림 10-16에 나와 있습니다.

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

**그림 10-16** -리소스 관리자 템플릿의 예

Terraform도 문제 템플릿에 대 한 직관적인 오류 메시지를 제공 합니다. 빌드 단계에서 초기에 템플릿 오류를 catch 하는 데 사용할 수 있는 편리한 유효성 검사 작업도 있습니다.

리소스 관리자 템플릿과 마찬가지로, 명령줄 도구를 사용 하 여 Terraform 템플릿을 배포할 수 있습니다. Terraform 템플릿을 확인 하 고 적용할 수 있는 Azure Pipelines에 커뮤니티에서 만든 작업도 있습니다.

경우에 따라 Terraform 및 ARM 템플릿에서는 새로 만든 데이터베이스에 대 한 연결 문자열과 같은 의미 있는 값을 출력 합니다. 이 정보는 빌드 파이프라인에서 캡처되고 후속 작업에 사용 될 수 있습니다.

## <a name="azure-cli-scripts-and-tasks"></a>스크립트 및 작업 Azure CLI

마지막으로 [Azure CLI](https://docs.microsoft.com/cli/azure/) 활용 하 여 클라우드 인프라를 선언적으로 스크립팅할 수 있습니다. 거의 모든 Azure 리소스를 프로 비전 하 고 구성 하기 위해 스크립트를 생성, 검색 및 공유할 수 Azure CLI. CLI는 gentle 학습 곡선으로 간단 하 게 사용할 수 있습니다. 스크립트는 PowerShell 또는 Bash 내에서 실행 됩니다. 특히 ARM 템플릿과 비교할 때 간단 하 게 디버깅할 수 있습니다.

Azure CLI 스크립트는 인프라를 분해 하 고 다시 배포 해야 할 때 제대로 작동 합니다. 기존 환경 업데이트는 어려울 수 있습니다. 많은 CLI 명령은 idempotent 되지 않습니다. 즉, 리소스가 이미 있는 경우에도 실행 될 때마다 리소스를 다시 만듭니다. 항상 각 리소스가 있는지 확인 하는 코드를 추가 하 여 만들 수 있습니다. 그러나 이렇게 하면 스크립트가 너무 커지고 관리 하기 어려울 수 있습니다.

이러한 스크립트는 Azure DevOps 파이프라인에로 포함 될 수도 있습니다 `Azure CLI tasks` . 파이프라인을 실행 하면 스크립트가 호출 됩니다.

그림 10-17에서는 Azure CLI 버전 및 구독의 세부 정보를 나열 하는 YAML 코드 조각을 보여 줍니다. 인라인 스크립트에 Azure CLI 명령을 포함 하는 방법을 확인 합니다.

```yaml
- task: AzureCLI@2
  displayName: Azure CLI
  inputs:
    azureSubscription: <Name of the Azure Resource Manager service connection>
    scriptType: ps
    scriptLocation: inlineScript
    inlineScript: |
      az --version
      az account show
```

**그림 10-17** -Azure CLI 스크립트

문서에서 [코드로 서의 인프라 란 무엇](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)이며, 제작자 Sam Guckenheimer는 "IaC를 구현 하는 팀이 안정적인 환경을 신속 하 고 대규모로 제공할 수 있는 방법에 대해 설명 합니다. 팀은 환경을 수동으로 구성 하는 것을 방지 하 고 코드를 통해 환경의 원하는 상태를 표시 하 여 일관성을 적용 합니다. IaC를 사용 하 여 인프라를 배포 하는 것은 반복 가능 하며, 구성 드리프트 또는 누락 종속성으로 인 한 런타임 문제를 방지 DevOps 팀은 통합 된 사례 및 도구 집합과 함께 작업 하 여 응용 프로그램 및 지원 인프라를 신속 하 고 안정적 이며 대규모로 제공할 수 있습니다. "

>[!div class="step-by-step"]
>[이전](feature-flags.md)
>[다음](application-bundles.md)
