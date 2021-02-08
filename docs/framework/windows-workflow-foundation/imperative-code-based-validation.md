---
description: '자세한 정보: 명령적 Code-Based 유효성 검사'
title: 명령 코드 기반 유효성 검사
ms.date: 03/30/2017
ms.assetid: ae12537c-455e-42b1-82f4-cea4c46c023e
ms.openlocfilehash: 36759572393be613a569c4846e3610fcbbde2a51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792702"
---
# <a name="imperative-code-based-validation"></a><span data-ttu-id="97ca9-103">명령 코드 기반 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="97ca9-103">Imperative Code-Based Validation</span></span>

<span data-ttu-id="97ca9-104">명령형 코드 기반 유효성 검사를 이용하면 활동 자체에서 활동 유효성 검사를 간단히 실행할 수 있으며 <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> 및 <xref:System.Activities.NativeActivity>의 파생 활동에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ca9-104">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and is available for activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="97ca9-105">유효성 검사 오류 또는 경고를 판단하는 유효성 검사 코드가 활동에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="97ca9-105">Validation code that determines any validation errors or warnings is added to the activity.</span></span>  
  
## <a name="using-code-based-validation"></a><span data-ttu-id="97ca9-106">코드 기반 유효성 검사 사용</span><span class="sxs-lookup"><span data-stu-id="97ca9-106">Using Code-Based Validation</span></span>

<span data-ttu-id="97ca9-107">코드 기반 유효성 검사는 <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> 및 <xref:System.Activities.NativeActivity>의 파생 활동에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="97ca9-107">Code-based validation is supported by activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="97ca9-108"><xref:System.Activities.CodeActivity.CacheMetadata%2A> 재정의에 유효성 검사 코드를 배치할 수 있으며, 메타데이터 인수에 유효성 검사 오류 또는 경고를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ca9-108">Validation code can be placed in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override, and validation errors or warnings can be added to the metadata argument.</span></span> <span data-ttu-id="97ca9-109">다음 예에서 `Cost`가 `Price`보다 크면 메타데이터에 유효성 검사 오류가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="97ca9-109">In the following example, if the `Cost` is greater than the `Price`, a validation error is added to the metadata.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="97ca9-110">`Cost` 및 `Price`는 활동에 대한 인수는 아니지만 디자인 타임에 설정되는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="97ca9-110">Note that `Cost` and `Price` are not arguments to the activity, but are properties that are set at design time.</span></span> <span data-ttu-id="97ca9-111">따라서 이러한 값은 <xref:System.Activities.CodeActivity.CacheMetadata%2A> 재정의에서 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ca9-111">That is why their values can be validated in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override.</span></span> <span data-ttu-id="97ca9-112">인수를 통해 흐르는 데이터 값은 런타임이 될 때가지 흐르지 않으므로 디자인 타임에서 유효성을 검사할 수 없습니다. 활동 인수는 `RequiredArgument` 특성 및 오버로드 그룹을 사용하여 바인딩되도록 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ca9-112">The value of the data flowing through an argument cannot be validated at design time because the data does not flow until run time, but activity arguments can be validated to ensure that they are bound by using the `RequiredArgument` attribute and overload groups.</span></span> <span data-ttu-id="97ca9-113">이 예제 코드에서는 `RequiredArgument` 인수에 대한 `Description` 특성을 확인하여 바인딩되어 있지 않을 경우 유효성 검사 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="97ca9-113">This example code sees the `RequiredArgument` attribute for the `Description` argument, and if it is not bound then a validation error is generated.</span></span> <span data-ttu-id="97ca9-114">필수 인수는 [필수 인수 및 오버 로드 그룹](required-arguments-and-overload-groups.md)에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ca9-114">Required arguments are covered in [Required Arguments and Overload Groups](required-arguments-and-overload-groups.md).</span></span>  
  
