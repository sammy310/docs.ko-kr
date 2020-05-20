---
title: 사용자 지정 활동 디자인 및 구현
description: 이 문서에서는 복합 활동을 만들거나 새 활동 유형을 만들어 Workflow Foundation에서 사용자 지정 활동을 만드는 데 필요한 리소스를 제공 합니다.
ms.date: 03/30/2017
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
ms.openlocfilehash: 9c184bff9518bb5581f3bf4cd408db224736192b
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419995"
---
# <a name="designing-and-implementing-custom-activities"></a><span data-ttu-id="153e9-103">사용자 지정 활동 디자인 및 구현</span><span class="sxs-lookup"><span data-stu-id="153e9-103">Designing and Implementing Custom Activities</span></span>
<span data-ttu-id="153e9-104">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]에서는 시스템 제공 활동을 복합 활동으로 어셈블하거나 <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> 또는 <xref:System.Activities.NativeActivity>에서 파생된 새 형식을 만들어 사용자 지정 활동을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="153e9-104">Custom activities in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] are created by either assembling system-provided activities into composite activities or by creating new types that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="153e9-105">이 단원에서는 이 메서드 중 하나를 사용하여 사용자 지정 활동을 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="153e9-105">This section describes how to create custom activities with either method.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="153e9-106">기본적으로 사용자 지정 활동은 워크플로 디자이너에 활동 이름과 함께 간단한 사각형으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="153e9-106">Custom activities by default display within the workflow designer as a simple rectangle with the activity’s name.</span></span> <span data-ttu-id="153e9-107">워크플로 디자이너에서 활동이 표시되는 모양을 사용자 지정하려면 사용자 지정 디자이너도 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="153e9-107">To provide a custom visual representation of your activity in the workflow designer you must also create a custom designer.</span></span> <span data-ttu-id="153e9-108">자세한 내용은 [사용자 지정 활동 디자이너 및 템플릿 사용](using-custom-activity-designers-and-templates.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="153e9-108">For more information, see [Using Custom Activity Designers and Templates](using-custom-activity-designers-and-templates.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="153e9-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="153e9-109">In This Section</span></span>  
 [<span data-ttu-id="153e9-110">작업 제작 옵션</span><span class="sxs-lookup"><span data-stu-id="153e9-110">Activity Authoring Options</span></span>](activity-authoring-options-in-wf.md)  
 <span data-ttu-id="153e9-111">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]에서 사용할 수 있는 제작 스타일에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="153e9-111">Discusses the authoring styles available in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="153e9-112">사용자 지정 활동 사용</span><span class="sxs-lookup"><span data-stu-id="153e9-112">Using a custom activity</span></span>](using-a-custom-activity.md)  
 <span data-ttu-id="153e9-113">워크플로 프로젝트에 사용자 지정 활동을 추가하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="153e9-113">Describes how to add a custom activity to a workflow project.</span></span>  
  
  [<span data-ttu-id="153e9-114">비동기 작업 만들기</span><span class="sxs-lookup"><span data-stu-id="153e9-114">Creating Asynchronous Activities</span></span>](creating-asynchronous-activities-in-wf.md)  
 <span data-ttu-id="153e9-115">비동기 활동을 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="153e9-115">Describes how to create asynchronous activities.</span></span>  
  
 [<span data-ttu-id="153e9-116">활동 유효성 검사 구성</span><span class="sxs-lookup"><span data-stu-id="153e9-116">Configuring Activity Validation</span></span>](configuring-activity-validation.md)  
 <span data-ttu-id="153e9-117">활동을 실행하기 전에 활동 유효성 검사를 사용하여 활동 구성 오류를 식별하고 보고하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="153e9-117">Describes how activity validation can be used to identify and report errors in an activity’s configuration prior to its execution.</span></span>  
  
 [<span data-ttu-id="153e9-118">런타임 시 작업 만들기</span><span class="sxs-lookup"><span data-stu-id="153e9-118">Creating an Activity at Runtime</span></span>](creating-an-activity-at-runtime-with-dynamicactivity.md)  
 <span data-ttu-id="153e9-119">런타임에 <xref:System.Activities.DynamicActivity>를 사용하여 활동을 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="153e9-119">Discusses how to create activities at runtime using <xref:System.Activities.DynamicActivity>.</span></span>  
  
 [<span data-ttu-id="153e9-120">워크플로 실행 속성</span><span class="sxs-lookup"><span data-stu-id="153e9-120">Workflow Execution Properties</span></span>](workflow-execution-properties.md)  
 <span data-ttu-id="153e9-121">워크플로 실행 속성을 사용하여 활동 환경에 컨텍스트별 속성을 추가하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="153e9-121">Describes how to use workflow execution properties to add context specific properties to an activity’s environment</span></span>  
  
 [<span data-ttu-id="153e9-122">활동 대리자 사용</span><span class="sxs-lookup"><span data-stu-id="153e9-122">Using Activity Delegates</span></span>](using-activity-delegates.md)  
 <span data-ttu-id="153e9-123">활동 대리자가 포함된 활동을 작성하고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="153e9-123">Discusses how to author and use activities that contain activity delegates.</span></span>
  
 [<span data-ttu-id="153e9-124">활동 확장 사용</span><span class="sxs-lookup"><span data-stu-id="153e9-124">Using Activity Extensions</span></span>](using-activity-extensions.md)  
 <span data-ttu-id="153e9-125">활동 확장을 작성하고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="153e9-125">Describes how to author and use activity extensions.</span></span>  
  
 [<span data-ttu-id="153e9-126">워크플로에서 OData 피드 사용</span><span class="sxs-lookup"><span data-stu-id="153e9-126">Consuming OData Feeds from a Workflow</span></span>](consuming-odata-feeds-from-a-workflow.md)  
 <span data-ttu-id="153e9-127">워크플로에서 WCF Data Service를 호출하는 여러 가지 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="153e9-127">Describes several methods for calling a WCF Data Service from a workflow.</span></span>  
  
 [<span data-ttu-id="153e9-128">활동 정의 범위 지정 및 표시 유형</span><span class="sxs-lookup"><span data-stu-id="153e9-128">Activity Definition Scoping and Visibility</span></span>](activity-definition-scoping-and-visibility.md)  
 <span data-ttu-id="153e9-129">활동에 대한 데이터 범위와 멤버 표시 유형을 정의하는 옵션 및 규칙에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="153e9-129">Describes the options and rules for defining data scoping and member visibility for activities.</span></span>
