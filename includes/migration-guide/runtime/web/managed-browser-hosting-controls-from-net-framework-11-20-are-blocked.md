---
ms.openlocfilehash: 26539011f0650c7a3bac9e1c41847561905fff58
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496657"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a><span data-ttu-id="2fbd1-101">.NET Framework 1.1 및 2.0에서 관리되는 브라우저 호스팅 컨트롤이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fbd1-101">Managed browser hosting controls from the .NET Framework 1.1 and 2.0 are blocked</span></span>

#### <a name="details"></a><span data-ttu-id="2fbd1-102">설명</span><span class="sxs-lookup"><span data-stu-id="2fbd1-102">Details</span></span>

<span data-ttu-id="2fbd1-103">이러한 컨트롤의 호스팅은 Internet Explorer에서 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fbd1-103">Hosting these controls is blocked in Internet Explorer.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2fbd1-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="2fbd1-104">Suggestion</span></span>

<span data-ttu-id="2fbd1-105">Internet Explorer에서는 관리되는 브라우저 호스팅 컨트롤을 사용하는 애플리케이션을 시작하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="2fbd1-105">Internet Explorer will fail to launch an application that uses managed browser hosting controls.</span></span> <span data-ttu-id="2fbd1-106">x86 시스템 및 x64 시스템의 32비트 프로세스의 경우 레지스트리 하위 키 <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code>의 EnableIEHosting 값을 <code>1</code>로 설정하고, x64 시스템의 64비트 프로세스의 경우 레지스트리 하위 키 <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code>의 <code>EnableIEHosting</code> 값을 <code>1</code>로 설정하여 이전 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fbd1-106">The previous behavior can be restored by setting the EnableIEHosting value of the registry subkey <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> to <code>1</code> for x86 systems and for 32-bit processes on x64 systems, and by setting the <code>EnableIEHosting</code> value of the registry subkey <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> to <code>1</code> for 64-bit processes on x64 systems.</span></span>

| <span data-ttu-id="2fbd1-107">이름</span><span class="sxs-lookup"><span data-stu-id="2fbd1-107">Name</span></span>    | <span data-ttu-id="2fbd1-108">값</span><span class="sxs-lookup"><span data-stu-id="2fbd1-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2fbd1-109">Scope</span><span class="sxs-lookup"><span data-stu-id="2fbd1-109">Scope</span></span>   |<span data-ttu-id="2fbd1-110">부</span><span class="sxs-lookup"><span data-stu-id="2fbd1-110">Minor</span></span>|
|<span data-ttu-id="2fbd1-111">버전</span><span class="sxs-lookup"><span data-stu-id="2fbd1-111">Version</span></span>|<span data-ttu-id="2fbd1-112">4.5</span><span class="sxs-lookup"><span data-stu-id="2fbd1-112">4.5</span></span>|
|<span data-ttu-id="2fbd1-113">형식</span><span class="sxs-lookup"><span data-stu-id="2fbd1-113">Type</span></span>|<span data-ttu-id="2fbd1-114">런타임</span><span class="sxs-lookup"><span data-stu-id="2fbd1-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="2fbd1-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="2fbd1-115">Affected APIs</span></span>

<span data-ttu-id="2fbd1-116">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2fbd1-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
