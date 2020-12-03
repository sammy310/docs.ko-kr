---
title: '호환성이 손상되는 변경: TripleDES.Create에서 생성된 인스턴스의 기본 FeedbackSize 값이 변경됨'
description: TripleDES.Create()에서 반환된 TripleDES 인스턴스의 FeedbackSize 속성에 대한 기본값이 64에서 8로 변경된 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 10/16/2020
ms.openlocfilehash: 4179da17bf2e5cc5fcc7d64d83ba92119f912042
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759894"
---
# <a name="default-feedbacksize-value-for-instances-created-by-tripledescreate-changed"></a><span data-ttu-id="69fff-103">TripleDES.Create에서 생성된 인스턴스의 기본 FeedbackSize 값이 변경됨</span><span class="sxs-lookup"><span data-stu-id="69fff-103">Default FeedbackSize value for instances created by TripleDES.Create changed</span></span>

<span data-ttu-id="69fff-104"><xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType>에서 반환된 <xref:System.Security.Cryptography.TripleDES> 인스턴스에서 <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=nameWithType> 속성의 기본값은 .NET Framework에서 더 쉽게 마이그레이션할 수 있도록 64에서 8로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="69fff-104">The default value for the <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=nameWithType> property on the <xref:System.Security.Cryptography.TripleDES> instance returned from <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> has changed from 64 to 8 to make migration from .NET Framework easier.</span></span> <span data-ttu-id="69fff-105">호출자 코드에서 직접 사용되지 않는 경우 이 속성은 <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> 속성이 <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType>인 경우에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="69fff-105">This property, unless used directly in caller code, is used only when the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> property is <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="69fff-106"><xref:System.Security.Cryptography.CipherMode.CFB> 모드 지원은 5.0 RC1 릴리스의 .NET에 처음 추가되었으므로 .NET 5.0 RC1 및 .NET 5.0 RC2 애플리케이션만 이 변경의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="69fff-106">Support for the <xref:System.Security.Cryptography.CipherMode.CFB> mode was first added to .NET for the 5.0 RC1 release, so only .NET 5.0 RC1 and .NET 5.0 RC2 applications should be impacted by this change.</span></span>

## <a name="change-description"></a><span data-ttu-id="69fff-107">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="69fff-107">Change description</span></span>

<span data-ttu-id="69fff-108">.NET Core 및 이전 .NET 5.0 시험판 버전에서 `TripleDES.Create().FeedbackSize`의 기본값은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="69fff-108">In .NET Core and previous pre-release versions of .NET 5.0, `TripleDES.Create().FeedbackSize` has a default value of 64.</span></span> <span data-ttu-id="69fff-109">RTM 버전의 .NET 5.0부터 `TripleDES.Create().FeedbackSize`의 기본값은 8입니다.</span><span class="sxs-lookup"><span data-stu-id="69fff-109">Starting in the RTM version of .NET 5.0, `TripleDES.Create().FeedbackSize` has a default value of 8.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="69fff-110">변경 이유</span><span class="sxs-lookup"><span data-stu-id="69fff-110">Reason for change</span></span>

<span data-ttu-id="69fff-111">.NET Framework에서 <xref:System.Security.Cryptography.TripleDES> 기본 클래스는 <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> 값을 기본적으로 64로 설정하지만 <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> 클래스는 기본값을 8로 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="69fff-111">In .NET Framework, the <xref:System.Security.Cryptography.TripleDES> base class defaults the value of <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> to 64, but the <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> class overwrites the default to 8.</span></span> <span data-ttu-id="69fff-112"><xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> 속성이 버전 2.0의 .NET Core에 도입될 때 동일한 동작이 유지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="69fff-112">When the <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> property was introduced to .NET Core in version 2.0, this same behavior was preserved.</span></span> <span data-ttu-id="69fff-113">그러나 .NET Framework에서 <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType>은 <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>의 인스턴스를 반환하므로 알고리즘 팩터리의 기본값은 8입니다.</span><span class="sxs-lookup"><span data-stu-id="69fff-113">However, in .NET Framework, <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> returns an instance of <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>, so the default value from the algorithm factory is 8.</span></span> <span data-ttu-id="69fff-114">.NET Core 및 .NET 5 이상의 경우 알고리즘 팩터리는 지금까지 기본값이 64였던 퍼블릭이 아닌 구현을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="69fff-114">For .NET Core and .NET 5+, the algorithm factory returns a non-public implementation, which, until now, had a default value of 64.</span></span>

