---
title: 코드 제공 인프라(Infrastructure as code)
description: 클라우드 네이티브 응용 프로그램을 사용 하 여 IaC (Infrastructure as Code) 수용
ms.date: 05/13/2020
ms.openlocfilehash: 5a7cd3a0b4906b1a4aec9e1015d6128867ae9963
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255446"
---
# <a name="infrastructure-as-code"></a><span data-ttu-id="7c9e0-103">코드 제공 인프라(Infrastructure as code)</span><span class="sxs-lookup"><span data-stu-id="7c9e0-103">Infrastructure as code</span></span>

<span data-ttu-id="7c9e0-104">클라우드 네이티브 시스템은 마이크로 서비스, 컨테이너 및 최신 시스템 디자인을 도입 하 여 속도와 민첩성을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-104">Cloud-native systems embrace microservices, containers, and modern system design to achieve speed and agility.</span></span> <span data-ttu-id="7c9e0-105">일관 되 고 품질 코드를 보장 하는 자동화 된 빌드 및 릴리스 단계를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-105">They provide automated build and release stages to ensure consistent and quality code.</span></span> <span data-ttu-id="7c9e0-106">그러나이는 스토리의 일부일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-106">But, that's only part of the story.</span></span> <span data-ttu-id="7c9e0-107">이러한 시스템이 실행 되는 클라우드 환경을 프로 비전 하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="7c9e0-107">How do you provision the cloud environments upon which these systems run?</span></span>

<span data-ttu-id="7c9e0-108">최신 클라우드 네이티브 응용 프로그램은 인프라를 코드로, 또는 [로](/azure/devops/learn/what-is-infrastructure-as-code)널리 승인 된 사례를 수용 합니다 `IaC` .</span><span class="sxs-lookup"><span data-stu-id="7c9e0-108">Modern cloud-native applications embrace the widely accepted practice of [Infrastructure as Code](/azure/devops/learn/what-is-infrastructure-as-code), or `IaC`.</span></span>  <span data-ttu-id="7c9e0-109">IaC를 사용 하면 플랫폼 프로 비전을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-109">With IaC, you automate platform provisioning.</span></span> <span data-ttu-id="7c9e0-110">기본적으로 DevOps 사례에 테스트 및 버전 관리와 같은 소프트웨어 엔지니어링 사례를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-110">You essentially apply software engineering practices such as testing and versioning to your DevOps practices.</span></span> <span data-ttu-id="7c9e0-111">인프라 및 배포는 자동화 되 고 일관 되며 반복 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-111">Your infrastructure and deployments are automated, consistent, and repeatable.</span></span> <span data-ttu-id="7c9e0-112">지속적인 배달과 수동 배포의 기존 모델을 자동화 하는 것 처럼, IaC (Infrastructure as Code)는 응용 프로그램 환경을 관리 하는 방식으로 발전 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-112">Just as continuous delivery automated the traditional model of manual deployments, Infrastructure as Code (IaC) is evolving how application environments are managed.</span></span>

<span data-ttu-id="7c9e0-113">ARM (Azure Resource Manager), Terraform 및 Azure CLI (명령줄 인터페이스)와 같은 도구를 사용 하 여 필요한 클라우드 인프라를 선언적으로 스크립팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-113">Tools like Azure Resource Manager (ARM), Terraform, and the Azure Command Line Interface (CLI) enable you to declaratively script the cloud infrastructure you require.</span></span>

## <a name="azure-resource-manager-templates"></a><span data-ttu-id="7c9e0-114">Azure 리소스 관리자 템플릿</span><span class="sxs-lookup"><span data-stu-id="7c9e0-114">Azure Resource Manager templates</span></span>

