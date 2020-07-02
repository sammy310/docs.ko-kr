---
ms.openlocfilehash: 7002c74594993ac6bf28643ef3271da356190c66
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622067"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a><span data-ttu-id="dda3f-101">사용자 지정 DataAnnotations.ValidationAttribute를 사용할 때 ASP.NET ValidationContext.MemberName은 NULL이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="dda3f-101">ASP.NET ValidationContext.MemberName is not NULL when using custom DataAnnotations.ValidationAttribute</span></span>

#### <a name="details"></a><span data-ttu-id="dda3f-102">설명</span><span class="sxs-lookup"><span data-stu-id="dda3f-102">Details</span></span>

<span data-ttu-id="dda3f-103">.NET Framework 4.7.2 이하 버전에서 사용자 지정 <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>을 사용할 때 <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> 속성이 `null`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dda3f-103">In .NET Framework 4.7.2 and earlier versions, when using a custom <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>, the <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> property returns `null`.</span></span> <span data-ttu-id="dda3f-104">2019년 10월 업데이트 이전의 .NET Framework 4.8 버전에서는 멤버 이름을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dda3f-104">In .NET Framework 4.8 version prior to the October 2019 update, it returns the member name.</span></span> <span data-ttu-id="dda3f-105">.NET Framework 4.8의 [.NET Framework 2019년 10월 품질 롤업 미리 보기](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/)부터 기본적으로 `null`을 반환하지만 대신 멤버 이름을 반환하도록 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dda3f-105">Starting with [.NET Framework October 2019 Preview of Quality Rollup](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) for .NET Framework 4.8, it returns `null` by default, but you can opt in to return the member name instead.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="dda3f-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="dda3f-106">Suggestion</span></span>

<span data-ttu-id="dda3f-107">.NET Framework 4.8 이상 버전의 [.NET Framework 2019년 10월 품질 롤업 미리 보기](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/)에서 이 속성이 멤버 이름을 반환하려면 *web.config* 파일에 다음 설정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dda3f-107">Add the following setting to your *web.config* file for the property to return the member name in [.NET Framework October 2019 Preview of Quality Rollup](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) for .NET Framework 4.8 and later versions:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="dda3f-108">2019년 10월 업데이트 이전의 .NET Framework 4.8 버전에서는 *web.config* 파일에 이를 추가하면 이전 동작이 복원되고 속성이 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dda3f-108">In .NET Framework 4.8 version prior to the October 2019 update,  adding this to your *web.config* file restores the previous behavior and the property returns `null`.</span></span>

| <span data-ttu-id="dda3f-109">이름</span><span class="sxs-lookup"><span data-stu-id="dda3f-109">Name</span></span>    | <span data-ttu-id="dda3f-110">값</span><span class="sxs-lookup"><span data-stu-id="dda3f-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="dda3f-111">Scope</span><span class="sxs-lookup"><span data-stu-id="dda3f-111">Scope</span></span>   |<span data-ttu-id="dda3f-112">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="dda3f-112">Unknown</span></span>|
|<span data-ttu-id="dda3f-113">버전</span><span class="sxs-lookup"><span data-stu-id="dda3f-113">Version</span></span>|<span data-ttu-id="dda3f-114">4.8</span><span class="sxs-lookup"><span data-stu-id="dda3f-114">4.8</span></span>|
|<span data-ttu-id="dda3f-115">형식</span><span class="sxs-lookup"><span data-stu-id="dda3f-115">Type</span></span>|<span data-ttu-id="dda3f-116">런타임</span><span class="sxs-lookup"><span data-stu-id="dda3f-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="dda3f-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="dda3f-117">Affected APIs</span></span>

-<xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|