<span data-ttu-id="69fff-115"><xref:System.Security.Cryptography.TripleDES> 구현 클래스의 <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> 값을 8로 변경하면 암호화 모드를 <xref:System.Security.Cryptography.CipherMode.CFB>로 지정하지만 <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> 속성을 명시적으로 할당하지 않은 .NET Framework용으로 작성된 애플리케이션이 .NET 5에서 계속 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69fff-115">Changing the <xref:System.Security.Cryptography.TripleDES> implementation class' <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> value to 8 allows for applications written for .NET Framework that specified the cipher mode as <xref:System.Security.Cryptography.CipherMode.CFB> but didn't explicitly assign the <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> property, to continue to function on .NET 5.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="69fff-116">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="69fff-116">Version introduced</span></span>

<span data-ttu-id="69fff-117">5.0</span><span class="sxs-lookup"><span data-stu-id="69fff-117">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="69fff-118">권장 조치</span><span class="sxs-lookup"><span data-stu-id="69fff-118">Recommended action</span></span>

<span data-ttu-id="69fff-119">다음 조건이 충족되면 RC1 또는 RC2 버전의 .NET 5.0에서 데이터를 암호화하거나 암호 해독하는 애플리케이션은 CFB64를 사용하여 해당 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="69fff-119">Applications that encrypt or decrypt data in the RC1 or RC2 versions of .NET 5.0 do so with CFB64, when the following conditions are met:</span></span>

- <span data-ttu-id="69fff-120"><xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType>의 <xref:System.Security.Cryptography.TripleDES> 인스턴스 포함.</span><span class="sxs-lookup"><span data-stu-id="69fff-120">With a <xref:System.Security.Cryptography.TripleDES> instance from <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="69fff-121"><xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>의 기본값 사용.</span><span class="sxs-lookup"><span data-stu-id="69fff-121">Using the default value for <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>.</span></span>
- <span data-ttu-id="69fff-122"><xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> 속성이 <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType>로 설정됨.</span><span class="sxs-lookup"><span data-stu-id="69fff-122">With the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> property set to <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="69fff-123">이 동작을 유지 관리하려면 `64`에 <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> 속성을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="69fff-123">To maintain this behavior, assign the <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> property to `64`.</span></span>

<span data-ttu-id="69fff-124">일부 `TripleDES` 구현은 <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>에 대해 동일한 기본값을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69fff-124">Not all `TripleDES` implementations use the same default for <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>.</span></span> <span data-ttu-id="69fff-125"><xref:System.Security.Cryptography.TripleDES> 인스턴스에서 <xref:System.Security.Cryptography.CipherMode.CFB> 암호화 모드를 사용하는 경우 항상 <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> 속성 값을 명시적으로 할당하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="69fff-125">We recommend that if you use the <xref:System.Security.Cryptography.CipherMode.CFB> cipher mode on <xref:System.Security.Cryptography.TripleDES> instances, you should always explicitly assign the <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> property value.</span></span>

```csharp
TripleDES cipher = TripleDES.Create();
cipher.Mode = CipherMode.CFB;
// Explicitly set the FeedbackSize for CFB to control between CFB8 and CFB64.
cipher.FeedbackSize = 8;
```

## <a name="affected-apis"></a><span data-ttu-id="69fff-126">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="69fff-126">Affected APIs</span></span>

- <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Security.Cryptography.TripleDES.Create`
- `P:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize`

### Category

- Cryptography

-->
