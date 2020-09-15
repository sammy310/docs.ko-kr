---
ms.openlocfilehash: 35fc4782ebbba33f5fc6668712af9d89d00cafe9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614974"
---
### <a name="wpf-changing-a-primary-key-when-displaying-ado-data-in-a-masterdetail-scenario"></a><span data-ttu-id="c743f-101">마스터/세부 정보 시나리오에서 ADO 데이터를 표시할 때 기본 키를 변경하는 WPF</span><span class="sxs-lookup"><span data-stu-id="c743f-101">WPF Changing a primary key when displaying ADO data in a Master/Detail scenario</span></span>

#### <a name="details"></a><span data-ttu-id="c743f-102">설명</span><span class="sxs-lookup"><span data-stu-id="c743f-102">Details</span></span>

<span data-ttu-id="c743f-103">`Order` 형식 항목의 ADO 컬렉션이 있고 기본 키 &quot;OrderID&quot;를 통해 ADO 컬렉션을 `Detail` 형식 항목의 컬렉션에 연결하는 &quot;OrderDetails&quot;라는 관계가 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="c743f-103">Suppose you have an ADO collection of items of type `Order`, with a relation named &quot;OrderDetails&quot; relating it to a collection of items of type `Detail` via the primary key &quot;OrderID&quot;.</span></span> <span data-ttu-id="c743f-104">WPF 앱에서 목록 컨트롤을 지정된 순서에 대한 세부 정보에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c743f-104">In your WPF app, you can bind a list control to the details for a given order:</span></span>

```xaml
<ListBox ItemsSource="{Binding Path=OrderDetails}" >
```

<span data-ttu-id="c743f-105">DataContext가 `Order`인 경우.</span><span class="sxs-lookup"><span data-stu-id="c743f-105">where the DataContext is an `Order`.</span></span> <span data-ttu-id="c743f-106">WPF는 `OrderID`가 마스터 항목의 `OrderID`와 일치하는 모든 `Detail` 항목의 컬렉션 D인 `OrderDetails` 속성 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c743f-106">WPF gets the value of the `OrderDetails` property - a collection D of all the `Detail` items whose `OrderID` matches the `OrderID` of the master item.</span></span> <span data-ttu-id="c743f-107">마스터 항목의 기본 키 `OrderID`를 변경하면 동작 변경이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c743f-107">The behavior change arises when you change the primary key `OrderID` of the master item.</span></span> <span data-ttu-id="c743f-108">ADO는 세부 정보 컬렉션에 있는 영향을 받는 각 레코드(컬렉션 D로 복사된 레코드)의 `OrderID`를 자동으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c743f-108">ADO automatically changes the `OrderID` of each of the affected records in the Details collection (namely the ones copied into collection D).</span></span>  <span data-ttu-id="c743f-109">하지만 D는 어떻게 처리될까요?</span><span class="sxs-lookup"><span data-stu-id="c743f-109">But what happens to D?</span></span>

- <span data-ttu-id="c743f-110">이전 동작: 컬렉션 D가 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="c743f-110">Old behavior: Collection D is cleared.</span></span> <span data-ttu-id="c743f-111">마스터 항목이 `OrderDetails` 속성에 대한 변경 알림을 표시하지 *않습니다*.</span><span class="sxs-lookup"><span data-stu-id="c743f-111">The master item does *not* raise a change notification for property `OrderDetails`.</span></span> <span data-ttu-id="c743f-112">ListBox가 현재 비어 있는 컬렉션 D를 계속 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c743f-112">The ListBox continues to use collection D, which is now empty.</span></span>
- <span data-ttu-id="c743f-113">새 동작:  컬렉션 D가 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c743f-113">New behavior:  Collection D is unchanged.</span></span> <span data-ttu-id="c743f-114">각 항목이 `OrderID` 속성에 대한 변경 알림을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c743f-114">Each of its items raises a change notification for the `OrderID` property.</span></span> <span data-ttu-id="c743f-115">ListBox가 컬렉션 D를 계속 사용하고 새 `OrderID`와 함께 세부 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c743f-115">The ListBox continues to use collection D, and displays the details with the new `OrderID`.</span></span> <span data-ttu-id="c743f-116">WPF는 `followParent` 인수를 `true`로 설정하고 ADO 메서드 <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType>를 호출하는 다른 방법으로 컬렉션 D를 만들어 새 동작을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c743f-116">WPF implements the new behavior by creating collection D in a different way:  by calling the ADO method <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType> with the `followParent` argument set to `true`.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c743f-117">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="c743f-117">Suggestion</span></span>

<span data-ttu-id="c743f-118">앱은 다음 AppContext 스위치를 사용하여 새 동작을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c743f-118">An app gets the new behavior by using the following AppContext switch.</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Data.DoNotUseFollowParentWhenBindingToADODataRelation=false"/>
  </runtime>
</configuration>
```

<span data-ttu-id="c743f-119">스위치는 기본적으로 .NET 4.7.1 이하를 대상으로 하는 앱의 경우 `true`(이전 동작)로 설정되고, .NET 4.7.2 이상을 대상으로 하는 앱의 경우 `false`(새 동작)로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c743f-119">The switch defaults to `true` (old behavior) for apps that target .NET 4.7.1 or below, and to `false` (new behavior) for apps that target .NET 4.7.2 or above.</span></span>

| <span data-ttu-id="c743f-120">이름</span><span class="sxs-lookup"><span data-stu-id="c743f-120">Name</span></span>    | <span data-ttu-id="c743f-121">값</span><span class="sxs-lookup"><span data-stu-id="c743f-121">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c743f-122">Scope</span><span class="sxs-lookup"><span data-stu-id="c743f-122">Scope</span></span>   | <span data-ttu-id="c743f-123">부</span><span class="sxs-lookup"><span data-stu-id="c743f-123">Minor</span></span>       |
| <span data-ttu-id="c743f-124">버전</span><span class="sxs-lookup"><span data-stu-id="c743f-124">Version</span></span> | <span data-ttu-id="c743f-125">4.7.2</span><span class="sxs-lookup"><span data-stu-id="c743f-125">4.7.2</span></span>       |
| <span data-ttu-id="c743f-126">형식</span><span class="sxs-lookup"><span data-stu-id="c743f-126">Type</span></span>    | <span data-ttu-id="c743f-127">대상 변경</span><span class="sxs-lookup"><span data-stu-id="c743f-127">Retargeting</span></span> |
