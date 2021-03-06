---
description: '자세히 알아보기: CacheMetadata를 사용 하 여 데이터 노출'
title: CacheMetadata를 사용하여 데이터 노출
ms.date: 03/30/2017
ms.assetid: 34832f23-e93b-40e6-a80b-606a855a00d9
ms.openlocfilehash: e3f4dc83a0e268ae548c904a714753fa025c77ae
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259787"
---
# <a name="exposing-data-with-cachemetadata"></a><span data-ttu-id="230fc-103">CacheMetadata를 사용하여 데이터 노출</span><span class="sxs-lookup"><span data-stu-id="230fc-103">Exposing data with CacheMetadata</span></span>

<span data-ttu-id="230fc-104">작업을 실행하기 전에 워크플로 런타임은 실행을 유지하는 데 필요한 모든 작업 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="230fc-104">Before executing an activity, the workflow runtime obtains all of the information about the activity that it needs in order to maintain its execution.</span></span> <span data-ttu-id="230fc-105">워크플로 런타임은 <xref:System.Activities.Activity.CacheMetadata%2A> 메서드를 실행하는 동안 이 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="230fc-105">The workflow runtime gets this information during the execution of the <xref:System.Activities.Activity.CacheMetadata%2A> method.</span></span> <span data-ttu-id="230fc-106">이 메서드의 기본 구현에서는 실행 시 작업에서 노출하는 모든 공용 인수, 변수 및 자식 작업을 런타임에 제공합니다. 작업에서 보다 많은 정보를 런타임에 제공해야 하는 경우(예: 전용 멤버 또는 작업에서 예약될 작업) 이 메서드를 재정의하여 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="230fc-106">The default implementation of this method provides the runtime with all of the public arguments, variables, and child activities exposed by the activity at the time it is executed; if the activity needs to give more information to the runtime than this (such as private members, or activities to be scheduled by the activity), this method can be overridden to provide it.</span></span>

## <a name="default-cachemetadata-behavior"></a><span data-ttu-id="230fc-107">기본 CacheMetadata 동작</span><span class="sxs-lookup"><span data-stu-id="230fc-107">Default CacheMetadata behavior</span></span>

<span data-ttu-id="230fc-108"><xref:System.Activities.NativeActivity.CacheMetadata%2A>에서 파생되는 작업에 대한 <xref:System.Activities.NativeActivity>의 기본 구현에서는 다음 메서드 형식을 다음과 같은 방식으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="230fc-108">The default implementation of <xref:System.Activities.NativeActivity.CacheMetadata%2A> for activities that derive from <xref:System.Activities.NativeActivity> processes the following method types in the following ways:</span></span>

- <span data-ttu-id="230fc-109"><xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601> 또는 <xref:System.Activities.InOutArgument%601>(제네릭 인수): 이러한 인수는 이름과 형식이 노출된 속성 이름 및 형식과 같고 적절한 인수 방향 및 일부 유효성 검사 데이터가 포함된 인수로 런타임에 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="230fc-109"><xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601>, or <xref:System.Activities.InOutArgument%601> (generic arguments): These arguments are exposed to the runtime as arguments with a name and type equal to the exposed property name and type, the appropriate argument direction, and some validation data.</span></span>

- <span data-ttu-id="230fc-110"><xref:System.Activities.Variable> 또는 해당 서브클래스: 이러한 멤버는 런타임에 공용 변수로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="230fc-110"><xref:System.Activities.Variable> or any subclass thereof: These members are exposed to the runtime as public variables.</span></span>

- <span data-ttu-id="230fc-111"><xref:System.Activities.Activity> 또는 해당 서브클래스: 이러한 멤버는 런타임에 공용 자식 작업으로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="230fc-111"><xref:System.Activities.Activity> or any subclass thereof: These members are exposed to the runtime as public child activities.</span></span> <span data-ttu-id="230fc-112">기본 동작은를 호출 하 고 자식 활동을 전달 하 여 명시적으로 구현할 수 있습니다 <xref:System.Activities.ActivityMetadata.AddImportedChild%2A> .</span><span class="sxs-lookup"><span data-stu-id="230fc-112">The default behavior can be implemented explicitly by calling <xref:System.Activities.ActivityMetadata.AddImportedChild%2A>, passing in the child activity.</span></span>

- <span data-ttu-id="230fc-113"><xref:System.Activities.ActivityDelegate> 또는 해당 서브클래스: 이러한 멤버는 런타임에 공용 대리자로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="230fc-113"><xref:System.Activities.ActivityDelegate> or any subclass thereof: These members are exposed to the runtime as public delegates.</span></span>

- <span data-ttu-id="230fc-114"><xref:System.Collections.ICollection> 형식의 <xref:System.Activities.Variable>: 컬렉션의 모든 요소가 런타임에 공용 변수로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="230fc-114"><xref:System.Collections.ICollection> of type <xref:System.Activities.Variable>: All elements in the collection are exposed to the runtime as public variables.</span></span>

- <span data-ttu-id="230fc-115"><xref:System.Collections.ICollection> 형식의 <xref:System.Activities.Activity>: 컬렉션의 모든 요소가 런타임에 공용 자식으로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="230fc-115"><xref:System.Collections.ICollection> of type <xref:System.Activities.Activity>: All elements in the collection are exposed to the runtime as public children.</span></span>

- <span data-ttu-id="230fc-116"><xref:System.Collections.ICollection> 형식의 <xref:System.Activities.ActivityDelegate>: 컬렉션의 모든 요소가 런타임에 공용 대리자로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="230fc-116"><xref:System.Collections.ICollection> of type <xref:System.Activities.ActivityDelegate>: All elements in the collection are exposed to the runtime as public delegates.</span></span>

