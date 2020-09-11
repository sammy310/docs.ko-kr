---
ms.openlocfilehash: f011f6ebe0fa85a59f3e69c93bba9eddc4c1689b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496908"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a><span data-ttu-id="728a4-101">더 이상 리플렉션 개체를 관리 코드에서 out-of-process DCOM 클라이언트로 전달할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="728a4-101">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients</span></span>

#### <a name="details"></a><span data-ttu-id="728a4-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="728a4-102">Details</span></span>

<span data-ttu-id="728a4-103">더이상 리플렉션 개체를 관리 코드에서 out-of-process DCOM 클라이언트로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="728a4-103">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients.</span></span> <span data-ttu-id="728a4-104">다음 형식이 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="728a4-104">The following types are affected:</span></span>

- <xref:System.Reflection.Assembly?displayProperty=fullName>
- <span data-ttu-id="728a4-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName>(및 <xref:System.Reflection.FieldInfo?displayProperty=fullName>,<xref:System.Reflection.MethodInfo?displayProperty=fullName>,<xref:System.Type?displayProperty=fullName> 및 <xref:System.Reflection.TypeInfo?displayProperty=fullName>을 포함한 파생된 형식)</span><span class="sxs-lookup"><span data-stu-id="728a4-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (and its derived types, including <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName>, and <xref:System.Reflection.TypeInfo?displayProperty=fullName>)</span></span>
- <xref:System.Reflection.MethodBody?displayProperty=fullName>
- <xref:System.Reflection.Module?displayProperty=fullName>
- <xref:System.Reflection.ParameterInfo?displayProperty=fullName>

<span data-ttu-id="728a4-106">개체에 대한 <code>IMarshal</code>을 호출하면 <code>E_NOINTERFACE</code>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="728a4-106">Calls to <code>IMarshal</code> for the object return <code>E_NOINTERFACE</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="728a4-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="728a4-107">Suggestion</span></span>

<span data-ttu-id="728a4-108">비리플렉션 개체에서 작동하도록 마샬링 코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="728a4-108">Update marshaling code to work with non-reflection objects.</span></span>

| <span data-ttu-id="728a4-109">Name</span><span class="sxs-lookup"><span data-stu-id="728a4-109">Name</span></span>    | <span data-ttu-id="728a4-110">값</span><span class="sxs-lookup"><span data-stu-id="728a4-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="728a4-111">Scope</span><span class="sxs-lookup"><span data-stu-id="728a4-111">Scope</span></span>   |<span data-ttu-id="728a4-112">부</span><span class="sxs-lookup"><span data-stu-id="728a4-112">Minor</span></span>|
|<span data-ttu-id="728a4-113">버전</span><span class="sxs-lookup"><span data-stu-id="728a4-113">Version</span></span>|<span data-ttu-id="728a4-114">4.6</span><span class="sxs-lookup"><span data-stu-id="728a4-114">4.6</span></span>|
|<span data-ttu-id="728a4-115">형식</span><span class="sxs-lookup"><span data-stu-id="728a4-115">Type</span></span>|<span data-ttu-id="728a4-116">런타임</span><span class="sxs-lookup"><span data-stu-id="728a4-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="728a4-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="728a4-117">Affected APIs</span></span>

- <xref:System.Reflection.Assembly?displayProperty=fullName>
- <xref:System.Reflection.FieldInfo?displayProperty=fullName>
- <xref:System.Reflection.MemberInfo?displayProperty=fullName>
- <xref:System.Reflection.MethodBody?displayProperty=fullName>
- <xref:System.Reflection.MethodInfo?displayProperty=fullName>
- <xref:System.Reflection.Module?displayProperty=fullName>
- <xref:System.Reflection.ParameterInfo?displayProperty=fullName>
- <xref:System.Reflection.TypeInfo?displayProperty=fullName>
- <xref:System.Type?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Reflection.Assembly`
- `T:System.Reflection.FieldInfo`
- `T:System.Reflection.MemberInfo`
- `T:System.Reflection.MethodBody`
- `T:System.Reflection.MethodInfo`
- `T:System.Reflection.Module`
- `T:System.Reflection.ParameterInfo`
- `T:System.Reflection.TypeInfo`
- `T:System.Type`

-->
