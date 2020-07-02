---
ms.openlocfilehash: ed526095459a48aa37b585dfed79cc12b9fb9e56
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622138"
---
### <a name="some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a><span data-ttu-id="5fc51-101">일부 .NET API는 첫 번째 기회(처리) EntryPointNotFoundExceptions의 원인</span><span class="sxs-lookup"><span data-stu-id="5fc51-101">Some .NET APIs cause first chance (handled) EntryPointNotFoundExceptions</span></span>

#### <a name="details"></a><span data-ttu-id="5fc51-102">설명</span><span class="sxs-lookup"><span data-stu-id="5fc51-102">Details</span></span>

<span data-ttu-id="5fc51-103">.NET Framework 4.5에서 소수의 .NET 메서드가 첫 번째 기회 <xref:System.EntryPointNotFoundException?displayProperty=fullName>을 throw하기 시작했습니다.</span><span class="sxs-lookup"><span data-stu-id="5fc51-103">In the .NET Framework 4.5, a small number of .NET methods began throwing first chance <xref:System.EntryPointNotFoundException?displayProperty=fullName>s.</span></span> <span data-ttu-id="5fc51-104">이러한 예외는 .NET Framework 내에서 처리되지만 첫 번째 예외를 예상하지 않은 테스트 자동화를 중단시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fc51-104">These exceptions were handled within the .NET Framework, but could break test automation that did not expect the first chance exceptions.</span></span> <span data-ttu-id="5fc51-105">이러한 동일 API는 HighVersionLie를 사용하는 경우 일부 ApiVerifier 시나리오를 중단시킵니다.</span><span class="sxs-lookup"><span data-stu-id="5fc51-105">These same APIs break some ApiVerifier scenarios when HighVersionLie is enabled.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5fc51-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="5fc51-106">Suggestion</span></span>

<span data-ttu-id="5fc51-107">.NET Framework 4.5.1로 업그레이드하여 이 버그를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fc51-107">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="5fc51-108">또는 첫 번째 기회 <xref:System.EntryPointNotFoundException?displayProperty=fullName>에서 문제가 발생하지 않도록 테스트 자동화를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fc51-108">Alternatively, test automation can be updated to not break on first-chance <xref:System.EntryPointNotFoundException?displayProperty=fullName>s.</span></span>

| <span data-ttu-id="5fc51-109">이름</span><span class="sxs-lookup"><span data-stu-id="5fc51-109">Name</span></span>    | <span data-ttu-id="5fc51-110">값</span><span class="sxs-lookup"><span data-stu-id="5fc51-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5fc51-111">Scope</span><span class="sxs-lookup"><span data-stu-id="5fc51-111">Scope</span></span>   |<span data-ttu-id="5fc51-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5fc51-112">Edge</span></span>|
|<span data-ttu-id="5fc51-113">버전</span><span class="sxs-lookup"><span data-stu-id="5fc51-113">Version</span></span>|<span data-ttu-id="5fc51-114">4.5</span><span class="sxs-lookup"><span data-stu-id="5fc51-114">4.5</span></span>|
|<span data-ttu-id="5fc51-115">형식</span><span class="sxs-lookup"><span data-stu-id="5fc51-115">Type</span></span>|<span data-ttu-id="5fc51-116">런타임</span><span class="sxs-lookup"><span data-stu-id="5fc51-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5fc51-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="5fc51-117">Affected APIs</span></span>

-<xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)></li></ul>|
