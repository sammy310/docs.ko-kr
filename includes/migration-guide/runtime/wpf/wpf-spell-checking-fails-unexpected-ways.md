---
ms.openlocfilehash: d4e60f2a59980263916718ebcc71cc359952c031
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497520"
---
### <a name="wpf-spell-checking-fails-in-unexpected-ways"></a><span data-ttu-id="935ad-101">예기치 않은 방식으로 WPF 맞춤법 검사가 실패</span><span class="sxs-lookup"><span data-stu-id="935ad-101">WPF Spell Checking fails in unexpected ways</span></span>

#### <a name="details"></a><span data-ttu-id="935ad-102">설명</span><span class="sxs-lookup"><span data-stu-id="935ad-102">Details</span></span>

<span data-ttu-id="935ad-103">여기에는 WPF 맞춤법 검사기의 여러 문제가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="935ad-103">This includes a number of WPF Spell Checker issues:</span></span><ul><li><span data-ttu-id="935ad-104">WPF 맞춤법 검사기가 때때로 <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName>을 throw</span><span class="sxs-lookup"><span data-stu-id="935ad-104">WPF Spell Checker sometimes throws <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName></span></span></li><li><span data-ttu-id="935ad-105">'다른 사용자로 실행'을 사용하여 애플리케이션을 시작하면 WPF 맞춤법 검사기가 <xref:System.UnauthorizedAccessException>과 함께 실패</span><span class="sxs-lookup"><span data-stu-id="935ad-105">WPF Spell Checker fails with <xref:System.UnauthorizedAccessException> when applications are launched using 'run as different user'</span></span></li><li><span data-ttu-id="935ad-106">WPF 맞춤법 검사기가 독일어의 'Hausnummer'와 같은 복합어의 맞춤법 오류를 잘못 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="935ad-106">WPF Spell Checker incorrectly identifies spelling errors in compound words like 'Hausnummer' in German.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="935ad-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="935ad-107">Suggestion</span></span>

<span data-ttu-id="935ad-108">문제 #1 - .NET Framework 4.6.2에서 해결되었습니다. 문제 #2 - '다른 사용자로 실행'을 사용하여 애플리케이션을 시작할 때 WPF 맞춤법 검사기가 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="935ad-108">Issue #1 - This has been fixed in .NET Framework 4.6.2 Issue #2 - WPF Spell Checker is no longer supported when applications are launched using 'run as different user'.</span></span> <span data-ttu-id="935ad-109">.NET Framework 4.6.2부터 이러한 방식으로 시작된 애플리케이션이 더 이상 예기치 않게 크래시되지 않습니다. - 대신 맞춤법 검사기가 자동으로 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="935ad-109">Starting .NET Framework 4.6.2, applications launched in this manner will no longer crash unexpectedly - instead the Spell Checker will be silently disabled.</span></span> <span data-ttu-id="935ad-110">문제 #3 - .NET Framework 4.6.2에서 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="935ad-110">Issue #3 - This has been fixed in .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="935ad-111">이름</span><span class="sxs-lookup"><span data-stu-id="935ad-111">Name</span></span>    | <span data-ttu-id="935ad-112">값</span><span class="sxs-lookup"><span data-stu-id="935ad-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="935ad-113">Scope</span><span class="sxs-lookup"><span data-stu-id="935ad-113">Scope</span></span>   |<span data-ttu-id="935ad-114">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="935ad-114">Edge</span></span>|
|<span data-ttu-id="935ad-115">버전</span><span class="sxs-lookup"><span data-stu-id="935ad-115">Version</span></span>|<span data-ttu-id="935ad-116">4.6.1</span><span class="sxs-lookup"><span data-stu-id="935ad-116">4.6.1</span></span>|
|<span data-ttu-id="935ad-117">형식</span><span class="sxs-lookup"><span data-stu-id="935ad-117">Type</span></span>|<span data-ttu-id="935ad-118">런타임</span><span class="sxs-lookup"><span data-stu-id="935ad-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="935ad-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="935ad-119">Affected APIs</span></span>

<span data-ttu-id="935ad-120">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="935ad-120">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
