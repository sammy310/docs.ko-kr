---
ms.openlocfilehash: d00f86c492a7d32344b1067a48c8e53aa2a43426
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761334"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a><span data-ttu-id="eeae5-101">더 이상 리플렉션 개체를 관리 코드에서 out-of-process DCOM 클라이언트로 전달할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="eeae5-101">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients</span></span>

|   |   |
|---|---|
|<span data-ttu-id="eeae5-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="eeae5-102">Details</span></span>|<span data-ttu-id="eeae5-103">더이상 리플렉션 개체를 관리 코드에서 out-of-process DCOM 클라이언트로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eeae5-103">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients.</span></span> <span data-ttu-id="eeae5-104">다음 형식이 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="eeae5-104">The following types are affected:</span></span><ul><li><xref:System.Reflection.Assembly?displayProperty=name></li><li><span data-ttu-id="eeae5-105"><xref:System.Reflection.MemberInfo?displayProperty=name>(및 <xref:System.Reflection.FieldInfo?displayProperty=name>,<xref:System.Reflection.MethodInfo?displayProperty=name>,<xref:System.Type?displayProperty=name> 및 <xref:System.Reflection.TypeInfo?displayProperty=name>을 포함한 파생된 형식)</span><span class="sxs-lookup"><span data-stu-id="eeae5-105"><xref:System.Reflection.MemberInfo?displayProperty=name> (and its derived types, including <xref:System.Reflection.FieldInfo?displayProperty=name>, <xref:System.Reflection.MethodInfo?displayProperty=name>, <xref:System.Type?displayProperty=name>, and <xref:System.Reflection.TypeInfo?displayProperty=name>)</span></span></li><li><xref:System.Reflection.MethodBody?displayProperty=name></li><li><xref:System.Reflection.Module?displayProperty=name></li><li><span data-ttu-id="eeae5-106"><xref:System.Reflection.ParameterInfo?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="eeae5-106"><xref:System.Reflection.ParameterInfo?displayProperty=name>.</span></span></li></ul><span data-ttu-id="eeae5-107">개체에 대한 <code>IMarshal</code>을 호출하면 <code>E_NOINTERFACE</code>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="eeae5-107">Calls to <code>IMarshal</code> for the object return <code>E_NOINTERFACE</code>.</span></span>|
|<span data-ttu-id="eeae5-108">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="eeae5-108">Suggestion</span></span>|<span data-ttu-id="eeae5-109">마샬링 코드를 리플렉션이 아닌 개체를 사용하도록 업데이트</span><span class="sxs-lookup"><span data-stu-id="eeae5-109">Update marshaling code to work with non-reflection objects</span></span>|
|<span data-ttu-id="eeae5-110">범위</span><span class="sxs-lookup"><span data-stu-id="eeae5-110">Scope</span></span>|<span data-ttu-id="eeae5-111">부</span><span class="sxs-lookup"><span data-stu-id="eeae5-111">Minor</span></span>|
|<span data-ttu-id="eeae5-112">버전</span><span class="sxs-lookup"><span data-stu-id="eeae5-112">Version</span></span>|<span data-ttu-id="eeae5-113">4.6</span><span class="sxs-lookup"><span data-stu-id="eeae5-113">4.6</span></span>|
|<span data-ttu-id="eeae5-114">형식</span><span class="sxs-lookup"><span data-stu-id="eeae5-114">Type</span></span>|<span data-ttu-id="eeae5-115">런타임</span><span class="sxs-lookup"><span data-stu-id="eeae5-115">Runtime</span></span>|

