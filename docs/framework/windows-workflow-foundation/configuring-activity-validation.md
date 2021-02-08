---
description: '자세한 정보: 작업 유효성 검사 구성'
title: 활동 유효성 검사 구성
ms.date: 03/30/2017
ms.assetid: 25a4eccb-b8fc-4857-a01d-2683b6341219
ms.openlocfilehash: 9e40842a18dd2afd9a5ec0104d66e8971d691b5f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792754"
---
# <a name="configuring-activity-validation"></a><span data-ttu-id="f5ed7-103">활동 유효성 검사 구성</span><span class="sxs-lookup"><span data-stu-id="f5ed7-103">Configuring Activity Validation</span></span>

<span data-ttu-id="f5ed7-104">활동 유효성 검사를 사용하면 활동 작성자 및 사용자가 활동을 실행하기 이전에 활동 구성 오류를 식별하여 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ed7-104">Activity validation enables activity authors and users to identify and report errors in an activity’s configuration prior to its execution.</span></span> <span data-ttu-id="f5ed7-105">WF (Windows Workflow Foundation)는 다음과 같은 세 가지 유형의 활동 유효성 검사를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ed7-105">Windows Workflow Foundation (WF) provides the following three types of activity validation:</span></span>  
  
- <span data-ttu-id="f5ed7-106">`RequiredArgument` 및 `OverloadGroup` 특성</span><span class="sxs-lookup"><span data-stu-id="f5ed7-106">`RequiredArgument` and `OverloadGroup` attributes.</span></span>  
  
- <span data-ttu-id="f5ed7-107">필수 코드 기반 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f5ed7-107">Imperative code-based validation.</span></span>  
  
- <span data-ttu-id="f5ed7-108">선언적 제약 조건</span><span class="sxs-lookup"><span data-stu-id="f5ed7-108">Declarative constraints.</span></span>  
  
 <span data-ttu-id="f5ed7-109">`RequiredArgument` 및 `OverloadGroup` 특성은 활동의 특정 인수가 필수 항목임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f5ed7-109">`RequiredArgument` and `OverloadGroup` attributes indicate that certain arguments on an activity are required.</span></span> <span data-ttu-id="f5ed7-110">필수 코드 기반 유효성 검사를 사용하면 활동 자체에 대한 유효성을 쉽게 검사할 수 있고, 선언적 제약 조건을 사용하면 활동 및 활동과 포함된 워크플로와의 관계에 대한 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ed7-110">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and declarative constraints enable validation about the activity and its relationship with the containing workflow.</span></span> <span data-ttu-id="f5ed7-111">활동이 유효성 검사 요구 사항에 따라 적절하게 구성되지 않은 경우 유효성 검사 오류 및 경고가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ed7-111">If an activity is not configured properly according to the validation requirements, validation errors and warnings are returned.</span></span> <span data-ttu-id="f5ed7-112">Workflow Designer를 사용하여 포함된 워크플로를 만드는 경우에는 유효성 검사 오류 및 경고가 디자이너에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ed7-112">If the containing workflow is created using the workflow designer, any validation errors and warnings are displayed in the designer.</span></span> <span data-ttu-id="f5ed7-113">워크플로 디자이너 외부에서 워크플로를 만드는 경우에는 워크플로가 호출되면 유효성 검사 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ed7-113">If the workflow is created outside of the workflow designer any validation errors are returned when the workflow is invoked.</span></span> <span data-ttu-id="f5ed7-114">워크플로를 만드는 방법에 상관없이 유효성 검사 오류가 있는 워크플로는 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ed7-114">Regardless of how the workflow was created, a workflow with validation errors is never allowed to execute.</span></span> <span data-ttu-id="f5ed7-115">이 단원에서는 이러한 유형의 활동 유효성 검사의 개요와 활동 유효성 검사를 호출하는 방법을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ed7-115">This section provides an overview of these types of activity validation and how activity validation is invoked.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f5ed7-116">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="f5ed7-116">In This Section</span></span>  

 [<span data-ttu-id="f5ed7-117">필수 인수 및 오버로드 그룹</span><span class="sxs-lookup"><span data-stu-id="f5ed7-117">Required Arguments and Overload Groups</span></span>](required-arguments-and-overload-groups.md)  
 <span data-ttu-id="f5ed7-118">`RequiredArgument` 및 `OverloadGroup` 특성을 사용하여 유효성 검사를 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ed7-118">Describes how to use the `RequiredArgument` and `OverloadGroup` attributes to provide validation.</span></span>  
  
 [<span data-ttu-id="f5ed7-119">명령 코드 기반 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f5ed7-119">Imperative Code-Based Validation</span></span>](imperative-code-based-validation.md)  
 <span data-ttu-id="f5ed7-120"><xref:System.Activities.CodeActivity> 및 <xref:System.Activities.NativeActivity> 기반 활동에 대해 코드 기반 유효성 검사를 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ed7-120">Describes how to use code-based validation for <xref:System.Activities.CodeActivity> and <xref:System.Activities.NativeActivity> based activities.</span></span>  
  
 [<span data-ttu-id="f5ed7-121">선언적 제약 조건</span><span class="sxs-lookup"><span data-stu-id="f5ed7-121">Declarative Constraints</span></span>](declarative-constraints.md)  
 <span data-ttu-id="f5ed7-122">선언적 제약 조건을 사용하여 복잡한 활동 유효성 검사를 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ed7-122">Describes how to use declarative constraints to provide complex activity validation.</span></span>  
  
 [<span data-ttu-id="f5ed7-123">활동 유효성 검사 호출</span><span class="sxs-lookup"><span data-stu-id="f5ed7-123">Invoking Activity Validation</span></span>](invoking-activity-validation.md)  
 <span data-ttu-id="f5ed7-124">활동 유효성 검사가 자동으로 호출되는 시기와 유효성 검사를 명시적으로 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ed7-124">Discusses when activity validation is invoked automatically and how to explicitly invoke validation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f5ed7-125">참고</span><span class="sxs-lookup"><span data-stu-id="f5ed7-125">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f5ed7-126">관련 단원</span><span class="sxs-lookup"><span data-stu-id="f5ed7-126">Related Sections</span></span>
