---
ms.openlocfilehash: f50022d9a7bacd7be40fe3050ced26e7c25cf7aa
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496263"
---
### <a name="crash-in-selector-when-removing-an-item-from-a-custom-incc-collection"></a><span data-ttu-id="ba4c9-101">사용자 지정 INCC 컬렉션에서 항목을 제거할 때 선택기에서 크래시가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ba4c9-101">Crash in Selector when removing an item from a custom INCC collection</span></span>

#### <a name="details"></a><span data-ttu-id="ba4c9-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="ba4c9-102">Details</span></span>

<span data-ttu-id="ba4c9-103"><code>T:System.InvalidOperationException</code>는 다음과 같은 시나리오에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba4c9-103">An <code>T:System.InvalidOperationException</code> can occur in the following scenario:</span></span><ul><li><span data-ttu-id="ba4c9-104"><code>T:System.Windows.Controls.Primitives.Selector</code>의 ItemsSource는 <code>T:System.Collections.Specialized.INotifyCollectionChanged</code>의 사용자 지정 구현이 있는 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="ba4c9-104">The ItemsSource for a <code>T:System.Windows.Controls.Primitives.Selector</code> is a collection with a custom implementation of <code>T:System.Collections.Specialized.INotifyCollectionChanged</code>.</span></span></li><li><span data-ttu-id="ba4c9-105">선택한 항목이 컬렉션에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba4c9-105">The selected item is removed from the collection.</span></span></li><li><span data-ttu-id="ba4c9-106"><code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code>에는 <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code> = -1(알 수 없는 위치를 나타냄)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba4c9-106">The <code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code> has <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code> = -1 (indicating an unknown position).</span></span></li></ul><span data-ttu-id="ba4c9-107">예외의 호출 스택은 System.Windows.Threading.Dispatcher.VerifyAccess() System.Windows.DependencyObject.GetValue(DependencyProperty dp) System.Windows.Controls.Primitives.Selector.GetIsSelected(DependencyObject 요소)에서 시작합니다. 애플리케이션에 1 초과 디스패처 스레드가 있는 경우 이 예외는 .NET Framework 4.5에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba4c9-107">The exception's callstack begins at System.Windows.Threading.Dispatcher.VerifyAccess() at System.Windows.DependencyObject.GetValue(DependencyProperty dp) at System.Windows.Controls.Primitives.Selector.GetIsSelected(DependencyObject element)This exception can occur in .NET Framework 4.5 if the application has more than one Dispatcher thread.</span></span> <span data-ttu-id="ba4c9-108">.NET Framework 4.7의 경우 단일 디스패처 스레드가 있는 애플리케이션에서도 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba4c9-108">In .NET Framework 4.7 the exception can also occur in applications with a single Dispatcher thread.</span></span> <span data-ttu-id="ba4c9-109">이 문제는 .NET Framework 4.7.1에서 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba4c9-109">The issue is fixed in .NET Framework 4.7.1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ba4c9-110">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="ba4c9-110">Suggestion</span></span>

<span data-ttu-id="ba4c9-111">.NET Framework 4.7.1로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="ba4c9-111">Upgrade to .NET Framework 4.7.1.</span></span>

| <span data-ttu-id="ba4c9-112">Name</span><span class="sxs-lookup"><span data-stu-id="ba4c9-112">Name</span></span>    | <span data-ttu-id="ba4c9-113">값</span><span class="sxs-lookup"><span data-stu-id="ba4c9-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ba4c9-114">Scope</span><span class="sxs-lookup"><span data-stu-id="ba4c9-114">Scope</span></span>   |<span data-ttu-id="ba4c9-115">부</span><span class="sxs-lookup"><span data-stu-id="ba4c9-115">Minor</span></span>|
|<span data-ttu-id="ba4c9-116">버전</span><span class="sxs-lookup"><span data-stu-id="ba4c9-116">Version</span></span>|<span data-ttu-id="ba4c9-117">4.7</span><span class="sxs-lookup"><span data-stu-id="ba4c9-117">4.7</span></span>|
|<span data-ttu-id="ba4c9-118">형식</span><span class="sxs-lookup"><span data-stu-id="ba4c9-118">Type</span></span>|<span data-ttu-id="ba4c9-119">런타임</span><span class="sxs-lookup"><span data-stu-id="ba4c9-119">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="ba4c9-120">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="ba4c9-120">Affected APIs</span></span>

<span data-ttu-id="ba4c9-121">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba4c9-121">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