<span data-ttu-id="7c9e0-115">ARM은 [Azure Resource Manager](/azure/azure-resource-manager/management/overview)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-115">ARM stands for [Azure Resource Manager](/azure/azure-resource-manager/management/overview).</span></span> <span data-ttu-id="7c9e0-116">Azure에 기본 제공 되 고 API 서비스로 노출 되는 API 프로 비전 엔진입니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-116">It's an API provisioning engine that is built into Azure and exposed as an API service.</span></span> <span data-ttu-id="7c9e0-117">ARM을 사용 하면 조정 된 단일 작업에서 Azure 리소스 그룹에 포함 된 리소스를 배포, 업데이트, 삭제 및 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-117">ARM enables you to deploy, update, delete, and manage the resources contained in Azure resource group in a single, coordinated operation.</span></span> <span data-ttu-id="7c9e0-118">필요한 리소스와 해당 구성을 지정 하는 JSON 기반 템플릿을 엔진에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-118">You provide the engine with a JSON-based template that specifies the resources you require and their configuration.</span></span> <span data-ttu-id="7c9e0-119">ARM은 종속성의 올바른 순서에 따라 배포를 자동으로 오케스트레이션 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-119">ARM automatically orchestrates the deployment in the correct order respecting dependencies.</span></span> <span data-ttu-id="7c9e0-120">엔진은 멱 등 성를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-120">The engine ensures idempotency.</span></span> <span data-ttu-id="7c9e0-121">동일한 구성으로 원하는 리소스가 이미 존재 하는 경우 프로 비전은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-121">If a desired resource already exists with the same configuration, provisioning will be ignored.</span></span>

<span data-ttu-id="7c9e0-122">Azure Resource Manager 템플릿은 Azure에서 다양 한 리소스를 정의 하는 데 사용 되는 JSON 기반 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-122">Azure Resource Manager templates are a JSON-based language for defining various resources in Azure.</span></span> <span data-ttu-id="7c9e0-123">기본 스키마는 그림 10-14와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-123">The basic schema looks something like Figure 10-14.</span></span>

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

<span data-ttu-id="7c9e0-124">**그림 10-14** -리소스 관리자 템플릿에 대 한 스키마</span><span class="sxs-lookup"><span data-stu-id="7c9e0-124">**Figure 10-14** - The schema for a Resource Manager template</span></span>

<span data-ttu-id="7c9e0-125">이 템플릿 내에서 다음과 같이 리소스 섹션 안에 저장소 컨테이너를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-125">Within this template, one might define a storage container inside the resources section like so:</span></span>

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

<span data-ttu-id="7c9e0-126">**그림 10-15** -리소스 관리자 템플릿에 정의 된 저장소 계정의 예</span><span class="sxs-lookup"><span data-stu-id="7c9e0-126">**Figure 10-15** - An example of a storage account defined in a Resource Manager template</span></span>

<span data-ttu-id="7c9e0-127">ARM 템플릿은 동적 환경 및 구성 정보를 사용 하 여 매개 변수화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-127">An ARM template can be parameterized with dynamic environment and configuration information.</span></span> <span data-ttu-id="7c9e0-128">이렇게 하면 개발, QA, 프로덕션 등의 다른 환경을 정의 하는 데 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-128">Doing so enables it to be reused to define different environments, such as development, QA, or production.</span></span> <span data-ttu-id="7c9e0-129">일반적으로 템플릿은 단일 Azure 리소스 그룹 내에 모든 리소스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-129">Normally, the template creates all resources within a single Azure resource group.</span></span> <span data-ttu-id="7c9e0-130">필요한 경우 단일 리소스 관리자 템플릿에서 여러 리소스 그룹을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-130">It's possible to define multiple resource groups in a single Resource Manager template, if needed.</span></span> <span data-ttu-id="7c9e0-131">리소스 그룹 자체를 삭제 하 여 환경의 모든 리소스를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-131">You can delete all resources in an environment by deleting the resource group itself.</span></span> <span data-ttu-id="7c9e0-132">비용 분석은 리소스 그룹 수준에서 실행 될 수도 있으므로 각 환경의 비용을 신속 하 게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-132">Cost analysis can also be run at the resource group level, allowing for quick accounting of how much each environment is costing.</span></span>

