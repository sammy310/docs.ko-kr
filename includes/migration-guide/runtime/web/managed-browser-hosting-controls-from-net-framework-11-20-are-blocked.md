---
ms.openlocfilehash: 38c35f3f6f2262d06409690d2326d9b982e1ec86
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235772"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a><span data-ttu-id="a643d-101">.NET Framework 1.1 및 2.0에서 관리되는 브라우저 호스팅 컨트롤이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="a643d-101">Managed browser hosting controls from the .NET Framework 1.1 and 2.0 are blocked</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a643d-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="a643d-102">Details</span></span>|<span data-ttu-id="a643d-103">이러한 컨트롤의 호스팅은 Internet Explorer에서 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="a643d-103">Hosting these controls is blocked in Internet Explorer.</span></span>|
|<span data-ttu-id="a643d-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="a643d-104">Suggestion</span></span>|<span data-ttu-id="a643d-105">Internet Explorer에서는 관리되는 브라우저 호스팅 컨트롤을 사용하는 애플리케이션을 시작하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="a643d-105">Internet Explorer will fail to launch an application that uses managed browser hosting controls.</span></span> <span data-ttu-id="a643d-106">x86 시스템 및 x64 시스템의 32비트 프로세스의 경우 레지스트리 하위 키 <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code>의 EnableIEHosting 값을 <code>1</code>로 설정하고, x64 시스템의 64비트 프로세스의 경우 레지스트리 하위 키 <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code>의 <code>EnableIEHosting</code> 값을 <code>1</code>로 설정하여 이전 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a643d-106">The previous behavior can be restored by setting the EnableIEHosting value of the registry subkey <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> to <code>1</code> for x86 systems and for 32-bit processes on x64 systems, and by setting the <code>EnableIEHosting</code> value of the registry subkey <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> to <code>1</code> for 64-bit processes on x64 systems.</span></span>|
|<span data-ttu-id="a643d-107">범위</span><span class="sxs-lookup"><span data-stu-id="a643d-107">Scope</span></span>|<span data-ttu-id="a643d-108">부</span><span class="sxs-lookup"><span data-stu-id="a643d-108">Minor</span></span>|
|<span data-ttu-id="a643d-109">버전</span><span class="sxs-lookup"><span data-stu-id="a643d-109">Version</span></span>|<span data-ttu-id="a643d-110">4.5</span><span class="sxs-lookup"><span data-stu-id="a643d-110">4.5</span></span>|
|<span data-ttu-id="a643d-111">형식</span><span class="sxs-lookup"><span data-stu-id="a643d-111">Type</span></span>|<span data-ttu-id="a643d-112">런타임</span><span class="sxs-lookup"><span data-stu-id="a643d-112">Runtime</span></span>|
