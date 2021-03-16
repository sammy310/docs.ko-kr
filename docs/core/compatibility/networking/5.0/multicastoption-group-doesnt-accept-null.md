---
title: '호환성이 손상되는 변경: MulticastOption.Group에서 null 값을 허용하지 않음'
description: MulticastOption.Group에서 Null 값을 더 이상 허용하지 않는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 08/18/2020
ms.openlocfilehash: 09c6415d275361abee8285aabdda13ccd9727043
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256454"
---
# <a name="multicastoptiongroup-doesnt-accept-a-null-value"></a><span data-ttu-id="2e1fb-103">MulticastOption.Group에서 null 값을 허용하지 않음</span><span class="sxs-lookup"><span data-stu-id="2e1fb-103">MulticastOption.Group doesn't accept a null value</span></span>

<span data-ttu-id="2e1fb-104"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType>에서는 `null` 값을 더 이상 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1fb-104"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> no longer accepts a value of `null`.</span></span> <span data-ttu-id="2e1fb-105">속성을 `null`로 설정하면 <xref:System.ArgumentNullException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e1fb-105">If you set the property to `null`, an <xref:System.ArgumentNullException> is thrown.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="2e1fb-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="2e1fb-106">Version introduced</span></span>

<span data-ttu-id="2e1fb-107">5.0</span><span class="sxs-lookup"><span data-stu-id="2e1fb-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="2e1fb-108">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="2e1fb-108">Change description</span></span>

<span data-ttu-id="2e1fb-109">이전 버전의 .NET에서는 <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> 속성을 `null`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1fb-109">In previous versions of .NET, you can set the <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> property to `null`.</span></span> <span data-ttu-id="2e1fb-110">나중에 <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>에 <xref:System.Net.Sockets.MulticastOption>을 전달하면 런타임에서 <xref:System.NullReferenceException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e1fb-110">If the <xref:System.Net.Sockets.MulticastOption> is later passed to <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>, the runtime throws a <xref:System.NullReferenceException>.</span></span>

<span data-ttu-id="2e1fb-111">.NET 5 이상에서 속성을 `null`로 설정하면 <xref:System.ArgumentNullException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e1fb-111">In .NET 5 and later, an <xref:System.ArgumentNullException> is thrown if you set the property to `null`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="2e1fb-112">변경 이유</span><span class="sxs-lookup"><span data-stu-id="2e1fb-112">Reason for change</span></span>

<span data-ttu-id="2e1fb-113">프레임워크 디자인 지침과 일치하도록, 값이 `null`이면 <xref:System.ArgumentNullException>을 throw하도록 속성이 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1fb-113">To be consistent with the Framework Design Guidelines, the property has been updated to throw an <xref:System.ArgumentNullException> if the value is `null`.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="2e1fb-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="2e1fb-114">Recommended action</span></span>

<span data-ttu-id="2e1fb-115"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType>을 `null`으로 설정하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e1fb-115">Make sure that you don't set <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> to `null`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="2e1fb-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="2e1fb-116">Affected APIs</span></span>

- <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Net.Sockets.MulticastOption.Group`

### Category

Networking

-->