<span data-ttu-id="7c9e0-133">GitHub의 [Azure 빠른 시작 템플릿](https://github.com/Azure/azure-quickstart-templates) 프로젝트에서 사용할 수 있는 ARM 템플릿의 많은 예가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-133">There are many examples of ARM templates available in the [Azure Quickstart Templates](https://github.com/Azure/azure-quickstart-templates) project on GitHub.</span></span> <span data-ttu-id="7c9e0-134">새 템플릿을 만들거나 기존 템플릿을 수정 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-134">They can help accelerate creating a new template or modifying an existing one.</span></span>

<span data-ttu-id="7c9e0-135">리소스 관리자 템플릿은 다양 한 방법으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-135">Resource Manager templates can be run in many of ways.</span></span> <span data-ttu-id="7c9e0-136">가장 간단한 방법은 단순히 Azure Portal에 붙여 넣는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-136">Perhaps the simplest way is to simply paste them into the Azure portal.</span></span> <span data-ttu-id="7c9e0-137">실험적 배포의 경우이 방법은 빠르게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-137">For experimental deployments, this method can be quick.</span></span> <span data-ttu-id="7c9e0-138">Azure DevOps에서 빌드 또는 릴리스 프로세스의 일부로 실행 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-138">They can also be run as part of a build or release process in Azure DevOps.</span></span> <span data-ttu-id="7c9e0-139">Azure에 대 한 연결을 활용 하 여 템플릿을 실행 하는 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-139">There are tasks that will leverage connections into Azure to run the templates.</span></span> <span data-ttu-id="7c9e0-140">리소스 관리자 템플릿에 대 한 변경 내용은 증분 방식으로 적용 됩니다. 즉, 새 리소스를 추가 하려면 단순히 템플릿에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-140">Changes to Resource Manager templates are applied incrementally, meaning that to add a new resource requires just adding it to the template.</span></span> <span data-ttu-id="7c9e0-141">도구는 현재 리소스와 템플릿에 정의 된 리소스 간의 차이점을 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-141">The tooling will reconcile differences between the current resources and those defined in the template.</span></span> <span data-ttu-id="7c9e0-142">그러면 리소스는 템플릿에 정의 된 것과 일치 하도록 만들어지거나 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-142">Resources will then be created or altered so they match what is defined in the template.</span></span>  

## <a name="terraform"></a><span data-ttu-id="7c9e0-143">Terraform</span><span class="sxs-lookup"><span data-stu-id="7c9e0-143">Terraform</span></span>

<span data-ttu-id="7c9e0-144">클라우드 네이티브 응용 프로그램은 종종로 생성 됩니다 `cloud agnostic` .</span><span class="sxs-lookup"><span data-stu-id="7c9e0-144">Cloud-native applications are often constructed to be `cloud agnostic`.</span></span> <span data-ttu-id="7c9e0-145">즉, 응용 프로그램이 특정 클라우드 공급 업체와 긴밀 하 게 결합 되지 않으며 공용 클라우드에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-145">Being so means the application isn't tightly coupled to a particular cloud vendor and can be deployed to any public cloud.</span></span>

<span data-ttu-id="7c9e0-146">[Terraform](https://www.terraform.io/) 은 모든 주요 클라우드 플레이어에서 클라우드 네이티브 응용 프로그램을 프로 비전 할 수 있는 상용 템플릿 도구입니다. Azure, GOOGLE CLOUD PLATFORM, AWS 및 alicloud.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-146">[Terraform](https://www.terraform.io/) is commercial templating tool that can provision cloud-native applications across all the major cloud players: Azure, Google Cloud Platform, AWS, and AliCloud.</span></span> <span data-ttu-id="7c9e0-147">JSON을 템플릿 정의 언어로 사용 하는 대신 약간 더 간결한 YAML을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-147">Instead of using JSON as the template definition language, it uses the slightly more terse YAML.</span></span>

<span data-ttu-id="7c9e0-148">이전 리소스 관리자 템플릿과 동일한 작업을 수행 하는 예제 Terraform 파일 (그림 10-15)은 그림 10-16에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-148">An example Terraform file that does the same as the previous Resource Manager template (Figure 10-15) is shown in Figure 10-16:</span></span>

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

<span data-ttu-id="7c9e0-149">**그림 10-16** -리소스 관리자 템플릿의 예</span><span class="sxs-lookup"><span data-stu-id="7c9e0-149">**Figure 10-16** - An example of a Resource Manager template</span></span>

<span data-ttu-id="7c9e0-150">Terraform도 문제 템플릿에 대 한 직관적인 오류 메시지를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-150">Terraform also provides intuitive error messages for problem templates.</span></span> <span data-ttu-id="7c9e0-151">빌드 단계에서 초기에 템플릿 오류를 catch 하는 데 사용할 수 있는 편리한 유효성 검사 작업도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-151">There's also a handy validate task that can be used in the build phase to catch template errors early.</span></span>

<span data-ttu-id="7c9e0-152">리소스 관리자 템플릿과 마찬가지로, 명령줄 도구를 사용 하 여 Terraform 템플릿을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-152">As with Resource Manager templates, command-line tools are available to deploy Terraform templates.</span></span> <span data-ttu-id="7c9e0-153">Terraform 템플릿을 확인 하 고 적용할 수 있는 Azure Pipelines에 커뮤니티에서 만든 작업도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-153">There are also community-created tasks in Azure Pipelines that can validate and apply Terraform templates.</span></span>

<span data-ttu-id="7c9e0-154">경우에 따라 Terraform 및 ARM 템플릿에서는 새로 만든 데이터베이스에 대 한 연결 문자열과 같은 의미 있는 값을 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-154">Sometimes Terraform and ARM templates output meaningful values, such as a connection string to a newly created database.</span></span> <span data-ttu-id="7c9e0-155">이 정보는 빌드 파이프라인에서 캡처되고 후속 작업에 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-155">This information can be captured in the build pipeline and used in subsequent tasks.</span></span>

## <a name="azure-cli-scripts-and-tasks"></a><span data-ttu-id="7c9e0-156">스크립트 및 작업 Azure CLI</span><span class="sxs-lookup"><span data-stu-id="7c9e0-156">Azure CLI Scripts and Tasks</span></span>

<span data-ttu-id="7c9e0-157">마지막으로 [Azure CLI](/cli/azure/) 활용 하 여 클라우드 인프라를 선언적으로 스크립팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-157">Finally, you can leverage [Azure CLI](/cli/azure/) to declaratively script your cloud infrastructure.</span></span> <span data-ttu-id="7c9e0-158">거의 모든 Azure 리소스를 프로 비전 하 고 구성 하기 위해 스크립트를 생성, 검색 및 공유할 수 Azure CLI.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-158">Azure CLI scripts can be created, found, and shared to provision and configure almost any Azure resource.</span></span> <span data-ttu-id="7c9e0-159">CLI는 gentle 학습 곡선으로 간단 하 게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-159">The CLI is simple to use with a gentle learning curve.</span></span> <span data-ttu-id="7c9e0-160">스크립트는 PowerShell 또는 Bash 내에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-160">Scripts are executed within either PowerShell or Bash.</span></span> <span data-ttu-id="7c9e0-161">특히 ARM 템플릿과 비교할 때 간단 하 게 디버깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-161">They're also straightforward to debug, especially when compared with ARM templates.</span></span>

<span data-ttu-id="7c9e0-162">Azure CLI 스크립트는 인프라를 분해 하 고 다시 배포 해야 할 때 제대로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-162">Azure CLI scripts work well when you need to tear down and redeploy your infrastructure.</span></span> <span data-ttu-id="7c9e0-163">기존 환경 업데이트는 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-163">Updating an existing environment can be tricky.</span></span> <span data-ttu-id="7c9e0-164">많은 CLI 명령은 idempotent 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-164">Many CLI commands aren't idempotent.</span></span> <span data-ttu-id="7c9e0-165">즉, 리소스가 이미 있는 경우에도 실행 될 때마다 리소스를 다시 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-165">That means they'll recreate the resource each time they're run, even if the resource already exists.</span></span> <span data-ttu-id="7c9e0-166">항상 각 리소스가 있는지 확인 하는 코드를 추가 하 여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-166">It's always possible to add code that checks for the existence of each resource before creating it.</span></span> <span data-ttu-id="7c9e0-167">그러나 이렇게 하면 스크립트가 너무 커지고 관리 하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-167">But, doing so, your script can become bloated and difficult to manage.</span></span>

<span data-ttu-id="7c9e0-168">이러한 스크립트는 Azure DevOps 파이프라인에로 포함 될 수도 있습니다 `Azure CLI tasks` .</span><span class="sxs-lookup"><span data-stu-id="7c9e0-168">These scripts can also be embedded in Azure DevOps pipelines as `Azure CLI tasks`.</span></span> <span data-ttu-id="7c9e0-169">파이프라인을 실행 하면 스크립트가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-169">Executing the pipeline invokes the script.</span></span>

<span data-ttu-id="7c9e0-170">그림 10-17에서는 Azure CLI 버전 및 구독의 세부 정보를 나열 하는 YAML 코드 조각을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-170">Figure 10-17 shows a YAML snippet that lists the version of Azure CLI and the details of the subscription.</span></span> <span data-ttu-id="7c9e0-171">인라인 스크립트에 Azure CLI 명령을 포함 하는 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-171">Note how Azure CLI commands are included in an inline script.</span></span>

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

<span data-ttu-id="7c9e0-172">**그림 10-17** -Azure CLI 스크립트</span><span class="sxs-lookup"><span data-stu-id="7c9e0-172">**Figure 10-17** - Azure CLI script</span></span>

<span data-ttu-id="7c9e0-173">문서에서 [코드로 서의 인프라 란 무엇](/azure/devops/learn/what-is-infrastructure-as-code)이며, 제작자 Sam Guckenheimer는 "IaC를 구현 하는 팀이 안정적인 환경을 신속 하 고 대규모로 제공할 수 있는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-173">In the article, [What is Infrastructure as Code](/azure/devops/learn/what-is-infrastructure-as-code), Author Sam Guckenheimer describes how, "Teams who implement IaC can deliver stable environments rapidly and at scale.</span></span> <span data-ttu-id="7c9e0-174">팀은 환경을 수동으로 구성 하는 것을 방지 하 고 코드를 통해 환경의 원하는 상태를 표시 하 여 일관성을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9e0-174">Teams avoid manual configuration of environments and enforce consistency by representing the desired state of their environments via code.</span></span> <span data-ttu-id="7c9e0-175">IaC를 사용 하 여 인프라를 배포 하는 것은 반복 가능 하며, 구성 드리프트 또는 누락 종속성으로 인 한 런타임 문제를 방지</span><span class="sxs-lookup"><span data-stu-id="7c9e0-175">Infrastructure deployments with IaC are repeatable and prevent runtime issues caused by configuration drift or missing dependencies.</span></span> <span data-ttu-id="7c9e0-176">DevOps 팀은 통합 된 사례 및 도구 집합과 함께 작업 하 여 응용 프로그램 및 지원 인프라를 신속 하 고 안정적 이며 대규모로 제공할 수 있습니다. "</span><span class="sxs-lookup"><span data-stu-id="7c9e0-176">DevOps teams can work together with a unified set of practices and tools to deliver applications and their supporting infrastructure rapidly, reliably, and at scale."</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7c9e0-177">[이전](feature-flags.md)
>[다음](application-bundles.md)</span><span class="sxs-lookup"><span data-stu-id="7c9e0-177">[Previous](feature-flags.md)
[Next](application-bundles.md)</span></span>
