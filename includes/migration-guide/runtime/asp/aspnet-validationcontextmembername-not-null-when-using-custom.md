---
ms.openlocfilehash: df13f6938ebaf8e96bb2825c1495044621f1c31b
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802584"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a><span data-ttu-id="8dc16-101">사용자 지정 DataAnnotations.ValidationAttribute를 사용할 때 ASP.NET ValidationContext.MemberName은 NULL이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8dc16-101">ASP.NET ValidationContext.MemberName is not NULL when using custom DataAnnotations.ValidationAttribute</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8dc16-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="8dc16-102">Details</span></span>|<span data-ttu-id="8dc16-103">.NET Framework 4.7.2 이하 버전에서 사용자 지정 <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>을 사용할 때 <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> 속성이 <code>null</code>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc16-103">In .NET Framework 4.7.2 and earlier versions, when using a custom <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>, the <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> property returns <code>null</code>.</span></span>  <span data-ttu-id="8dc16-104">.NET Framework 4.8에서는 멤버 이름을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc16-104">In .NET Framework 4.8, it returns the member name.</span></span>|
|<span data-ttu-id="8dc16-105">제안</span><span class="sxs-lookup"><span data-stu-id="8dc16-105">Suggestion</span></span>|<span data-ttu-id="8dc16-106"><xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> 속성의 기본 동작은 동일하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dc16-106">The default behavior of the <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> property remains the same.</span></span>  <span data-ttu-id="8dc16-107"><code>ValidationContext.MemberName</code> 속성에서 유효한 값을 검색하려면 다음 설정을 앱 구성 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc16-107">To retrieve a valid value from the <code>ValidationContext.MemberName</code> property, add the following setting to your app config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="8dc16-108">범위</span><span class="sxs-lookup"><span data-stu-id="8dc16-108">Scope</span></span>|<span data-ttu-id="8dc16-109">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="8dc16-109">Unknown</span></span>|
|<span data-ttu-id="8dc16-110">버전</span><span class="sxs-lookup"><span data-stu-id="8dc16-110">Version</span></span>|<span data-ttu-id="8dc16-111">4.8</span><span class="sxs-lookup"><span data-stu-id="8dc16-111">4.8</span></span>|
|<span data-ttu-id="8dc16-112">Type</span><span class="sxs-lookup"><span data-stu-id="8dc16-112">Type</span></span>|<span data-ttu-id="8dc16-113">런타임</span><span class="sxs-lookup"><span data-stu-id="8dc16-113">Runtime</span></span>|
|<span data-ttu-id="8dc16-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="8dc16-114">Affected APIs</span></span>|<ul><li><xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|

