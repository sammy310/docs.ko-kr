---
ms.openlocfilehash: 9bf6972812bdf4a385b99fe34d2cd3cd8a91c8cf
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761096"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a><span data-ttu-id="8842e-101">ClickOnce가 4.0 대상 앱에서 SHA-256 지원</span><span class="sxs-lookup"><span data-stu-id="8842e-101">ClickOnce supports SHA-256 on 4.0-targeted apps</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8842e-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="8842e-102">Details</span></span>|<span data-ttu-id="8842e-103">이전에 SHA-256으로 서명된 인증서가 있는 ClickOnce 앱은 앱이 4.0을 대상으로 하더라도 .NET Framework 4.5 이상이 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="8842e-103">Previously, a ClickOnce app with a certificate signed with SHA-256 would require .NET Framework 4.5 or later to be present, even if the app targeted 4.0.</span></span> <span data-ttu-id="8842e-104">이제 .NET Framework 4.0을 대상으로 하는 ClickOnce 앱을 SHA-256으로 서명한 경우에도 .NET Framework 4.0에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8842e-104">Now, .NET Framework 4.0-targeted ClickOnce apps can run on .NET Framework 4.0, even if signed with SHA-256.</span></span>|
|<span data-ttu-id="8842e-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="8842e-105">Suggestion</span></span>|<span data-ttu-id="8842e-106">이 변경 내용은 해당 종속성을 제거하고 .NET Framework 4 이전 버전을 대상으로 하는 ClickOnce 앱을 SHA-256 인증서로 서명할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="8842e-106">This change removes that dependency and allows SHA-256 certificates to be used to sign ClickOnce apps that target .NET Framework 4 and earlier versions.</span></span>|
|<span data-ttu-id="8842e-107">범위</span><span class="sxs-lookup"><span data-stu-id="8842e-107">Scope</span></span>|<span data-ttu-id="8842e-108">부</span><span class="sxs-lookup"><span data-stu-id="8842e-108">Minor</span></span>|
|<span data-ttu-id="8842e-109">버전</span><span class="sxs-lookup"><span data-stu-id="8842e-109">Version</span></span>|<span data-ttu-id="8842e-110">4.6</span><span class="sxs-lookup"><span data-stu-id="8842e-110">4.6</span></span>|
|<span data-ttu-id="8842e-111">형식</span><span class="sxs-lookup"><span data-stu-id="8842e-111">Type</span></span>|<span data-ttu-id="8842e-112">대상 변경</span><span class="sxs-lookup"><span data-stu-id="8842e-112">Retargeting</span></span>|