```csharp  
public sealed class CreateProduct : CodeActivity  
{  
    public double Price { get; set; }  
    public double Cost { get; set; }  
  
    // [RequiredArgument] attribute will generate a validation error
    // if the Description argument is not set.  
    [RequiredArgument]  
    public InArgument<string> Description { get; set; }  
  
    protected override void CacheMetadata(CodeActivityMetadata metadata)  
    {  
        base.CacheMetadata(metadata);  
        // Determine when the activity has been configured in an invalid way.  
        if (this.Cost > this.Price)  
        {  
            // Add a validation error with a custom message.  
            metadata.AddValidationError("The Cost must be less than or equal to the Price.");  
        }  
    }  
  
    protected override void Execute(CodeActivityContext context)  
    {  
        // Not needed for the sample.  
    }  
}  
```  
  
 <span data-ttu-id="97ca9-115">기본적으로 <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A>가 호출되면 메타데이터에 유효성 검사 오류가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="97ca9-115">By default, a validation error is added to the metadata when <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> is called.</span></span> <span data-ttu-id="97ca9-116">유효성 검사 경고를 추가하려면 <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A>를 취하는 <xref:System.Activities.Validation.ValidationError> 오버로드를 사용하고 <xref:System.Activities.Validation.ValidationError> 속성을 설정하여 <xref:System.Activities.Validation.ValidationError.IsWarning%2A>가 경고를 나타내도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="97ca9-116">To add a validation warning, use the <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> overload that takes a <xref:System.Activities.Validation.ValidationError>, and specify that the <xref:System.Activities.Validation.ValidationError> represents a warning by setting the <xref:System.Activities.Validation.ValidationError.IsWarning%2A> property.</span></span>  
  
 <span data-ttu-id="97ca9-117">Workflow Designer에서 워크플로를 수정하면 유효성 검사가 수행되어 Workflow Designer에 유효성 검사 오류 또는 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="97ca9-117">Validation occurs when a workflow is modified in the workflow designer and any validation errors or warnings are displayed in the workflow designer.</span></span> <span data-ttu-id="97ca9-118">워크플로를 호출하면 런타임에도 유효성 검사가 수행되며 유효성 검사 오류가 발생할 경우 기본 유효성 검사 논리에 따라 <xref:System.Activities.InvalidWorkflowException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="97ca9-118">Validation also occurs at run time when a workflow is invoked and if any validation errors occur, an <xref:System.Activities.InvalidWorkflowException> is thrown by the default validation logic.</span></span> <span data-ttu-id="97ca9-119">유효성 검사를 호출 하 고 유효성 검사 경고 또는 오류에 액세스 하는 방법에 대 한 자세한 내용은 [활동 유효성 검사 호출](invoking-activity-validation.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="97ca9-119">For more information about invoking validation and accessing any validation warnings or errors, see [Invoking Activity Validation](invoking-activity-validation.md).</span></span>  
  
 <span data-ttu-id="97ca9-120"><xref:System.Activities.CodeActivity.CacheMetadata%2A>에서 throw되는 모든 예외는 유효성 검사 오류로 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97ca9-120">Any exceptions that are thrown from <xref:System.Activities.CodeActivity.CacheMetadata%2A> are not treated as validation errors.</span></span> <span data-ttu-id="97ca9-121">이러한 예외는 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>에 대한 호출에서 이스케이프되며 호출자가 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ca9-121">These exceptions will escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span>  
  
 <span data-ttu-id="97ca9-122">코드 기반 유효성 검사는 해당 코드가 포함된 활동의 유효성을 검사하는 데 유용하지만 워크플로의 다른 활동은 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97ca9-122">Code-based validation is useful for validating the activity that contains the code, but it does not have visibility into the other activities in the workflow.</span></span> <span data-ttu-id="97ca9-123">선언적 제약 조건 유효성 검사는 워크플로의 활동과 다른 활동 간 관계의 유효성을 검사할 수 있는 기능을 제공 하며 [선언적 제약 조건](declarative-constraints.md) 항목에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ca9-123">Declarative constraints validation provides the ability to validate the relationships between an activity and other activities in the workflow, and is covered in the [Declarative Constraints](declarative-constraints.md) topic.</span></span>
