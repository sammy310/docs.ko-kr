---
ms.openlocfilehash: 83d3f24680531d1e447f047151a28c98ce0da04b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620399"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a><span data-ttu-id="54468-101">.NET Framework 1.1 및 2.0에서 관리되는 브라우저 호스팅 컨트롤이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="54468-101">Managed browser hosting controls from the .NET Framework 1.1 and 2.0 are blocked</span></span>

#### <a name="details"></a><span data-ttu-id="54468-102">설명</span><span class="sxs-lookup"><span data-stu-id="54468-102">Details</span></span>

<span data-ttu-id="54468-103">이러한 컨트롤의 호스팅은 Internet Explorer에서 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="54468-103">Hosting these controls is blocked in Internet Explorer.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="54468-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="54468-104">Suggestion</span></span>

<span data-ttu-id="54468-105">Internet Explorer에서는 관리되는 브라우저 호스팅 컨트롤을 사용하는 애플리케이션을 시작하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="54468-105">Internet Explorer will fail to launch an application that uses managed browser hosting controls.</span></span> <span data-ttu-id="54468-106">x86 시스템 및 x64 시스템의 32비트 프로세스의 경우 레지스트리 하위 키 <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code>의 EnableIEHosting 값을 <code>1</code>로 설정하고, x64 시스템의 64비트 프로세스의 경우 레지스트리 하위 키 <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code>의 <code>EnableIEHosting</code> 값을 <code>1</code>로 설정하여 이전 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54468-106">The previous behavior can be restored by setting the EnableIEHosting value of the registry subkey <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> to <code>1</code> for x86 systems and for 32-bit processes on x64 systems, and by setting the <code>EnableIEHosting</code> value of the registry subkey <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> to <code>1</code> for 64-bit processes on x64 systems.</span></span>

| <span data-ttu-id="54468-107">이름</span><span class="sxs-lookup"><span data-stu-id="54468-107">Name</span></span>    | <span data-ttu-id="54468-108">값</span><span class="sxs-lookup"><span data-stu-id="54468-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="54468-109">Scope</span><span class="sxs-lookup"><span data-stu-id="54468-109">Scope</span></span>   |<span data-ttu-id="54468-110">부</span><span class="sxs-lookup"><span data-stu-id="54468-110">Minor</span></span>|
|<span data-ttu-id="54468-111">버전</span><span class="sxs-lookup"><span data-stu-id="54468-111">Version</span></span>|<span data-ttu-id="54468-112">4.5</span><span class="sxs-lookup"><span data-stu-id="54468-112">4.5</span></span>|
|<span data-ttu-id="54468-113">형식</span><span class="sxs-lookup"><span data-stu-id="54468-113">Type</span></span>|<span data-ttu-id="54468-114">런타임</span><span class="sxs-lookup"><span data-stu-id="54468-114">Runtime</span></span>|
