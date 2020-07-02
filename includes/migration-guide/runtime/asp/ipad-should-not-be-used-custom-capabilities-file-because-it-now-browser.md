---
ms.openlocfilehash: af10716fe5f4c07091e8605cdf620e4a499fb1e8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620181"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a><span data-ttu-id="47dce-101">이제 iPad는 브라우저 기능이므로 사용자 지정 기능 파일에서 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47dce-101">IPad should not be used in custom capabilities file because it is now a browser capability</span></span>

#### <a name="details"></a><span data-ttu-id="47dce-102">설명</span><span class="sxs-lookup"><span data-stu-id="47dce-102">Details</span></span>

<span data-ttu-id="47dce-103">.NET Framework 4.5부터 iPad는 기본 ASP.NET 브라우저 기능 파일의 식별자이므로 사용자 지정 기능 파일에 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47dce-103">Beginning in .NET Framework 4.5, iPad is an identifier in the default ASP.NET browser capabilities file, so it should not be used in a custom capabilities file</span></span>

#### <a name="suggestion"></a><span data-ttu-id="47dce-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="47dce-104">Suggestion</span></span>

<span data-ttu-id="47dce-105">iPad 관련 기능이 필요한 경우, 사용자 에이전트 일치로 새로운 &quot;IPad&quot; ID를 생성하는 대신 사전 정의된 게이트웨이 refID &quot;IPad&quot;에서 기능을 설정하여 iPad 동작을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dce-105">If iPad-specific capabilities are required, it is necessary to modify iPad behavior by setting capabilities on the pre-defined gateway refID &quot;IPad&quot; instead of by generating a new &quot;IPad&quot; ID by user agent matching.</span></span>

| <span data-ttu-id="47dce-106">이름</span><span class="sxs-lookup"><span data-stu-id="47dce-106">Name</span></span>    | <span data-ttu-id="47dce-107">값</span><span class="sxs-lookup"><span data-stu-id="47dce-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="47dce-108">Scope</span><span class="sxs-lookup"><span data-stu-id="47dce-108">Scope</span></span>   |<span data-ttu-id="47dce-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="47dce-109">Edge</span></span>|
|<span data-ttu-id="47dce-110">버전</span><span class="sxs-lookup"><span data-stu-id="47dce-110">Version</span></span>|<span data-ttu-id="47dce-111">4.5</span><span class="sxs-lookup"><span data-stu-id="47dce-111">4.5</span></span>|
|<span data-ttu-id="47dce-112">형식</span><span class="sxs-lookup"><span data-stu-id="47dce-112">Type</span></span>|<span data-ttu-id="47dce-113">런타임</span><span class="sxs-lookup"><span data-stu-id="47dce-113">Runtime</span></span>|
