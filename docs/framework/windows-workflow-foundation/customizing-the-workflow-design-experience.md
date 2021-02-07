---
description: '자세한 정보: 워크플로 디자인 환경 사용자 지정'
title: 워크플로 디자인 환경 사용자 지정
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 02049f8b42de3de6e4dfdfe8a4151be1500bcca9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742656"
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="544ce-103">워크플로 디자인 환경 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="544ce-103">Customizing the Workflow Design Experience</span></span>

<span data-ttu-id="544ce-104">사용자 지정 활동을 디자인 하 고 Windows 워크플로 디자이너를 재호스팅 하기 위한 시나리오는 .NET Framework 4에서 크게 간소화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="544ce-104">The scenarios for designing custom activities and for rehosting the Windows Workflow Designer have been greatly simplified in .NET Framework 4.</span></span> <span data-ttu-id="544ce-105">따라서 개발과 배포를 더 쉽고 유연하게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="544ce-105">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="544ce-106">인프라의 주요 변경 내용으로, 새 activity designer 프로그래밍 모델은 Windows Presentation Foundation (WPF)를 기반으로 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="544ce-106">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="544ce-107">이렇게 하면 활동 디자이너를 선언적으로 정의 하 고 비교를 사용 하 여 다른 응용 프로그램의 워크플로 디자이너을 쉽게 rehost 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="544ce-107">This gives you the ability to define activity designers declaratively and to rehost the Workflow Designer in other applications with comparative easy.</span></span> <span data-ttu-id="544ce-108">Workflow Designer를 다시 호스트하면 IntelliSense 또는 간소화된 식 도메인을 지원하는 사용자 지정 식 편집기를 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="544ce-108">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="544ce-109">WCF (Windows Communication Foundation)와의 통합은 워크플로 서비스를 사용 하 여 더욱 원활 하 게 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="544ce-109">The integration with Windows Communication Foundation (WCF) has become more seamless with use of workflow services.</span></span> <span data-ttu-id="544ce-110">사용자 지정 활동 디자이너와 모델 항목 트리를 사용하여 다시 호스트된 Workflow Designer의 디자인 타임 환경을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="544ce-110">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="544ce-111">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="544ce-111">In This Section</span></span>

 [<span data-ttu-id="544ce-112">사용자 지정 활동 디자이너 및 템플릿 사용</span><span class="sxs-lookup"><span data-stu-id="544ce-112">Using Custom Activity Designers and Templates</span></span>](using-custom-activity-designers-and-templates.md)

 <span data-ttu-id="544ce-113">새로운 사용자 지정 활동 디자이너와 템플릿을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="544ce-113">Describes how to create new custom activity designers and templates.</span></span>

 [<span data-ttu-id="544ce-114">Workflow Designer 재호스팅</span><span class="sxs-lookup"><span data-stu-id="544ce-114">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)

 <span data-ttu-id="544ce-115">Visual Studio 외부에서 Windows 워크플로 디자이너를 다시 호스팅하는 방법 및 유효성 검사 오류를 표시 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="544ce-115">Describes how to re-host the Windows Workflow Designer outside of Visual Studio and how to display validation errors.</span></span>

 [<span data-ttu-id="544ce-116">사용자 지정 식 편집기 사용</span><span class="sxs-lookup"><span data-stu-id="544ce-116">Using a Custom Expression Editor</span></span>](using-a-custom-expression-editor.md)

 <span data-ttu-id="544ce-117">Visual Studio 2010 외부에서 다시 호스트 되는 워크플로 디자이너에서 사용할 사용자 지정 식 편집기를 구현 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="544ce-117">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of Visual Studio 2010.</span></span>

## <a name="reference"></a><span data-ttu-id="544ce-118">참고</span><span class="sxs-lookup"><span data-stu-id="544ce-118">Reference</span></span>

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a><span data-ttu-id="544ce-119">참조</span><span class="sxs-lookup"><span data-stu-id="544ce-119">See also</span></span>

- [<span data-ttu-id="544ce-120">Windows Workflow Foundation 확장</span><span class="sxs-lookup"><span data-stu-id="544ce-120">Extending Windows Workflow Foundation</span></span>](extend.md)
- [<span data-ttu-id="544ce-121">Designer</span><span class="sxs-lookup"><span data-stu-id="544ce-121">Designer</span></span>](./samples/designer.md)
- [<span data-ttu-id="544ce-122">사용자 지정 활동 디자이너</span><span class="sxs-lookup"><span data-stu-id="544ce-122">Custom Activity Designers</span></span>](./samples/custom-activity-designers.md)
- [<span data-ttu-id="544ce-123">디자이너 재호스팅</span><span class="sxs-lookup"><span data-stu-id="544ce-123">Designer ReHosting</span></span>](./samples/designer-rehosting.md)
