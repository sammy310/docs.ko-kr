---
ms.openlocfilehash: e42bce91afab68e509cb35a8992fa3ca2f096872
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496198"
---
### <a name="wpf-printing-stack-update"></a><span data-ttu-id="36ee5-101">WPF 인쇄 스택 업데이트</span><span class="sxs-lookup"><span data-stu-id="36ee5-101">WPF Printing Stack Update</span></span>

#### <a name="details"></a><span data-ttu-id="36ee5-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="36ee5-102">Details</span></span>

<span data-ttu-id="36ee5-103">이제 <xref:System.Printing.PrintQueue?displayProperty=fullName>을 사용하는 WPF 인쇄 API는 사용되지 않는 XPS 인쇄 API 대신 Windows의 인쇄 문서 패키지 API를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="36ee5-103">WPF's Printing APIs using <xref:System.Printing.PrintQueue?displayProperty=fullName> now call Window's Print Document Package API in favor of the now deprecated XPS Print API.</span></span> <span data-ttu-id="36ee5-104">서비스 효율성이 변경됩니다. 사용자와 개발자 모두 동작이나 API 사용에서 달라진 내용을 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36ee5-104">The change was made with serviceability in mind; neither users nor developers should see any changes in behavior or API usage.</span></span> <span data-ttu-id="36ee5-105">Windows 10 크리에이터스 업데이트에서 실행될 때 기본적으로 새로운 인쇄 스택을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="36ee5-105">The new printing stack is enabled by default when running in Windows 10 Creators Update.</span></span> <span data-ttu-id="36ee5-106">이전 인쇄 스택은 이전 Windows 버전에서처럼 계속 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="36ee5-106">The old printing stack will still continue to work just as before in older Windows versions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="36ee5-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="36ee5-107">Suggestion</span></span>

<span data-ttu-id="36ee5-108">Windows 10 크리에이터스 업데이트에서 이전 스택을 사용하려면 <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> 레지스트리 키의 <code>UseXpsOMPrinting</code> REG_DWORD 값을 <code>1</code>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="36ee5-108">To use the old stack in Windows 10 Creators Update, set the <code>UseXpsOMPrinting</code> REG_DWORD value of the <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> registry key to <code>1</code>.</span></span>

| <span data-ttu-id="36ee5-109">Name</span><span class="sxs-lookup"><span data-stu-id="36ee5-109">Name</span></span>    | <span data-ttu-id="36ee5-110">값</span><span class="sxs-lookup"><span data-stu-id="36ee5-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="36ee5-111">Scope</span><span class="sxs-lookup"><span data-stu-id="36ee5-111">Scope</span></span>   |<span data-ttu-id="36ee5-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="36ee5-112">Edge</span></span>|
|<span data-ttu-id="36ee5-113">버전</span><span class="sxs-lookup"><span data-stu-id="36ee5-113">Version</span></span>|<span data-ttu-id="36ee5-114">4.7</span><span class="sxs-lookup"><span data-stu-id="36ee5-114">4.7</span></span>|
|<span data-ttu-id="36ee5-115">형식</span><span class="sxs-lookup"><span data-stu-id="36ee5-115">Type</span></span>|<span data-ttu-id="36ee5-116">런타임</span><span class="sxs-lookup"><span data-stu-id="36ee5-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="36ee5-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="36ee5-117">Affected APIs</span></span>

<span data-ttu-id="36ee5-118">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36ee5-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
