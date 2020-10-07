---
ms.openlocfilehash: 53860bb867522503c5cb9bd35e25fadd00a116a2
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609165"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a><span data-ttu-id="6708b-101">AntiXSSEncoder를 사용할 때 여러 줄 ASP.NET TextBox 간격이 변경됨</span><span class="sxs-lookup"><span data-stu-id="6708b-101">Multi-line ASP.NET TextBox spacing changed when using AntiXSSEncoder</span></span>

#### <a name="details"></a><span data-ttu-id="6708b-102">설명</span><span class="sxs-lookup"><span data-stu-id="6708b-102">Details</span></span>

<span data-ttu-id="6708b-103">.NET Framework 4.0에서 <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName>을 사용하는 경우 추가 줄은 포스트백에서 여러 줄 텍스트 상자의 줄 사이에 삽입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6708b-103">In .NET Framework 4.0, extra lines were inserted between lines of a multi-line text box on postback, if using the <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName>.</span></span> <span data-ttu-id="6708b-104">.NET Framework 4.5에서는 웹 응용 프로그램이 .NET Framework 4.5를 대상으로 하는 경우를 제외하고 이러한 추가 줄 바꿈이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6708b-104">In .NET Framework 4.5, those extra line breaks are not included, but only if the web app is targeting .NET Framework 4.5</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6708b-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="6708b-105">Suggestion</span></span>

<span data-ttu-id="6708b-106">.NET Framework 4.5로 대상이 다시 지정된 4.0 웹 응용 프로그램에는 더 이상 추가 줄 바꿈을 삽입하지 않도록 개선된 여러 줄 텍스트 상자가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6708b-106">Be aware that 4.0 web apps retargeted to .NET Framework 4.5 may have multi-line text boxes improved to no longer insert extra line breaks.</span></span> <span data-ttu-id="6708b-107">이것이 필요 없는 경우 응용 프로그램은 .NET Framework 4.0을 대상으로 하여 .NET Framework 4.5에서 실행하는 경우 이전 동작을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6708b-107">If this is not desirable, the app  can have the old behavior when running on .NET Framework 4.5 by targeting the .NET Framework 4.0.</span></span>

| <span data-ttu-id="6708b-108">이름</span><span class="sxs-lookup"><span data-stu-id="6708b-108">Name</span></span>    | <span data-ttu-id="6708b-109">값</span><span class="sxs-lookup"><span data-stu-id="6708b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6708b-110">Scope</span><span class="sxs-lookup"><span data-stu-id="6708b-110">Scope</span></span>   | <span data-ttu-id="6708b-111">부</span><span class="sxs-lookup"><span data-stu-id="6708b-111">Minor</span></span>       |
| <span data-ttu-id="6708b-112">버전</span><span class="sxs-lookup"><span data-stu-id="6708b-112">Version</span></span> | <span data-ttu-id="6708b-113">4.5</span><span class="sxs-lookup"><span data-stu-id="6708b-113">4.5</span></span>         |
| <span data-ttu-id="6708b-114">형식</span><span class="sxs-lookup"><span data-stu-id="6708b-114">Type</span></span>    | <span data-ttu-id="6708b-115">대상 변경</span><span class="sxs-lookup"><span data-stu-id="6708b-115">Retargeting</span></span> |
