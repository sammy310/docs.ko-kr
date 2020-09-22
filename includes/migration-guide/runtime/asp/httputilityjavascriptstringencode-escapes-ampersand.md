---
ms.openlocfilehash: b648aee35ff44730f545f0fa06f4e0a86615dece
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606958"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="cd502-101">HttpUtility.JavaScriptStringEncode가 앰퍼샌드를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="cd502-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

#### <a name="details"></a><span data-ttu-id="cd502-102">설명</span><span class="sxs-lookup"><span data-stu-id="cd502-102">Details</span></span>

<span data-ttu-id="cd502-103">.NET Framework 4.5부터 <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName>이 앰퍼샌드(&amp;) 문자를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="cd502-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> escapes the ampersand (&amp;) character.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="cd502-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="cd502-104">Suggestion</span></span>

<span data-ttu-id="cd502-105">응용 프로그램이 이 메서드의 이전 동작에 종속되는 경우 aspnet:JavaScriptDoNotEncodeAmpersand 설정을 구성 파일에 있는 [ASP.NET appSettings 요소](/previous-versions/aspnet/hh975440(v=vs.120))에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd502-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>

| <span data-ttu-id="cd502-106">이름</span><span class="sxs-lookup"><span data-stu-id="cd502-106">Name</span></span>    | <span data-ttu-id="cd502-107">값</span><span class="sxs-lookup"><span data-stu-id="cd502-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="cd502-108">Scope</span><span class="sxs-lookup"><span data-stu-id="cd502-108">Scope</span></span>   |<span data-ttu-id="cd502-109">부</span><span class="sxs-lookup"><span data-stu-id="cd502-109">Minor</span></span>|
|<span data-ttu-id="cd502-110">버전</span><span class="sxs-lookup"><span data-stu-id="cd502-110">Version</span></span>|<span data-ttu-id="cd502-111">4.5</span><span class="sxs-lookup"><span data-stu-id="cd502-111">4.5</span></span>|
|<span data-ttu-id="cd502-112">형식</span><span class="sxs-lookup"><span data-stu-id="cd502-112">Type</span></span>|<span data-ttu-id="cd502-113">런타임</span><span class="sxs-lookup"><span data-stu-id="cd502-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="cd502-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="cd502-114">Affected APIs</span></span>

- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String)`
- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)`

-->
