---
ms.openlocfilehash: 424e8ff704b888aa3d2c1254ac712da4034f59b8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616119"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a><span data-ttu-id="f0a0b-101">ObsoleteAttribute가 WinMD 시나리오에서 ObsoleteAttribute와 DeprecatedAttribute를 내보냄</span><span class="sxs-lookup"><span data-stu-id="f0a0b-101">ObsoleteAttribute exports as both ObsoleteAttribute and DeprecatedAttribute in WinMD scenarios</span></span>

#### <a name="details"></a><span data-ttu-id="f0a0b-102">설명</span><span class="sxs-lookup"><span data-stu-id="f0a0b-102">Details</span></span>

<span data-ttu-id="f0a0b-103">Windows 메타데이터 라이브러리(.winmd 파일)를 만들 때 <xref:System.ObsoleteAttribute?displayProperty=fullName> 특성은 <xref:System.ObsoleteAttribute?displayProperty=fullName> 및 [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute)로서 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="f0a0b-103">When you create a Windows Metadata library (.winmd file), the <xref:System.ObsoleteAttribute?displayProperty=fullName> attribute is exported as both <xref:System.ObsoleteAttribute?displayProperty=fullName> and [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f0a0b-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="f0a0b-104">Suggestion</span></span>

<span data-ttu-id="f0a0b-105"><xref:System.ObsoleteAttribute?displayProperty=fullName> 특성이 사용된 기존 소스 코드를 다시 컴파일하면 C++/CX 또는 JavaScript의 해당 코드가 사용될 때 경고가 발생할 수 있습니다. <xref:System.ObsoleteAttribute?displayProperty=fullName> 및 [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) 모두를 관리되는 어셈블리의 코드에 적용하는 것은 좋지 않습니다. 빌드 경고가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0a0b-105">Recompilation of existing source code that uses the <xref:System.ObsoleteAttribute?displayProperty=fullName> attribute may generate warnings when consuming that code from C++/CX or JavaScript.We do not recommend applying both <xref:System.ObsoleteAttribute?displayProperty=fullName> and [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) to code in managed assemblies; it may result in build warnings.</span></span>

| <span data-ttu-id="f0a0b-106">이름</span><span class="sxs-lookup"><span data-stu-id="f0a0b-106">Name</span></span>    | <span data-ttu-id="f0a0b-107">값</span><span class="sxs-lookup"><span data-stu-id="f0a0b-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f0a0b-108">Scope</span><span class="sxs-lookup"><span data-stu-id="f0a0b-108">Scope</span></span>   | <span data-ttu-id="f0a0b-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f0a0b-109">Edge</span></span>        |
| <span data-ttu-id="f0a0b-110">버전</span><span class="sxs-lookup"><span data-stu-id="f0a0b-110">Version</span></span> | <span data-ttu-id="f0a0b-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="f0a0b-111">4.5.1</span></span>       |
| <span data-ttu-id="f0a0b-112">형식</span><span class="sxs-lookup"><span data-stu-id="f0a0b-112">Type</span></span>    | <span data-ttu-id="f0a0b-113">대상 변경</span><span class="sxs-lookup"><span data-stu-id="f0a0b-113">Retargeting</span></span> |
