---
ms.openlocfilehash: c967a5b09b5e9ffeee7bff046f0c96469bc7fb02
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615656"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a><span data-ttu-id="3c314-101">ClickOnce가 4.0 대상 앱에서 SHA-256 지원</span><span class="sxs-lookup"><span data-stu-id="3c314-101">ClickOnce supports SHA-256 on 4.0-targeted apps</span></span>

#### <a name="details"></a><span data-ttu-id="3c314-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="3c314-102">Details</span></span>

<span data-ttu-id="3c314-103">이전에 SHA-256으로 서명된 인증서가 있는 ClickOnce 앱은 앱이 4.0을 대상으로 하더라도 .NET Framework 4.5 이상이 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="3c314-103">Previously, a ClickOnce app with a certificate signed with SHA-256 would require .NET Framework 4.5 or later to be present, even if the app targeted 4.0.</span></span> <span data-ttu-id="3c314-104">이제 .NET Framework 4.0을 대상으로 하는 ClickOnce 앱을 SHA-256으로 서명한 경우에도 .NET Framework 4.0에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c314-104">Now, .NET Framework 4.0-targeted ClickOnce apps can run on .NET Framework 4.0, even if signed with SHA-256.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3c314-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="3c314-105">Suggestion</span></span>

<span data-ttu-id="3c314-106">이 변경 내용은 해당 종속성을 제거하고 .NET Framework 4 이전 버전을 대상으로 하는 ClickOnce 앱을 SHA-256 인증서로 서명할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c314-106">This change removes that dependency and allows SHA-256 certificates to be used to sign ClickOnce apps that target .NET Framework 4 and earlier versions.</span></span>

| <span data-ttu-id="3c314-107">이름</span><span class="sxs-lookup"><span data-stu-id="3c314-107">Name</span></span>    | <span data-ttu-id="3c314-108">값</span><span class="sxs-lookup"><span data-stu-id="3c314-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3c314-109">Scope</span><span class="sxs-lookup"><span data-stu-id="3c314-109">Scope</span></span>   | <span data-ttu-id="3c314-110">부</span><span class="sxs-lookup"><span data-stu-id="3c314-110">Minor</span></span>       |
| <span data-ttu-id="3c314-111">버전</span><span class="sxs-lookup"><span data-stu-id="3c314-111">Version</span></span> | <span data-ttu-id="3c314-112">4.6</span><span class="sxs-lookup"><span data-stu-id="3c314-112">4.6</span></span>         |
| <span data-ttu-id="3c314-113">형식</span><span class="sxs-lookup"><span data-stu-id="3c314-113">Type</span></span>    | <span data-ttu-id="3c314-114">대상 변경</span><span class="sxs-lookup"><span data-stu-id="3c314-114">Retargeting</span></span> |
