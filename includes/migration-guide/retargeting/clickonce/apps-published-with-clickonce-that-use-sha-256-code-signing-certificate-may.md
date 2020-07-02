---
ms.openlocfilehash: 416590c7bd959eea011b7e7c5db48f22d349d0f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615660"
---
### <a name="apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a><span data-ttu-id="6ca97-101">SHA-256 코드 서명 인증서를 사용하는 ClickOnce로 게시된 앱이 Windows 2003에서 실패할 수 있음</span><span class="sxs-lookup"><span data-stu-id="6ca97-101">Apps published with ClickOnce that use a SHA-256 code-signing certificate may fail on Windows 2003</span></span>

#### <a name="details"></a><span data-ttu-id="6ca97-102">설명</span><span class="sxs-lookup"><span data-stu-id="6ca97-102">Details</span></span>

<span data-ttu-id="6ca97-103">실행 파일이 SHA256으로 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ca97-103">The executable is signed with SHA256.</span></span> <span data-ttu-id="6ca97-104">이전에는 코드 서명 인증서가 SHA-1 또는 SHA-256인지에 관계없이 SHA1로 서명되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca97-104">Previously, it was signed with SHA1 regardless of whether the code-signing certificate was SHA-1 or SHA-256.</span></span> <span data-ttu-id="6ca97-105">적용 대상:</span><span class="sxs-lookup"><span data-stu-id="6ca97-105">This applies to:</span></span>

- <span data-ttu-id="6ca97-106">Visual Studio 2012 이상으로 빌드된 모든 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="6ca97-106">All applications built with Visual Studio 2012 or later.</span></span>
- <span data-ttu-id="6ca97-107">.NET Framework 4.5가 있는 시스템에서 Visual Studio 2010 또는 이전 버전으로 빌드된 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="6ca97-107">Applications built with Visual Studio 2010 or earlier on systems with the .NET Framework 4.5 present.</span></span>
<span data-ttu-id="6ca97-108">또한 .NET Framework 4.5 이상이 있는 경우 컴파일 시의 대상 .NET Framework 버전에 관계없이 ClickOnce 매니페스트도 SHA-256 인증서에 대해 SHA-256으로 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ca97-108">In addition, if the .NET Framework 4.5 or later is present, the ClickOnce manifest is also signed with SHA-256 for SHA-256 certificates regardless of the .NET Framework version against which it was compiled.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6ca97-109">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="6ca97-109">Suggestion</span></span>

<span data-ttu-id="6ca97-110">ClickOnce 실행 파일의 서명 변경 내용은 Windows Server 2003 시스템에만 영향을 줍니다. KB 938397을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca97-110">The change in signing the ClickOnce executable affects only Windows Server 2003 systems; they require that KB 938397 be installed.</span></span> <span data-ttu-id="6ca97-111">앱이 .NET Framework 4.0 또는 이전 버전을 대상으로 하는 경우에도 SHA-256으로 매니페스트에 서명하는 변경 내용으로 인해 .NET Framework 4.5 이상 버전에서 런타임 종속성이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca97-111">The change in signing the manifest with SHA-256 even when an app targets the .NET Framework 4.0 or earlier versions introduces a runtime dependency on the .NET Framework 4.5 or a later version.</span></span>

| <span data-ttu-id="6ca97-112">이름</span><span class="sxs-lookup"><span data-stu-id="6ca97-112">Name</span></span>    | <span data-ttu-id="6ca97-113">값</span><span class="sxs-lookup"><span data-stu-id="6ca97-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6ca97-114">Scope</span><span class="sxs-lookup"><span data-stu-id="6ca97-114">Scope</span></span>   | <span data-ttu-id="6ca97-115">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6ca97-115">Edge</span></span>        |
| <span data-ttu-id="6ca97-116">버전</span><span class="sxs-lookup"><span data-stu-id="6ca97-116">Version</span></span> | <span data-ttu-id="6ca97-117">4.5</span><span class="sxs-lookup"><span data-stu-id="6ca97-117">4.5</span></span>         |
| <span data-ttu-id="6ca97-118">형식</span><span class="sxs-lookup"><span data-stu-id="6ca97-118">Type</span></span>    | <span data-ttu-id="6ca97-119">대상 변경</span><span class="sxs-lookup"><span data-stu-id="6ca97-119">Retargeting</span></span> |
