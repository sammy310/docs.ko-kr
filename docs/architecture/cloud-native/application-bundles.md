---
title: 클라우드 네이티브 애플리케이션 번들
description: Azure 용 클라우드 네이티브 .NET 앱 설계 | 클라우드 네이티브 응용 프로그램 번들
ms.date: 05/12/2020
ms.openlocfilehash: c16a9cba1fe31e025532ba98d644114a319bb9de
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395486"
---
# <a name="cloud-native-application-bundles"></a><span data-ttu-id="2f9ac-103">클라우드 네이티브 애플리케이션 번들</span><span class="sxs-lookup"><span data-stu-id="2f9ac-103">Cloud Native Application Bundles</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="2f9ac-104">클라우드 네이티브 응용 프로그램의 핵심 속성은 클라우드의 기능을 활용 하 여 개발 속도를 높이는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-104">A key property of cloud-native applications is that they leverage the capabilities of the cloud to speed up development.</span></span> <span data-ttu-id="2f9ac-105">이 디자인은 전체 응용 프로그램에서 다양 한 종류의 기술을 사용 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-105">This design often means that a full application uses different kinds of technologies.</span></span> <span data-ttu-id="2f9ac-106">응용 프로그램은 Docker 컨테이너에 제공 될 수 있으며, 일부 서비스는 Azure Functions 사용할 수 있는 반면, 다른 부분은 하드웨어 GPU 가속을 사용 하 여 대량 금속 서버에 할당 된 가상 컴퓨터에서 직접 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-106">Applications may be shipped in Docker containers, some services may use Azure Functions, while other parts may run directly on virtual machines allocated on large metal servers with hardware GPU acceleration.</span></span> <span data-ttu-id="2f9ac-107">두 클라우드 네이티브 응용 프로그램이 동일 하지 않으므로 제공 하는 단일 메커니즘을 제공 하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-107">No two cloud-native applications are the same, so it's been difficult to provide a single mechanism for shipping them.</span></span>

<span data-ttu-id="2f9ac-108">Docker 컨테이너는 배포에 대 한 투구 차트를 사용 하 여 Kubernetes에서 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-108">The Docker containers may run on Kubernetes using a Helm Chart for deployment.</span></span> <span data-ttu-id="2f9ac-109">Terraform 템플릿을 사용 하 여 Azure Functions을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-109">The Azure Functions may be allocated using Terraform templates.</span></span> <span data-ttu-id="2f9ac-110">마지막으로, 가상 머신은 Terraform을 사용 하 여 할당 될 수 있지만 Ansible를 사용 하 여 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-110">Finally, the virtual machines may be allocated using Terraform but built out using Ansible.</span></span> <span data-ttu-id="2f9ac-111">이는 기술이 많은 기술 이며, 모든 것을 적절 한 패키지로 함께 패키지할 방법이 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-111">This is a whole mess of technologies and there has been no way to package them all together into a reasonable package.</span></span> <span data-ttu-id="2f9ac-112">지금까지.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-112">Until now.</span></span>

<span data-ttu-id="2f9ac-113">CNABs (Cloud Native Application 번들)는 분산 응용 프로그램을 패키지 하는 사양을 개발 하기 위해 Microsoft, Docker 및 HashiCorp와 같은 다양 한 커뮤니티 관심이 있는 회사의 공동 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-113">Cloud Native Application Bundles (CNABs) are a joint effort by a number of community-minded companies such as Microsoft, Docker, and HashiCorp to develop a specification to package distributed applications.</span></span>

<span data-ttu-id="2f9ac-114">이 활동은 2018 년 12 월에 발표 되었으므로 더 큰 커뮤니티에 활동을 노출 하기 위해 수행 해야 하는 작업은 여전히 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-114">The effort was announced in December of 2018, so there's still a fair bit of work to do to expose the effort to the greater community.</span></span> <span data-ttu-id="2f9ac-115">그러나 이미 [개방 된 사양과](https://github.com/deislabs/cnab-spec) [duffle](https://duffle.sh/)이라는 참조 구현이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-115">However, there's already an [open specification](https://github.com/deislabs/cnab-spec) and a reference implementation known as [Duffle](https://duffle.sh/).</span></span> <span data-ttu-id="2f9ac-116">Go로 작성 된이 도구는 Docker와 Microsoft 간의 공동 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-116">This tool, which was written in Go, is a joint effort between Docker and Microsoft.</span></span>

<span data-ttu-id="2f9ac-117">CNABs에는 여러 종류의 설치 기술이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-117">The CNABs can contain different kinds of installation technologies.</span></span> <span data-ttu-id="2f9ac-118">이를 통해 투구 차트, Terraform 템플릿, Ansible 플레이 북 등을 동일한 패키지에 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-118">This allows things like Helm Charts, Terraform templates, and Ansible Playbooks to coexist in the same package.</span></span> <span data-ttu-id="2f9ac-119">작성 된 패키지는 자체 포함 되 고 이식 가능 합니다. USB 스틱에서 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-119">Once built, the packages are self-contained and portable; they can be installed from a USB stick.</span></span>  <span data-ttu-id="2f9ac-120">패키지는 자신이 주장 하는 당사자 로부터 온 것임을 확인 하기 위해 암호화 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-120">The packages are cryptographically signed to ensure they originate from the party they claim.</span></span>

