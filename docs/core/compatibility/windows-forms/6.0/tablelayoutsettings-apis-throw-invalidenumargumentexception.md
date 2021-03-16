---
title: '호환성이 손상되는 변경: 일부 TableLayoutSettings 속성이 InvalidEnumArgumentException을 throw함'
description: 이제 일부 TableLayoutSettings API가 잘못된 인수에 대해 InvalidEnumArgumentException을 throw하는 .NET 6의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 01/18/2021
ms.openlocfilehash: 2da097122b935ec3a60c2bb009cc8ebbcff6468e
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255726"
---
# <a name="selected-tablelayoutsettings-properties-throw-invalidenumargumentexception"></a><span data-ttu-id="b22aa-103">선택한 TableLayoutSettings 속성이 InvalidEnumArgumentException을 throw함</span><span class="sxs-lookup"><span data-stu-id="b22aa-103">Selected TableLayoutSettings properties throw InvalidEnumArgumentException</span></span>

<span data-ttu-id="b22aa-104">잘못된 값을 할당하려고 하면 이제 선택한 <xref:System.Windows.Forms.TableLayoutSettings> 속성이 <xref:System.ComponentModel.InvalidEnumArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="b22aa-104">Selected <xref:System.Windows.Forms.TableLayoutSettings> properties now throw an <xref:System.ComponentModel.InvalidEnumArgumentException> if you attempt to assign an incorrect value.</span></span>

## <a name="change-description"></a><span data-ttu-id="b22aa-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="b22aa-105">Change description</span></span>

<span data-ttu-id="b22aa-106">이전 .NET 버전에서는 잘못된 값을 할당하려고 하면 해당 속성이 <xref:System.ArgumentOutOfRangeException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="b22aa-106">In previous .NET versions, these properties throw an <xref:System.ArgumentOutOfRangeException> if you attempt to assign an incorrect value.</span></span> <span data-ttu-id="b22aa-107">.NET 6부터 해당 속성은 이 경우에 <xref:System.ComponentModel.InvalidEnumArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="b22aa-107">Starting in .NET 6, these properties throw an <xref:System.ComponentModel.InvalidEnumArgumentException> in such cases.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="b22aa-108">변경 이유</span><span class="sxs-lookup"><span data-stu-id="b22aa-108">Reason for change</span></span>

<span data-ttu-id="b22aa-109"><xref:System.ComponentModel.InvalidEnumArgumentException>을 throw하는 것은 유사한 상황에서 기존 Windows Forms API에 맞추려는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b22aa-109">Throwing <xref:System.ComponentModel.InvalidEnumArgumentException> is in line with the existing Windows Forms API in similar situations.</span></span> <span data-ttu-id="b22aa-110">또한 이 예외를 throw하면 개발자에게 향상된 디버그 환경이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b22aa-110">Throwing this exception also provides developers with a better debug experience.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="b22aa-111">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="b22aa-111">Version introduced</span></span>

<span data-ttu-id="b22aa-112">.NET 6.0</span><span class="sxs-lookup"><span data-stu-id="b22aa-112">.NET 6.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="b22aa-113">권장 조치</span><span class="sxs-lookup"><span data-stu-id="b22aa-113">Recommended action</span></span>

- <span data-ttu-id="b22aa-114">잘못된 값이 할당되지 않도록 코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="b22aa-114">Update the code to prevent assigning incorrect values.</span></span>
- <span data-ttu-id="b22aa-115">필요한 경우 이 API에 액세스할 때 <xref:System.ComponentModel.InvalidEnumArgumentException>을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b22aa-115">If necessary, handle an <xref:System.ComponentModel.InvalidEnumArgumentException> when accessing these APIs.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="b22aa-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="b22aa-116">Affected APIs</span></span>

<span data-ttu-id="b22aa-117">다음 표에서는 영향을 받는 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b22aa-117">The following table lists the affected properties:</span></span>

| <span data-ttu-id="b22aa-118">속성</span><span class="sxs-lookup"><span data-stu-id="b22aa-118">Property</span></span> | <span data-ttu-id="b22aa-119">버전이 변경됨</span><span class="sxs-lookup"><span data-stu-id="b22aa-119">Version changed</span></span> |
|-|-|-|-|
| <xref:System.Windows.Forms.TableLayoutPanel.CellBorderStyle?displayProperty=fullName> | <span data-ttu-id="b22aa-120">미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="b22aa-120">Preview 1</span></span> |
| <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle?displayProperty=fullName> | <span data-ttu-id="b22aa-121">미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="b22aa-121">Preview 1</span></span> |

<!--

### Affected APIs

- `P:System.Windows.Forms.TableLayoutPanel.CellBorderStyle`
- `P:System.Windows.Forms.TableLayoutPanel.GrowStyle`

### Category

Windows Forms

-->
