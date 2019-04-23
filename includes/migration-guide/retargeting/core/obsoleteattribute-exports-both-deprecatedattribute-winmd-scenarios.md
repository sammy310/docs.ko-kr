---
ms.openlocfilehash: e8c48c4b1031813ce62f576e5bf1f94c082dfe4b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774434"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a><span data-ttu-id="eef55-101">ObsoleteAttribute가 WinMD 시나리오에서 ObsoleteAttribute와 DeprecatedAttribute를 내보냄</span><span class="sxs-lookup"><span data-stu-id="eef55-101">ObsoleteAttribute exports as both ObsoleteAttribute and DeprecatedAttribute in WinMD scenarios</span></span>

|   |   |
|---|---|
|<span data-ttu-id="eef55-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="eef55-102">Details</span></span>|<span data-ttu-id="eef55-103">Windows 메타데이터 라이브러리(.winmd 파일)를 만들 때 <xref:System.ObsoleteAttribute?displayProperty=name> 특성은 <xref:System.ObsoleteAttribute?displayProperty=name> 및 [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute)로서 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="eef55-103">When you create a Windows Metadata library (.winmd file), the <xref:System.ObsoleteAttribute?displayProperty=name> attribute is exported as both <xref:System.ObsoleteAttribute?displayProperty=name> and [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute).</span></span>|
|<span data-ttu-id="eef55-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="eef55-104">Suggestion</span></span>|<span data-ttu-id="eef55-105"><xref:System.ObsoleteAttribute?displayProperty=name> 특성이 사용된 기존 소스 코드를 다시 컴파일하면 C++/CX 또는 JavaScript의 해당 코드가 사용될 때 경고가 발생할 수 있습니다. <xref:System.ObsoleteAttribute?displayProperty=name> 및 [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) 모두를 관리되는 어셈블리의 코드에 적용하는 것은 좋지 않습니다. 빌드 경고가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef55-105">Recompilation of existing source code that uses the <xref:System.ObsoleteAttribute?displayProperty=name> attribute may generate warnings when consuming that code from C++/CX or JavaScript.We do not recommend applying both <xref:System.ObsoleteAttribute?displayProperty=name> and [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) to code in managed assemblies; it may result in build warnings.</span></span>|
|<span data-ttu-id="eef55-106">범위</span><span class="sxs-lookup"><span data-stu-id="eef55-106">Scope</span></span>|<span data-ttu-id="eef55-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="eef55-107">Edge</span></span>|
|<span data-ttu-id="eef55-108">버전</span><span class="sxs-lookup"><span data-stu-id="eef55-108">Version</span></span>|<span data-ttu-id="eef55-109">4.5.1</span><span class="sxs-lookup"><span data-stu-id="eef55-109">4.5.1</span></span>|
|<span data-ttu-id="eef55-110">형식</span><span class="sxs-lookup"><span data-stu-id="eef55-110">Type</span></span>|<span data-ttu-id="eef55-111">대상 변경</span><span class="sxs-lookup"><span data-stu-id="eef55-111">Retargeting</span></span>|
