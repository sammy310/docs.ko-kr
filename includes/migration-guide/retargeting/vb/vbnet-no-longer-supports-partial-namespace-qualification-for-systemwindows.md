---
ms.openlocfilehash: cef8096c971da8ae245ff974697022f350cb9195
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616075"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a><span data-ttu-id="ccc28-101">VB.NET가 System.Windows API에 대한 부분 네임스페이스 한정을 더 이상 지원하지 않음</span><span class="sxs-lookup"><span data-stu-id="ccc28-101">VB.NET no longer supports partial namespace qualification for System.Windows APIs</span></span>

#### <a name="details"></a><span data-ttu-id="ccc28-102">설명</span><span class="sxs-lookup"><span data-stu-id="ccc28-102">Details</span></span>

<span data-ttu-id="ccc28-103">.NET Framework 4.5.2부터 VB.NET 프로젝트는 부분적으로 정규화된 네임스페이스를 사용하는 System.Windows API를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ccc28-103">Beginning in .NET Framework 4.5.2, VB.NET projects cannot specify System.Windows APIs with partially-qualified namespaces.</span></span> <span data-ttu-id="ccc28-104">예를 들어 `Windows.Forms.DialogResult`를 참조하면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="ccc28-104">For example, referring to `Windows.Forms.DialogResult` will fail.</span></span> <span data-ttu-id="ccc28-105">대신, 코드는 정규화된 이름(<xref:System.Windows.Forms.DialogResult>)을 참조하거나 특정 네임스페이스를 가져오고 간단히 <xref:System.Windows.Forms.DialogResult?displayProperty=fullName>를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccc28-105">Instead, code must refer to the fully qualified name (<xref:System.Windows.Forms.DialogResult>) or import the specific namespace and refer simply to <xref:System.Windows.Forms.DialogResult?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ccc28-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="ccc28-106">Suggestion</span></span>

<span data-ttu-id="ccc28-107">코드는 간단한 이름(및 관련 네임스페이스를 가져오는) 또는 정규화된 이름을 사용하는 `System.Windows` API를 참조하도록 업데이트되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccc28-107">Code should be updated to refer to `System.Windows` APIs either with simple names (and importing the relevant namespace) or with fully qualified names.</span></span>

| <span data-ttu-id="ccc28-108">이름</span><span class="sxs-lookup"><span data-stu-id="ccc28-108">Name</span></span>    | <span data-ttu-id="ccc28-109">값</span><span class="sxs-lookup"><span data-stu-id="ccc28-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ccc28-110">Scope</span><span class="sxs-lookup"><span data-stu-id="ccc28-110">Scope</span></span>   | <span data-ttu-id="ccc28-111">부</span><span class="sxs-lookup"><span data-stu-id="ccc28-111">Minor</span></span>       |
| <span data-ttu-id="ccc28-112">버전</span><span class="sxs-lookup"><span data-stu-id="ccc28-112">Version</span></span> | <span data-ttu-id="ccc28-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="ccc28-113">4.5.2</span></span>       |
| <span data-ttu-id="ccc28-114">형식</span><span class="sxs-lookup"><span data-stu-id="ccc28-114">Type</span></span>    | <span data-ttu-id="ccc28-115">대상 변경</span><span class="sxs-lookup"><span data-stu-id="ccc28-115">Retargeting</span></span> |
