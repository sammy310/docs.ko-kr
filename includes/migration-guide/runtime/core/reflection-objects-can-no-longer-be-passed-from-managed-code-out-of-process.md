---
ms.openlocfilehash: a54b17b2002bd0f85b8b47c5e37e040470d6c494
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621333"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a><span data-ttu-id="8c133-101">더 이상 리플렉션 개체를 관리 코드에서 out-of-process DCOM 클라이언트로 전달할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="8c133-101">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients</span></span>

#### <a name="details"></a><span data-ttu-id="8c133-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="8c133-102">Details</span></span>

<span data-ttu-id="8c133-103">더이상 리플렉션 개체를 관리 코드에서 out-of-process DCOM 클라이언트로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c133-103">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients.</span></span> <span data-ttu-id="8c133-104">다음 형식이 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8c133-104">The following types are affected:</span></span><ul><li><xref:System.Reflection.Assembly?displayProperty=fullName></li><li><span data-ttu-id="8c133-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName>(및 <xref:System.Reflection.FieldInfo?displayProperty=fullName>,<xref:System.Reflection.MethodInfo?displayProperty=fullName>,<xref:System.Type?displayProperty=fullName> 및 <xref:System.Reflection.TypeInfo?displayProperty=fullName>을 포함한 파생된 형식)</span><span class="sxs-lookup"><span data-stu-id="8c133-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (and its derived types, including <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName>, and <xref:System.Reflection.TypeInfo?displayProperty=fullName>)</span></span></li><li><xref:System.Reflection.MethodBody?displayProperty=fullName></li><li><xref:System.Reflection.Module?displayProperty=fullName></li><li><span data-ttu-id="8c133-106"><xref:System.Reflection.ParameterInfo?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="8c133-106"><xref:System.Reflection.ParameterInfo?displayProperty=fullName>.</span></span></li></ul><span data-ttu-id="8c133-107">개체에 대한 <code>IMarshal</code>을 호출하면 <code>E_NOINTERFACE</code>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8c133-107">Calls to <code>IMarshal</code> for the object return <code>E_NOINTERFACE</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8c133-108">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="8c133-108">Suggestion</span></span>

<span data-ttu-id="8c133-109">마샬링 코드를 리플렉션이 아닌 개체를 사용하도록 업데이트</span><span class="sxs-lookup"><span data-stu-id="8c133-109">Update marshaling code to work with non-reflection objects</span></span>

| <span data-ttu-id="8c133-110">이름</span><span class="sxs-lookup"><span data-stu-id="8c133-110">Name</span></span>    | <span data-ttu-id="8c133-111">값</span><span class="sxs-lookup"><span data-stu-id="8c133-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8c133-112">Scope</span><span class="sxs-lookup"><span data-stu-id="8c133-112">Scope</span></span>   |<span data-ttu-id="8c133-113">부</span><span class="sxs-lookup"><span data-stu-id="8c133-113">Minor</span></span>|
|<span data-ttu-id="8c133-114">버전</span><span class="sxs-lookup"><span data-stu-id="8c133-114">Version</span></span>|<span data-ttu-id="8c133-115">4.6</span><span class="sxs-lookup"><span data-stu-id="8c133-115">4.6</span></span>|
|<span data-ttu-id="8c133-116">형식</span><span class="sxs-lookup"><span data-stu-id="8c133-116">Type</span></span>|<span data-ttu-id="8c133-117">런타임</span><span class="sxs-lookup"><span data-stu-id="8c133-117">Runtime</span></span>|
