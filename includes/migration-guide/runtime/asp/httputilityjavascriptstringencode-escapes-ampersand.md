---
ms.openlocfilehash: 0056baa1e5f0cdc5bfcf8b0e83c9490ec5722926
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235707"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="a4f04-101">HttpUtility.JavaScriptStringEncode가 앰퍼샌드를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f04-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a4f04-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="a4f04-102">Details</span></span>|<span data-ttu-id="a4f04-103">.NET Framework 4.5부터 <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name>이 앰퍼샌드(&amp;) 문자를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f04-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name> escapes the ampersand (&amp;) character.</span></span>|
|<span data-ttu-id="a4f04-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="a4f04-104">Suggestion</span></span>|<span data-ttu-id="a4f04-105">응용 프로그램이 이 메서드의 이전 동작에 종속되는 경우 aspnet:JavaScriptDoNotEncodeAmpersand 설정을 구성 파일에 있는 [ASP.NET appSettings 요소](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120))에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f04-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>|
|<span data-ttu-id="a4f04-106">범위</span><span class="sxs-lookup"><span data-stu-id="a4f04-106">Scope</span></span>|<span data-ttu-id="a4f04-107">부</span><span class="sxs-lookup"><span data-stu-id="a4f04-107">Minor</span></span>|
|<span data-ttu-id="a4f04-108">버전</span><span class="sxs-lookup"><span data-stu-id="a4f04-108">Version</span></span>|<span data-ttu-id="a4f04-109">4.5</span><span class="sxs-lookup"><span data-stu-id="a4f04-109">4.5</span></span>|
|<span data-ttu-id="a4f04-110">형식</span><span class="sxs-lookup"><span data-stu-id="a4f04-110">Type</span></span>|<span data-ttu-id="a4f04-111">런타임</span><span class="sxs-lookup"><span data-stu-id="a4f04-111">Runtime</span></span>|
|<span data-ttu-id="a4f04-112">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="a4f04-112">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
