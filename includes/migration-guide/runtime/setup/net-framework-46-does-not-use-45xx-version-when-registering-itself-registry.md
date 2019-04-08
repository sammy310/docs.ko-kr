---
ms.openlocfilehash: 08c16f261338148619de2e484c73046b9d9a6bfe
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761394"
---
### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a><span data-ttu-id="ae4bd-101">.NET Framework 4.6은 레지스트리에 등록될 때 4.5.x.x 버전을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae4bd-101">The .NET Framework 4.6 does not use a 4.5.x.x version when registering itself in the registry</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ae4bd-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="ae4bd-102">Details</span></span>|<span data-ttu-id="ae4bd-103">예상할 수 있듯이 .NET Framework 4.6의 레지스트리(<code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>)에 설정된 버전 키는 '4.5'가 아니라 '4.6'으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4bd-103">As one might expect, the version key set in the registry (at <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) for the .NET Framework 4.6 begins with '4.6', not '4.5'.</span></span> <span data-ttu-id="ae4bd-104">이러한 레지스트리 키를 사용하여 컴퓨터에 설치된 .NET Framework 버전을 확인하는 앱은 4.6이 가능한 새 버전이고 이전 4.5.x 릴리스와 호환된다는 것을 이해하도록 업데이트되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4bd-104">Apps that depend on these registry keys to know which .NET Framework versions are installed on a machine should be updated to understand that 4.6 is a new possible version, and one that is compatible with previous 4.5.x releases.</span></span>|
|<span data-ttu-id="ae4bd-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="ae4bd-105">Suggestion</span></span>|<span data-ttu-id="ae4bd-106">4.5 레지스트리 키를 검색하여 4.6을 수락하도록 .NET Framework 4.5 설치를 검색하는 앱을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4bd-106">Update apps probing for a .NET Framework 4.5 install by looking for 4.5 registry keys to also accept 4.6.</span></span>|
|<span data-ttu-id="ae4bd-107">범위</span><span class="sxs-lookup"><span data-stu-id="ae4bd-107">Scope</span></span>|<span data-ttu-id="ae4bd-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ae4bd-108">Edge</span></span>|
|<span data-ttu-id="ae4bd-109">버전</span><span class="sxs-lookup"><span data-stu-id="ae4bd-109">Version</span></span>|<span data-ttu-id="ae4bd-110">4.6</span><span class="sxs-lookup"><span data-stu-id="ae4bd-110">4.6</span></span>|
|<span data-ttu-id="ae4bd-111">형식</span><span class="sxs-lookup"><span data-stu-id="ae4bd-111">Type</span></span>|<span data-ttu-id="ae4bd-112">런타임</span><span class="sxs-lookup"><span data-stu-id="ae4bd-112">Runtime</span></span>|