<span data-ttu-id="2f9ac-121">CNAB의 핵심은 라는 파일입니다 `bundle.json` .</span><span class="sxs-lookup"><span data-stu-id="2f9ac-121">The core of a CNAB is a file called `bundle.json`.</span></span> <span data-ttu-id="2f9ac-122">이 파일은 번들의 콘텐츠를 정의 합니다. 즉, Terraform 또는 이미지나 기타 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-122">This file defines the contents of the bundle, be they Terraform or images or anything else.</span></span> <span data-ttu-id="2f9ac-123">그림 11-9에서는 Terraform을 호출 하는 CNAB를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-123">Figure 11-9 defines a CNAB that invokes some Terraform.</span></span> <span data-ttu-id="2f9ac-124">하지만 실제로는 Terraform을 호출 하는 데 사용 되는 호출 이미지를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-124">Notice, however, that it actually defines an invocation image that is used to invoke the Terraform.</span></span> <span data-ttu-id="2f9ac-125">패키지를 만들면 *cnab* 디렉터리에 있는 Docker 파일이 docker 이미지에 기본 제공 됩니다 .이 이미지는 번들에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-125">When packaged up, the Docker file that is located in the *cnab* directory is built into a Docker image, which will be included in the bundle.</span></span> <span data-ttu-id="2f9ac-126">번들의 Docker 컨테이너 내부에 Terraform을 설치 하는 것은 사용자가 번들을 실행 하기 위해 컴퓨터에 Terraform을 설치 하지 않아도 된다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-126">Having Terraform installed inside a Docker container in the bundle means that users don't need to have Terraform installed on their machine to run the bundling.</span></span>

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

<span data-ttu-id="2f9ac-127">**그림 10-18** -예제 Terraform 파일</span><span class="sxs-lookup"><span data-stu-id="2f9ac-127">**Figure 10-18** - An example Terraform file</span></span>

<span data-ttu-id="2f9ac-128">`bundle.json`또한는 Terraform으로 전달 되는 매개 변수 집합을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-128">The `bundle.json` also defines a set of parameters that are passed down into the Terraform.</span></span> <span data-ttu-id="2f9ac-129">번들의 매개 변수화를 사용 하면 다양 한 환경에서 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-129">Parameterization of the bundle allows for installation in a variety of different environments.</span></span>

<span data-ttu-id="2f9ac-130">CNAB 형식만 유연 하 여 모든 클라우드에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-130">The CNAB format is also flexible, allowing it to be used against any cloud.</span></span> <span data-ttu-id="2f9ac-131">[Openstack](https://www.openstack.org/)과 같은 온-프레미스 솔루션에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-131">It can even be used against on-premises solutions such as [OpenStack](https://www.openstack.org/).</span></span>

## <a name="devops-decisions"></a><span data-ttu-id="2f9ac-132">DevOps 결정</span><span class="sxs-lookup"><span data-stu-id="2f9ac-132">DevOps Decisions</span></span>

<span data-ttu-id="2f9ac-133">이러한 도구는 DevOps 공간에 몇 가지 훌륭한 도구를 포함 하 고 있으며 성공 하는 방법에 대 한 방대한 서적 및 백서도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-133">There are so many great tools in the DevOps space these days and even more fantastic books and papers on how to succeed.</span></span> <span data-ttu-id="2f9ac-134">DevOps 여행에서 시작 하기 위한 즐겨 찾는 책은 가상 회사가 NoOps에서 DevOps로 변환 하는 것을 따르는 [Phoenix 프로젝트](https://www.oreilly.com/library/view/the-phoenix-project/9781457191350/)입니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-134">A favorite book to get started on the DevOps journey is [The Phoenix Project](https://www.oreilly.com/library/view/the-phoenix-project/9781457191350/), which follows the transformation of a fictional company from NoOps to DevOps.</span></span> <span data-ttu-id="2f9ac-135">특정 한 가지 사항은 다음과 같습니다. DevOps는 복잡 한 클라우드 네이티브 응용 프로그램을 배포할 때 더 이상 "바람직한" 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-135">One thing is for certain: DevOps is no longer a "nice to have" when deploying complex, Cloud Native Applications.</span></span> <span data-ttu-id="2f9ac-136">이는 요구 사항이 며 프로젝트를 시작할 때 계획 하 고이에 대해 자원을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9ac-136">It's a requirement and should be planned for and resourced at the start of any project.</span></span>

## <a name="references"></a><span data-ttu-id="2f9ac-137">참조</span><span class="sxs-lookup"><span data-stu-id="2f9ac-137">References</span></span>

- [<span data-ttu-id="2f9ac-138">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="2f9ac-138">Azure DevOps</span></span>](https://azure.microsoft.com/services/devops/)
- [<span data-ttu-id="2f9ac-139">Azure Resource Manager</span><span class="sxs-lookup"><span data-stu-id="2f9ac-139">Azure Resource Manager</span></span>](https://azure.microsoft.com/documentation/articles/resource-group-overview/)
- [<span data-ttu-id="2f9ac-140">Terraform</span><span class="sxs-lookup"><span data-stu-id="2f9ac-140">Terraform</span></span>](https://www.terraform.io/)
- [<span data-ttu-id="2f9ac-141">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="2f9ac-141">Azure CLI</span></span>](https://docs.microsoft.com/cli/azure/)

>[!div class="step-by-step"]
><span data-ttu-id="2f9ac-142">[이전](infrastructure-as-code.md)
>[다음](summary.md)</span><span class="sxs-lookup"><span data-stu-id="2f9ac-142">[Previous](infrastructure-as-code.md)
[Next](summary.md)</span></span>
