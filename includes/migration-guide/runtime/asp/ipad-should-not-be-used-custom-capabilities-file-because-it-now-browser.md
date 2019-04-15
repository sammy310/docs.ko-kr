---
ms.openlocfilehash: 84f570cbbd97be79426e117d4c97ec182a397fd4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235539"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a><span data-ttu-id="719ca-101">이제 iPad는 브라우저 기능이므로 사용자 지정 기능 파일에서 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="719ca-101">IPad should not be used in custom capabilities file because it is now a browser capability</span></span>

|   |   |
|---|---|
|<span data-ttu-id="719ca-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="719ca-102">Details</span></span>|<span data-ttu-id="719ca-103">.NET Framework 4.5부터 iPad는 기본 ASP.NET 브라우저 기능 파일의 식별자이므로 사용자 지정 기능 파일에 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="719ca-103">Beginning in .NET Framework 4.5, iPad is an identifier in the default ASP.NET browser capabilities file, so it should not be used in a custom capabilities file</span></span>|
|<span data-ttu-id="719ca-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="719ca-104">Suggestion</span></span>|<span data-ttu-id="719ca-105">iPad 관련 기능이 필요한 경우, 사용자 에이전트 일치로 새로운 &quot;IPad&quot; ID를 생성하는 대신 사전 정의된 게이트웨이 refID &quot;IPad&quot;에서 기능을 설정하여 iPad 동작을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="719ca-105">If iPad-specific capabilities are required, it is necessary to modify iPad behavior by setting capabilities on the pre-defined gateway refID &quot;IPad&quot; instead of by generating a new &quot;IPad&quot; ID by user agent matching.</span></span>|
|<span data-ttu-id="719ca-106">범위</span><span class="sxs-lookup"><span data-stu-id="719ca-106">Scope</span></span>|<span data-ttu-id="719ca-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="719ca-107">Edge</span></span>|
|<span data-ttu-id="719ca-108">버전</span><span class="sxs-lookup"><span data-stu-id="719ca-108">Version</span></span>|<span data-ttu-id="719ca-109">4.5</span><span class="sxs-lookup"><span data-stu-id="719ca-109">4.5</span></span>|
|<span data-ttu-id="719ca-110">형식</span><span class="sxs-lookup"><span data-stu-id="719ca-110">Type</span></span>|<span data-ttu-id="719ca-111">런타임</span><span class="sxs-lookup"><span data-stu-id="719ca-111">Runtime</span></span>|