<span data-ttu-id="230fc-117"><xref:System.Activities.Activity.CacheMetadata%2A>, <xref:System.Activities.Activity> 및 <xref:System.Workflow.Activities.CodeActivity>에서 파생되는 작업에 대한 <xref:System.Activities.AsyncCodeActivity>도 다음과 같은 차이점을 제외하고 위와 동일하게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="230fc-117">The <xref:System.Activities.Activity.CacheMetadata%2A> for activities that derive from <xref:System.Activities.Activity>, <xref:System.Workflow.Activities.CodeActivity>, and <xref:System.Activities.AsyncCodeActivity> also function as above, except for the following differences:</span></span>

- <span data-ttu-id="230fc-118"><xref:System.Activities.Activity>에서 파생되는 클래스는 자식 작업이나 대리자를 예약할 수 없으므로 이러한 멤버는 가져온 자식 및 대리자로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="230fc-118">Classes that derive from <xref:System.Activities.Activity> cannot schedule child activities or delegates, so such members are exposed as imported children and delegates; the</span></span>

- <span data-ttu-id="230fc-119"><xref:System.Activities.CodeActivity> 및 <xref:System.Activities.AsyncCodeActivity>에서 파생되는 클래스는 변수, 자식 또는 대리자를 지원하지 않으므로 인수만 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="230fc-119">Classes that derive from <xref:System.Activities.CodeActivity> and <xref:System.Activities.AsyncCodeActivity> do not support variables, children, or delegates, so only arguments will be exposed.</span></span>

## <a name="overriding-cachemetadata-to-provide-information-to-the-runtime"></a><span data-ttu-id="230fc-120">CacheMetadata를 재정의하여 런타임에 정보 제공</span><span class="sxs-lookup"><span data-stu-id="230fc-120">Overriding CacheMetadata to provide information to the runtime</span></span>

<span data-ttu-id="230fc-121">다음 코드 조각에서는 <xref:System.Activities.Activity.CacheMetadata%2A> 메서드를 실행하는 동안 작업의 메타데이터에 멤버 정보를 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="230fc-121">The following code snippet demonstrates how to add information about members to an activity’s metadata during the execution of the <xref:System.Activities.Activity.CacheMetadata%2A> method.</span></span> <span data-ttu-id="230fc-122">작업에 대한 공용 데이터를 모두 캐시하기 위해 메서드의 기준이 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="230fc-122">Note that the base of the method is called to cache all public data about the activity.</span></span>

```csharp
protected override void CacheMetadata(NativeActivityMetadata metadata)
{
    base.CacheMetadata(metadata);
    metadata.AddImplementationChild(this._writeLine);
    metadata.AddVariable(this._myVariable);
    metadata.AddImplementationVariable(this._myImplementationVariable);

    RuntimeArgument argument = new RuntimeArgument("MyArgument", ArgumentDirection.In, typeof(SomeType));
    metadata.Bind(argument, this.SomeName);
    metadata.AddArgument(argument);
}
```

## <a name="using-cachemetadata-to-expose-implementation-children"></a><span data-ttu-id="230fc-123">CacheMetadata를 사용하여 구현 자식 노출</span><span class="sxs-lookup"><span data-stu-id="230fc-123">Using CacheMetadata to expose implementation children</span></span>

<span data-ttu-id="230fc-124">변수를 사용하여 작업에서 예약될 자식 작업에 데이터를 전달하려면 변수를 구현 변수로 추가해야 합니다. 공용 변수의 값은 이런 방식으로 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="230fc-124">In order to pass data to child activities that are to be scheduled by an activity using variables, it is necessary to add the variables as implementation variables; public variables cannot have their values set this way.</span></span> <span data-ttu-id="230fc-125">이것은 작업이 속성을 가진 캡슐화된 클래스가 아니라 매개 변수를 가진 함수의 구현으로 실행되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="230fc-125">The reason for this is that activities are intended to be executed more as implementations of functions (which have parameters), rather than encapsulated classes (which have properties).</span></span> <span data-ttu-id="230fc-126">하지만 예약된 작업은 자식 작업과 동일한 방식으로 부모 작업의 인수에 액세스할 수 없기 때문에 <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>를 사용하는 경우와 같이 인수를 명시적으로 설정해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="230fc-126">However, there are situations in which the arguments must be explicitly set, such as when using <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, since the scheduled activity doesn't have access to the parent activity's arguments in the way a child activity would.</span></span>

<span data-ttu-id="230fc-127">다음 코드 조각에서는를 사용 하 여 네이티브 활동에서 예약 된 활동으로 인수를 전달 하는 방법을 보여 줍니다 <xref:System.Activities.Activity.CacheMetadata%2A> .</span><span class="sxs-lookup"><span data-stu-id="230fc-127">The following code snippet demonstrates how to pass an argument from a native activity into a scheduled activity using <xref:System.Activities.Activity.CacheMetadata%2A>.</span></span>

```csharp
public sealed class ChildActivity : NativeActivity
{
    public WriteLine _writeLine;
    public InArgument<string> Message { get; set; }
    private Variable<string> MessageVariable { get; set; }
    public ChildActivity()
    {
        MessageVariable = new Variable<string>();
        _writeLine = new WriteLine
        {
            Text = new InArgument<string>(MessageVariable),
        };
    }
    protected override void CacheMetadata(NativeActivityMetadata metadata)
    {
        base.CacheMetadata(metadata);
        metadata.AddImplementationVariable(this.MessageVariable);
        metadata.AddImplementationChild(this._writeLine);
    }
    protected override void Execute(NativeActivityContext context)
    {
        string configuredMessage = context.GetValue(Message);
        context.SetValue(MessageVariable, configuredMessage);
        context.ScheduleActivity(this._writeLine);
    }
}
```
