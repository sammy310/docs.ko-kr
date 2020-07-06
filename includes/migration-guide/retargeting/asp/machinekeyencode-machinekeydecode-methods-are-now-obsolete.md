---
ms.openlocfilehash: e9d34465970287ed94c0f0373ee4ae94d55aa1ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617180"
---
### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a><span data-ttu-id="9b6aa-101">MachineKey.Encode 및 MachineKey.Decode 메서드는 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="9b6aa-101">MachineKey.Encode and MachineKey.Decode methods are now obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="9b6aa-102">설명</span><span class="sxs-lookup"><span data-stu-id="9b6aa-102">Details</span></span>

<span data-ttu-id="9b6aa-103">이러한 메서드는 이제 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b6aa-103">These methods are now obsolete.</span></span> <span data-ttu-id="9b6aa-104">이러한 메서드를 호출하는 코드를 컴파일하면 컴파일러 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b6aa-104">Compilation of code that calls these methods produces a compiler warning.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9b6aa-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="9b6aa-105">Suggestion</span></span>

<span data-ttu-id="9b6aa-106"><xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> 및 <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>를 대신 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9b6aa-106">The recommended alternatives are <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> and <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span></span> <span data-ttu-id="9b6aa-107">또는 빌드 경고를 표시하지 않거나 이전 컴파일러를 사용하여 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b6aa-107">Alternatively, the build warnings can be suppressed, or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="9b6aa-108">API는 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b6aa-108">The APIs are still supported.</span></span>

| <span data-ttu-id="9b6aa-109">이름</span><span class="sxs-lookup"><span data-stu-id="9b6aa-109">Name</span></span>    | <span data-ttu-id="9b6aa-110">값</span><span class="sxs-lookup"><span data-stu-id="9b6aa-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9b6aa-111">Scope</span><span class="sxs-lookup"><span data-stu-id="9b6aa-111">Scope</span></span>   | <span data-ttu-id="9b6aa-112">부</span><span class="sxs-lookup"><span data-stu-id="9b6aa-112">Minor</span></span>       |
| <span data-ttu-id="9b6aa-113">버전</span><span class="sxs-lookup"><span data-stu-id="9b6aa-113">Version</span></span> | <span data-ttu-id="9b6aa-114">4.5</span><span class="sxs-lookup"><span data-stu-id="9b6aa-114">4.5</span></span>         |
| <span data-ttu-id="9b6aa-115">형식</span><span class="sxs-lookup"><span data-stu-id="9b6aa-115">Type</span></span>    | <span data-ttu-id="9b6aa-116">대상 변경</span><span class="sxs-lookup"><span data-stu-id="9b6aa-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="9b6aa-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="9b6aa-117">Affected APIs</span></span>

- <xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType>
- <xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType>
