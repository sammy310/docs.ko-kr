---
title: '호환성이 손상되는 변경: 일부 API가 ArgumentNullException을 throw함'
description: 일부 API가 인수의 유효성을 검사하고 이제 ArgumentNullException을 throw하는 .NET 6의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 01/29/2021
ms.openlocfilehash: ca7f32739237715657350f52d2523b0ce378364d
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255739"
---
# <a name="some-apis-throw-argumentnullexception"></a><span data-ttu-id="972e0-103">일부 API가 ArgumentNullException을 throw함</span><span class="sxs-lookup"><span data-stu-id="972e0-103">Some APIs throw ArgumentNullException</span></span>

<span data-ttu-id="972e0-104">이제 일부 API는 입력 매개 변수의 유효성을 검사하여 `null` 입력 인수를 사용하여 호출된 경우 <xref:System.ArgumentNullException>을 throw합니다(이전에는 <xref:System.NullReferenceException>을 throw함).</span><span class="sxs-lookup"><span data-stu-id="972e0-104">Some APIs now validate input parameters and throw an <xref:System.ArgumentNullException> where previously they threw a <xref:System.NullReferenceException>, if invoked with `null` input arguments.</span></span>

## <a name="change-description"></a><span data-ttu-id="972e0-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="972e0-105">Change description</span></span>

<span data-ttu-id="972e0-106">이전 .NET 버전에서 영향을 받는 API는 `null`인 인수를 사용하여 호출된 경우 <xref:System.NullReferenceException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="972e0-106">In previous .NET versions, the affected APIs throw a <xref:System.NullReferenceException> if invoked with an argument that's `null`.</span></span>

<span data-ttu-id="972e0-107">.NET 6부터 영향을 받는 API는 `null`인 인수를 사용하여 호출된 경우 <xref:System.ArgumentNullException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="972e0-107">Starting in .NET 6, the affected APIs throw an <xref:System.ArgumentNullException> if invoked with an argument that's `null`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="972e0-108">변경 이유</span><span class="sxs-lookup"><span data-stu-id="972e0-108">Reason for change</span></span>

<span data-ttu-id="972e0-109"><xref:System.ArgumentNullException>을 throw하면 .NET 런타임 동작을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="972e0-109">Throwing <xref:System.ArgumentNullException> conforms to .NET Runtime behavior.</span></span> <span data-ttu-id="972e0-110">예외를 발생시킨 인수를 명확하게 전달하여 더 나은 디버그 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="972e0-110">It provides a better debug experience by clearly communicating which argument caused the exception.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="972e0-111">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="972e0-111">Version introduced</span></span>

<span data-ttu-id="972e0-112">.NET 6.0</span><span class="sxs-lookup"><span data-stu-id="972e0-112">.NET 6.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="972e0-113">권장 조치</span><span class="sxs-lookup"><span data-stu-id="972e0-113">Recommended action</span></span>

- <span data-ttu-id="972e0-114">코드를 검토하여 필요한 경우 영향을 받는 API에 `null` 입력 인수를 전달하지 않도록 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="972e0-114">Review and, if necessary, update your code to prevent passing `null` input arguments to the affected APIs.</span></span>
- <span data-ttu-id="972e0-115">코드가 <xref:System.NullReferenceException>을 처리하는 경우 <xref:System.ArgumentNullException>에 대한 처리기로 바꾸거나 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="972e0-115">If your code handles <xref:System.NullReferenceException>, replace or add an additional handler for <xref:System.ArgumentNullException>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="972e0-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="972e0-116">Affected APIs</span></span>

<span data-ttu-id="972e0-117">다음 표에서는 영향을 받는 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="972e0-117">The following table lists the affected properties:</span></span>

| <span data-ttu-id="972e0-118">속성</span><span class="sxs-lookup"><span data-stu-id="972e0-118">Property</span></span> | <span data-ttu-id="972e0-119">버전이 변경됨</span><span class="sxs-lookup"><span data-stu-id="972e0-119">Version changed</span></span> |
|-|-|-|-|
| <xref:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)?displayProperty=fullName> | <span data-ttu-id="972e0-120">미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="972e0-120">Preview 1</span></span> |

<!--

### Affected APIs

- `P:System.Windows.Forms.TreeNodeCollection.Item(System.Int32)`

### Category

Windows Forms

-->
