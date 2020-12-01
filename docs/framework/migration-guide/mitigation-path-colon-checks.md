---
title: '완화: 경로 콜론 검사'
description: 적절한 드라이브 구분 기호 구문(콜론)에 대한 검사를 지원하도록 .NET Framework 4.6.2에서 변경된 사항에 대해 알아봅니다.
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
ms.openlocfilehash: 03f1c7249549aae7e3bef986c97fb5f320fbeb2f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96283460"
---
# <a name="mitigation-path-colon-checks"></a><span data-ttu-id="e635d-103">완화: 경로 콜론 검사</span><span class="sxs-lookup"><span data-stu-id="e635d-103">Mitigation: Path Colon Checks</span></span>

<span data-ttu-id="e635d-104">.NET Framework 4.6.2를 대상으로 하는 앱부터 이전에 지원되지 않던 경로를 지원하도록 여러 가지 변경이 수행되었습니다(길이 및 형식 측면에서).</span><span class="sxs-lookup"><span data-stu-id="e635d-104">Starting with apps that target the .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in terms of length and format).</span></span> <span data-ttu-id="e635d-105">특히 적절한 드라이브 구분 기호 구문(콜론)에 대한 확인이 좀 더 정확해졌습니다.</span><span class="sxs-lookup"><span data-stu-id="e635d-105">In particular, checks for the proper drive separator syntax (the colon) were made more correct.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="e635d-106">영향</span><span class="sxs-lookup"><span data-stu-id="e635d-106">Impact</span></span>  

 <span data-ttu-id="e635d-107">이러한 변경으로 인해 <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> 및 <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> 메서드에서 이전에 지원했던 일부 URI 경로가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="e635d-107">These changes block some URI paths the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods previously supported.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="e635d-108">완화</span><span class="sxs-lookup"><span data-stu-id="e635d-108">Mitigation</span></span>  

 <span data-ttu-id="e635d-109">전에는 허용되었지만 <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> 및 <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> 메서드로 더 이상 지원되지 않는 경로 문제를 해결하려면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e635d-109">To work around the problem of a previously acceptable path that is no longer supported by the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods, you can do the following:</span></span>  
  
- <span data-ttu-id="e635d-110">URL에서 스키마를 수동으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e635d-110">Manually remove the scheme from a URL.</span></span> <span data-ttu-id="e635d-111">예를 들어 URL에서 `file://`을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e635d-111">For example, remove `file://` from a URL.</span></span>  
  
- <span data-ttu-id="e635d-112">URI를 <xref:System.Uri> 생성자에 전달하고 <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> 속성 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e635d-112">Pass the URI to a <xref:System.Uri> constructor,  and retrieve the value of the <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> property.</span></span>  
  
- <span data-ttu-id="e635d-113">`Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> 스위치를 `true`로 설정하여 새 경로 정규화를 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="e635d-113">Opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> switch to `true`.</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
    </runtime>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e635d-114">참조</span><span class="sxs-lookup"><span data-stu-id="e635d-114">See also</span></span>

- [<span data-ttu-id="e635d-115">애플리케이션 호환성</span><span class="sxs-lookup"><span data-stu-id="e635d-115">Application compatibility</span></span>](application-compatibility.md)
