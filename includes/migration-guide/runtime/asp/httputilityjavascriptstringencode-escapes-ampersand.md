---
ms.openlocfilehash: d587e542a72d584502ac3ac892619cc38b88ef77
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620145"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="a34be-101">HttpUtility.JavaScriptStringEncode가 앰퍼샌드를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="a34be-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

#### <a name="details"></a><span data-ttu-id="a34be-102">설명</span><span class="sxs-lookup"><span data-stu-id="a34be-102">Details</span></span>

<span data-ttu-id="a34be-103">.NET Framework 4.5부터 <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName>이 앰퍼샌드(&amp;) 문자를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="a34be-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> escapes the ampersand (&amp;) character.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a34be-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="a34be-104">Suggestion</span></span>

<span data-ttu-id="a34be-105">응용 프로그램이 이 메서드의 이전 동작에 종속되는 경우 aspnet:JavaScriptDoNotEncodeAmpersand 설정을 구성 파일에 있는 [ASP.NET appSettings 요소](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120))에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a34be-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>

| <span data-ttu-id="a34be-106">이름</span><span class="sxs-lookup"><span data-stu-id="a34be-106">Name</span></span>    | <span data-ttu-id="a34be-107">값</span><span class="sxs-lookup"><span data-stu-id="a34be-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a34be-108">Scope</span><span class="sxs-lookup"><span data-stu-id="a34be-108">Scope</span></span>   |<span data-ttu-id="a34be-109">부</span><span class="sxs-lookup"><span data-stu-id="a34be-109">Minor</span></span>|
|<span data-ttu-id="a34be-110">버전</span><span class="sxs-lookup"><span data-stu-id="a34be-110">Version</span></span>|<span data-ttu-id="a34be-111">4.5</span><span class="sxs-lookup"><span data-stu-id="a34be-111">4.5</span></span>|
|<span data-ttu-id="a34be-112">형식</span><span class="sxs-lookup"><span data-stu-id="a34be-112">Type</span></span>|<span data-ttu-id="a34be-113">런타임</span><span class="sxs-lookup"><span data-stu-id="a34be-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a34be-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="a34be-114">Affected APIs</span></span>

-<xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
