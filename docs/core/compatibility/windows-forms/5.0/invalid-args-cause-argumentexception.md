---
title: '호환성이 손상되는 변경: WinForms 메서드는 이제 ArgumentException을 throw함'
description: 일부 Windows Forms 메서드가 잘못된 인수에 대해 ArgumentException을 throw하는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 07/18/2020
ms.openlocfilehash: 9823e9162a562081cdd64346a502ca136b51fa75
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256141"
---
# <a name="winforms-methods-now-throw-argumentexception"></a><span data-ttu-id="f44f1-103">WinForms 메서드는 이제 ArgumentException을 throw함</span><span class="sxs-lookup"><span data-stu-id="f44f1-103">WinForms methods now throw ArgumentException</span></span>

<span data-ttu-id="f44f1-104">이제 일부 Windows Forms 메서드에서는 이전에는 없었던 잘못된 인수에 대한 <xref:System.ArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="f44f1-104">Some Windows Forms methods now throw an <xref:System.ArgumentException> for invalid arguments, where previously they did not.</span></span>

## <a name="change-description"></a><span data-ttu-id="f44f1-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="f44f1-105">Change description</span></span>

<span data-ttu-id="f44f1-106">이전에는 예기치 않거나 잘못된 형식의 인수를 특정 Windows Forms 메서드에 전달하면 불분명한 상태가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f44f1-106">Previously, passing arguments of an unexpected or incorrect type to certain Windows Forms methods would result in an indeterminate state.</span></span> <span data-ttu-id="f44f1-107">.NET 5부터 해당 메서드는 잘못된 인수를 전달하면 <xref:System.ArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="f44f1-107">Starting in .NET 5, these methods now throw an <xref:System.ArgumentException> when passed invalid arguments.</span></span>

<span data-ttu-id="f44f1-108"><xref:System.ArgumentException> throw는 .NET 런타임의 동작을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f44f1-108">Throwing an <xref:System.ArgumentException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="f44f1-109">또한 잘못된 인수를 명확하게 전달하여 디버깅 환경을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="f44f1-109">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="f44f1-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="f44f1-110">Version introduced</span></span>

<span data-ttu-id="f44f1-111">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="f44f1-111">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f44f1-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="f44f1-112">Recommended action</span></span>

- <span data-ttu-id="f44f1-113">잘못된 인수가 전달되지 않도록 코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f44f1-113">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="f44f1-114">필요한 경우 메서드를 호출할 때 <xref:System.ArgumentException>을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f44f1-114">If necessary, handle an <xref:System.ArgumentException> when calling the method.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="f44f1-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="f44f1-115">Affected APIs</span></span>

<span data-ttu-id="f44f1-116">다음 표에서는 영향을 받는 메서드 및 매개 변수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f44f1-116">The following table lists the affected methods and parameters:</span></span>

| <span data-ttu-id="f44f1-117">메서드</span><span class="sxs-lookup"><span data-stu-id="f44f1-117">Method</span></span> | <span data-ttu-id="f44f1-118">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="f44f1-118">Parameter name</span></span> | <span data-ttu-id="f44f1-119">조건</span><span class="sxs-lookup"><span data-stu-id="f44f1-119">Condition</span></span> | <span data-ttu-id="f44f1-120">추가된 버전</span><span class="sxs-lookup"><span data-stu-id="f44f1-120">Version added</span></span> |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | <span data-ttu-id="f44f1-121">인수가 <xref:System.Windows.Forms.TabPage> 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f44f1-121">Argument is not of type <xref:System.Windows.Forms.TabPage>.</span></span> | <span data-ttu-id="f44f1-122">미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="f44f1-122">Preview 1</span></span> |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | <span data-ttu-id="f44f1-123">인수는 `null`, <xref:System.String.Empty?displayProperty=nameWithType> 또는 공백입니다.</span><span class="sxs-lookup"><span data-stu-id="f44f1-123">Argument is `null`, <xref:System.String.Empty?displayProperty=nameWithType>, or white space.</span></span> | <span data-ttu-id="f44f1-124">Preview 5</span><span class="sxs-lookup"><span data-stu-id="f44f1-124">Preview 5</span></span> |
| <xref:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)> | `culture` | <span data-ttu-id="f44f1-125">지정된 문화권의 `InputLanguage`를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f44f1-125">Unable to retrieve an `InputLanguage` for the specified culture.</span></span> | <span data-ttu-id="f44f1-126">미리 보기 7</span><span class="sxs-lookup"><span data-stu-id="f44f1-126">Preview 7</span></span> |

<!--

### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`
- `M:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)`

### Category

Windows Forms

-->
