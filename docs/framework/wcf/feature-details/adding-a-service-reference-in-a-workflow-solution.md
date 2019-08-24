---
title: 워크플로 솔루션에 서비스 참조 추가
ms.date: 03/30/2017
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
ms.openlocfilehash: 8f1fa4604f1a1873c7063ec3c9dccf08bd0aa0ee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669669"
---
# <a name="adding-a-service-reference-in-a-workflow-solution"></a><span data-ttu-id="e9051-102">워크플로 솔루션에 서비스 참조 추가</span><span class="sxs-lookup"><span data-stu-id="e9051-102">Adding a Service Reference in a Workflow Solution</span></span>

<span data-ttu-id="e9051-103">워크플로 애플리케이션에서 서비스 참조를 추가하는 작업은 일반적인 WCF 애플리케이션과 약간 다르게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="e9051-103">Adding a service reference in a workflow application works a little differently than a regular WCF application.</span></span> <span data-ttu-id="e9051-104">선택 하면 **추가 > 서비스 참조** 및 서비스에 URL 지정, 메타 데이터를 다운로드 하 고 사용자 지정 활동에 대 한 참조를 추가 하는 WCF 워크플로 서비스를 WCF 서비스를 호출할 수 있도록 하 여 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9051-104">When you select **Add > Service Reference** and specify the URL to the service, the metadata is downloaded and custom activities are generated that allow you to call the WCF service or WCF workflow service you added a reference to.</span></span> <span data-ttu-id="e9051-105">서비스 참조를 추가한 후 생성된 활동이 빌드되도록 솔루션을 다시 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e9051-105">After adding a service reference, rebuild the solution so the generated activities are built.</span></span> <span data-ttu-id="e9051-106">솔루션을 다시 빌드한 후 생성된 활동이 워크플로 디자이너 도구 상자에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e9051-106">They will then appear in the workflow designer toolbox.</span></span> <span data-ttu-id="e9051-107">그러나 워크플로 솔루션 내에서 서비스 참조를 추가하는 경우에만 이러한 과정이 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9051-107">Note however, that this will only work if you are adding a service reference within a workflow solution.</span></span> <span data-ttu-id="e9051-108">다음 웹 캐스트에는 다른 형식의 프로젝트에서 서비스 참조를 추가 하는 방법을 보여 줍니다. [웹 프로젝트의 워크플로에서 WCF 서비스 호출](https://go.microsoft.com/fwlink/?LinkId=207725)합니다.</span><span class="sxs-lookup"><span data-stu-id="e9051-108">The following web cast shows how to add a service reference in other types of projects: [Calling a WCF Service from a Workflow in a Web Project](https://go.microsoft.com/fwlink/?LinkId=207725).</span></span>

<span data-ttu-id="e9051-109">동일한 작업 이름이 포함된 서비스에 대한 서비스 참조를 둘 이상 추가하면 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e9051-109">Adding two or more service references to services that contain the same operation name will cause a problem.</span></span> <span data-ttu-id="e9051-110">생성된 활동이 첫 번째 서비스 작업만 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e9051-110">The generated activities will call only the first service operation.</span></span> <span data-ttu-id="e9051-111">이 문제를 해결하려면 해당 서비스 작업을 구분하도록 서비스 작업의 이름을 변경하거나 생성된 각 활동에서 엔드포인트 구성 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="e9051-111">To work around this issue rename the service operations so they are different or change the endpoint configuration name within each generated activity.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9051-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="e9051-112">See also</span></span>

- [<span data-ttu-id="e9051-113">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="e9051-113">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="e9051-114">웹 프로젝트의 워크플로에서 WCF 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="e9051-114">Calling a WCF Service from a Workflow in a Web Project</span></span>](https://go.microsoft.com/fwlink/?LinkId=207725)
