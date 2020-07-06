---
ms.openlocfilehash: d420be76645fc71ac922542fa49f799a473e9a83
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614851"
---
### <a name="accessibility-improvements-in-windows-workflow-foundation-wf-workflow-designer"></a><span data-ttu-id="390da-101">Windows WF(Workflow Foundation) 워크플로 디자이너의 접근성 개선 사항</span><span class="sxs-lookup"><span data-stu-id="390da-101">Accessibility improvements in Windows Workflow Foundation (WF) workflow designer</span></span>

#### <a name="details"></a><span data-ttu-id="390da-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="390da-102">Details</span></span>

<span data-ttu-id="390da-103">Windows WF(Workflow Foundation) 워크플로 디자이너는 접근성 기술 작동 방법을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="390da-103">The Windows Workflow Foundation (WF) workflow designer is improving how it works with accessibility technologies.</span></span> <span data-ttu-id="390da-104">개선 사항에는 다음과 같은 변경 내용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="390da-104">These improvements include the following changes:</span></span>

- <span data-ttu-id="390da-105">일부 컨트롤에서 왼쪽에서 오른쪽으로, 위쪽에서 아래쪽으로 탭 순서를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="390da-105">The tab order is changed to left to right and top to bottom in some controls:</span></span>
- <span data-ttu-id="390da-106"><xref:System.ServiceModel.Activities.InitializeCorrelation> 작업에 대한 상관 관계 데이터를 설정하는 초기화 상관 관계 창</span><span class="sxs-lookup"><span data-stu-id="390da-106">The initialize correlation window for setting correlation data for the <xref:System.ServiceModel.Activities.InitializeCorrelation> activity</span></span>
- <span data-ttu-id="390da-107"><xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 작업에 대한 콘텐츠 정의 창</span><span class="sxs-lookup"><span data-stu-id="390da-107">The content definition window for the <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply> activities</span></span>
- <span data-ttu-id="390da-108">바로 가기를 통해 추가 함수가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="390da-108">More functions are available via the keyboard:</span></span>
- <span data-ttu-id="390da-109">작업의 속성을 편집할 때 처음으로 포커스된 경우 바로 가기에서 속성 그룹을 축소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="390da-109">When editing the properties of an activity, property groups can be collapsed by keyboard the first time they are focused.</span></span>
- <span data-ttu-id="390da-110">이제 경고 아이콘은 바로 가기에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="390da-110">Warning icons are now accessible by keyboard.</span></span>
- <span data-ttu-id="390da-111">바로 가기에서 속성 창의 추가 속성 단추에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="390da-111">The More Properties button in the Properties window is now accessible by keyboard.</span></span>
- <span data-ttu-id="390da-112">이제 바로 가기 사용자는 워크플로 디자이너의 인수 및 변수 창에 있는 헤더 항목에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="390da-112">Keyboard users now can access the header items in the Arguments and Variables panes of the Workflow Designer.</span></span>
- <span data-ttu-id="390da-113">다음과 같은 경우 포커스가 있는 항목의 표시 유형 향상</span><span class="sxs-lookup"><span data-stu-id="390da-113">Improved visibility of items with focus, such as when:</span></span>
- <span data-ttu-id="390da-114">워크플로 디자이너 및 작업 디자이너에서 사용하는 데이터 그리드에 행 추가</span><span class="sxs-lookup"><span data-stu-id="390da-114">Adding rows to data grids used by the Workflow Designer and activity designers.</span></span>
- <span data-ttu-id="390da-115"><xref:System.ServiceModel.Activities.ReceiveReply> 및 <xref:System.ServiceModel.Activities.SendReply> 작업에서 필드 누름</span><span class="sxs-lookup"><span data-stu-id="390da-115">Tabbing through fields in the <xref:System.ServiceModel.Activities.ReceiveReply> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>
- <span data-ttu-id="390da-116">변수 또는 인수에 대한 기본값 설정</span><span class="sxs-lookup"><span data-stu-id="390da-116">Setting default values for variables or arguments</span></span>
- <span data-ttu-id="390da-117">이제 화면 읽기 프로그램이 다음 항목을 올바르게 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="390da-117">Screen readers can now correctly recognize:</span></span>
- <span data-ttu-id="390da-118">워크플로 디자이너에서 설정된 중단점</span><span class="sxs-lookup"><span data-stu-id="390da-118">Breakpoints set in the workflow designer.</span></span>
- <span data-ttu-id="390da-119"><xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> 및 <xref:System.ServiceModel.Activities.CorrelationScope> 작업</span><span class="sxs-lookup"><span data-stu-id="390da-119">The <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision>, and <xref:System.ServiceModel.Activities.CorrelationScope> activities.</span></span>
- <span data-ttu-id="390da-120"><xref:System.ServiceModel.Activities.Receive> 작업의 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="390da-120">The contents of the <xref:System.ServiceModel.Activities.Receive> activity.</span></span>
- <span data-ttu-id="390da-121"><xref:System.Activities.Statements.InvokeMethod> 작업의 대상 유형</span><span class="sxs-lookup"><span data-stu-id="390da-121">The Target Type for the <xref:System.Activities.Statements.InvokeMethod> activity.</span></span>
- <span data-ttu-id="390da-122"><xref:System.Activities.Statements.TryCatch> 작업의 예외 콤보 상자 및 마지막 섹션</span><span class="sxs-lookup"><span data-stu-id="390da-122">The Exception combobox and the Finally section in the <xref:System.Activities.Statements.TryCatch> activity.</span></span>
- <span data-ttu-id="390da-123">메시지 유형 콤보 상자, 상관 관계 이니셜라이저 추가 창의 분할기, 콘텐츠 정의 창 및 메시징 작업의 CorrelatesOn 정의 창(<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> 및 <xref:System.ServiceModel.Activities.ReceiveReply>)</span><span class="sxs-lookup"><span data-stu-id="390da-123">The Message Type combobox, the splitter in the Add Correlation Initializers window, the Content Definition window, and the CorrelatesOn Defintion window in the messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>).</span></span>
- <span data-ttu-id="390da-124">상태 컴퓨터 전환 및 전환 대상</span><span class="sxs-lookup"><span data-stu-id="390da-124">State machine transitions and transitions destinations.</span></span>
- <span data-ttu-id="390da-125"><xref:System.Activities.Statements.FlowDecision> 작업의 주석 및 커넥터</span><span class="sxs-lookup"><span data-stu-id="390da-125">Annotations and connectors on <xref:System.Activities.Statements.FlowDecision> activities.</span></span>
- <span data-ttu-id="390da-126">작업의 팝업(마우스 오른쪽 단추 클릭) 메뉴</span><span class="sxs-lookup"><span data-stu-id="390da-126">The context (right-click) menus for activities.</span></span>
- <span data-ttu-id="390da-127">속성 값 편집기, 검색 정리 단추, 범주별으로 및 사전순 정렬 단추 및 속성 그리드의 식 편집기 대화 상자</span><span class="sxs-lookup"><span data-stu-id="390da-127">The property value editors, the Clear Search button, the By Category and Alphabetical sort buttons, and the Expression Editor dialog in the properties grid.</span></span>
- <span data-ttu-id="390da-128">워크플로 디자이너의 확대/축소 백분율</span><span class="sxs-lookup"><span data-stu-id="390da-128">The zoom percentage in the Workflow Designer.</span></span>
- <span data-ttu-id="390da-129"><xref:System.Activities.Statements.Parallel> 및 <xref:System.Activities.Statements.Pick> 작업의 구분 기호</span><span class="sxs-lookup"><span data-stu-id="390da-129">The separator in <xref:System.Activities.Statements.Parallel> and <xref:System.Activities.Statements.Pick> activities.</span></span>
- <span data-ttu-id="390da-130"><xref:System.Activities.Statements.InvokeDelegate> 작업</span><span class="sxs-lookup"><span data-stu-id="390da-130">The <xref:System.Activities.Statements.InvokeDelegate> activity.</span></span>
- <span data-ttu-id="390da-131">사전 작업의 형식 선택 창(`Microsoft.Activities.AddToDictionary&lt;TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary&lt;TKey,TValue>`등)</span><span class="sxs-lookup"><span data-stu-id="390da-131">The Select Types window for dictionary activities (`Microsoft.Activities.AddToDictionary&lt;TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary&lt;TKey,TValue>`, etc.).</span></span>
- <span data-ttu-id="390da-132">.NET 형식 찾아보기 및 선택 창</span><span class="sxs-lookup"><span data-stu-id="390da-132">The Browse and Select .NET Type window.</span></span>
- <span data-ttu-id="390da-133">워크플로 디자이너의 이동 경로</span><span class="sxs-lookup"><span data-stu-id="390da-133">Breadcrumbs in the Workflow Designer.</span></span>
- <span data-ttu-id="390da-134">고대비 테마를 선택한 사용자는 워크플로 디자이너의 표시 유형에서 여러 개선 사항 및 포커스 요소에 사용되는 요소와 더욱 분명한 선택 영역 상자 사이의 대조율과 같은 해당 컨트롤을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="390da-134">Users who choose High Contrast themes will see many improvements in the visibility of the Workflow Designer and its controls like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="390da-135">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="390da-135">Suggestion</span></span>

