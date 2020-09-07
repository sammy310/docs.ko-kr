---
ms.openlocfilehash: 196b6a13d32c7767b858d6d68ca775eb49324805
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497244"
---
### <a name="listboxitem-isselected-binding-issue-with-observablecollectionlttgtmove"></a><span data-ttu-id="efc02-101">ObservableCollection&lt;T&gt;.Move의 ListBoxItem IsSelected 바인딩 문제</span><span class="sxs-lookup"><span data-stu-id="efc02-101">ListBoxItem IsSelected binding issue with ObservableCollection&lt;T&gt;.Move</span></span>

#### <a name="details"></a><span data-ttu-id="efc02-102">설명</span><span class="sxs-lookup"><span data-stu-id="efc02-102">Details</span></span>

<span data-ttu-id="efc02-103">선택한 항목을 사용하여 <xref:System.Windows.Controls.ListBox?displayProperty=fullName>에 바인딩된 컬렉션에서 <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> 또는 <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)>을 호출하면 이후에 <xref:System.Windows.Controls.ListBox?displayProperty=fullName> 항목을 선택하거나 선택 취소할 때 비정상적인 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efc02-103">Calling <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> or <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> on a collection bound to a <xref:System.Windows.Controls.ListBox?displayProperty=fullName> with items selected can lead to erratic behavior with future selection or unselection of <xref:System.Windows.Controls.ListBox?displayProperty=fullName> items.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="efc02-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="efc02-104">Suggestion</span></span>

<span data-ttu-id="efc02-105"><xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> 대신 <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> 및 <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName>을 호출하면 이 문제가 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="efc02-105">Calling <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> and <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> instead of <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> will work around this issue.</span></span> <span data-ttu-id="efc02-106">또는 .NET Framework 4.6에서 이 문제가 수정되어 해당 버전의 .NET Framework로 업그레이드하여 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efc02-106">Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="efc02-107">이름</span><span class="sxs-lookup"><span data-stu-id="efc02-107">Name</span></span>    | <span data-ttu-id="efc02-108">값</span><span class="sxs-lookup"><span data-stu-id="efc02-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="efc02-109">Scope</span><span class="sxs-lookup"><span data-stu-id="efc02-109">Scope</span></span>   |<span data-ttu-id="efc02-110">부</span><span class="sxs-lookup"><span data-stu-id="efc02-110">Minor</span></span>|
|<span data-ttu-id="efc02-111">버전</span><span class="sxs-lookup"><span data-stu-id="efc02-111">Version</span></span>|<span data-ttu-id="efc02-112">4.5</span><span class="sxs-lookup"><span data-stu-id="efc02-112">4.5</span></span>|
|<span data-ttu-id="efc02-113">형식</span><span class="sxs-lookup"><span data-stu-id="efc02-113">Type</span></span>|<span data-ttu-id="efc02-114">런타임</span><span class="sxs-lookup"><span data-stu-id="efc02-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="efc02-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="efc02-115">Affected APIs</span></span>

- <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.ObjectModel.ObservableCollection`1.Move(System.Int32,System.Int32)``
- ``M:System.Collections.ObjectModel.ObservableCollection`1.MoveItem(System.Int32,System.Int32)``

-->
