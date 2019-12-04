---
title: 워크플로 디자인 환경 사용자 지정
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 27be398d874747b65ae051224070d3f40f1fbbb0
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715133"
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="2b4ac-102">워크플로 디자인 환경 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="2b4ac-102">Customizing the Workflow Design Experience</span></span>

<span data-ttu-id="2b4ac-103">사용자 지정 활동을 디자인 하 고 Windows 워크플로 디자이너를 재호스팅 하기 위한 시나리오는 .NET Framework 4에서 크게 간소화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2b4ac-103">The scenarios for designing custom activities and for rehosting the Windows Workflow Designer have been greatly simplified in .NET Framework 4.</span></span> <span data-ttu-id="2b4ac-104">따라서 개발과 배포를 더 쉽고 유연하게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b4ac-104">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="2b4ac-105">인프라의 주요 변경 내용으로, 새 activity designer 프로그래밍 모델은 Windows Presentation Foundation (WPF)를 기반으로 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b4ac-105">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="2b4ac-106">이렇게 하면 활동 디자이너를 선언적으로 정의 하 고 비교를 사용 하 여 다른 응용 프로그램의 워크플로 디자이너을 쉽게 rehost 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b4ac-106">This gives you the ability to define activity designers declaratively and to rehost the Workflow Designer in other applications with comparative easy.</span></span> <span data-ttu-id="2b4ac-107">Workflow Designer를 다시 호스트하면 IntelliSense 또는 간소화된 식 도메인을 지원하는 사용자 지정 식 편집기를 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b4ac-107">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="2b4ac-108">WCF (Windows Communication Foundation)와의 통합은 워크플로 서비스를 사용 하 여 더욱 원활 하 게 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b4ac-108">The integration with Windows Communication Foundation (WCF) has become more seamless with use of workflow services.</span></span> <span data-ttu-id="2b4ac-109">사용자 지정 활동 디자이너와 모델 항목 트리를 사용하여 다시 호스트된 Workflow Designer의 디자인 타임 환경을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b4ac-109">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2b4ac-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="2b4ac-110">In This Section</span></span>

 [<span data-ttu-id="2b4ac-111">사용자 지정 활동 디자이너 및 템플릿 사용</span><span class="sxs-lookup"><span data-stu-id="2b4ac-111">Using Custom Activity Designers and Templates</span></span>](using-custom-activity-designers-and-templates.md)

 <span data-ttu-id="2b4ac-112">새로운 사용자 지정 활동 디자이너와 템플릿을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2b4ac-112">Describes how to create new custom activity designers and templates.</span></span>

 [<span data-ttu-id="2b4ac-113">워크플로 디자이너 재호스트</span><span class="sxs-lookup"><span data-stu-id="2b4ac-113">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)

 <span data-ttu-id="2b4ac-114">Visual Studio 외부에서 Windows 워크플로 디자이너를 다시 호스팅하는 방법 및 유효성 검사 오류를 표시 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b4ac-114">Describes how to re-host the Windows Workflow Designer outside of Visual Studio and how to display validation errors.</span></span>

 [<span data-ttu-id="2b4ac-115">사용자 지정 식 편집기 사용</span><span class="sxs-lookup"><span data-stu-id="2b4ac-115">Using a Custom Expression Editor</span></span>](using-a-custom-expression-editor.md)

 <span data-ttu-id="2b4ac-116">Visual Studio 2010 외부에서 다시 호스트 되는 워크플로 디자이너에서 사용할 사용자 지정 식 편집기를 구현 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b4ac-116">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of Visual Studio 2010.</span></span>

## <a name="reference"></a><span data-ttu-id="2b4ac-117">참조</span><span class="sxs-lookup"><span data-stu-id="2b4ac-117">Reference</span></span>

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a><span data-ttu-id="2b4ac-118">참조</span><span class="sxs-lookup"><span data-stu-id="2b4ac-118">See also</span></span>

- [<span data-ttu-id="2b4ac-119">Windows Workflow Foundation 확장</span><span class="sxs-lookup"><span data-stu-id="2b4ac-119">Extending Windows Workflow Foundation</span></span>](extend.md)
- [<span data-ttu-id="2b4ac-120">디자이너</span><span class="sxs-lookup"><span data-stu-id="2b4ac-120">Designer</span></span>](./samples/designer.md)
- [<span data-ttu-id="2b4ac-121">사용자 지정 작업 디자이너</span><span class="sxs-lookup"><span data-stu-id="2b4ac-121">Custom Activity Designers</span></span>](./samples/custom-activity-designers.md)
- [<span data-ttu-id="2b4ac-122">디자이너 재호스팅</span><span class="sxs-lookup"><span data-stu-id="2b4ac-122">Designer ReHosting</span></span>](./samples/designer-rehosting.md)