<span data-ttu-id="390da-136">다시 호스트된 워크플로 디자이너에서 애플리케이션을 사용하는 경우 애플리케이션은 다음과 같은 작업 중 하나를 수행하여 이러한 변경 내용을 활요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="390da-136">If you have an application with a re-hosted workflow designer, your application can benefit from these changes by performing either of these actions:</span></span>

- <span data-ttu-id="390da-137">.NET Framework 4.7.1을 대상으로 지정하도록 애플리케이션을 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="390da-137">Recompile your application to target the .NET Framework 4.7.1.</span></span> <span data-ttu-id="390da-138">이러한 접근성 변경 내용은 기본적으로 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="390da-138">These accessibility changes are enabled by default.</span></span>
- <span data-ttu-id="390da-139">애플리케이션이 .NET Framework 4.7 이전을 대상으로 하지만 .NET Framework 4.7.1에서 실행되는 경우 다음 예제와 같이 다음 [AppContext 스위치](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)를 app.config 파일의 `<runtime>` 섹션에 추가하고 `false`로 설정하여 이러한 레거시 접근성 동작에서 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="390da-139">If your application targets the .NET Framework 4.7 or earlier but is running on the .NET Framework 4.7.1, you can opt out of these legacy accessibility behaviors by adding the following [AppContext switch](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the `<runtime>` section of the app.config file and set it to `false`, as the following example shows.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
  </runtime>
</configuration>
```

<span data-ttu-id="390da-140">.NET Framework 4.7.1 이상을 대상으로 하고 레거시 액세스 가능성 동작을 유지하려는 애플리케이션은 이 AppContext 스위치를 `true`로 명확하게 설정하여 레거시 액세스 가능성 기능 사용을 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="390da-140">Applications that target the .NET Framework 4.7.1 or later and want to preserve the legacy accessibility behavior can opt in to the use of legacy accessibility features by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="390da-141">이름</span><span class="sxs-lookup"><span data-stu-id="390da-141">Name</span></span>    | <span data-ttu-id="390da-142">값</span><span class="sxs-lookup"><span data-stu-id="390da-142">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="390da-143">Scope</span><span class="sxs-lookup"><span data-stu-id="390da-143">Scope</span></span>   | <span data-ttu-id="390da-144">부</span><span class="sxs-lookup"><span data-stu-id="390da-144">Minor</span></span>       |
| <span data-ttu-id="390da-145">버전</span><span class="sxs-lookup"><span data-stu-id="390da-145">Version</span></span> | <span data-ttu-id="390da-146">4.7.1</span><span class="sxs-lookup"><span data-stu-id="390da-146">4.7.1</span></span>       |
| <span data-ttu-id="390da-147">형식</span><span class="sxs-lookup"><span data-stu-id="390da-147">Type</span></span>    | <span data-ttu-id="390da-148">대상 변경</span><span class="sxs-lookup"><span data-stu-id="390da-148">Retargeting</span></span> |
