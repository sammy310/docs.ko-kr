---
ms.openlocfilehash: 086dac69d085d070511fcfd5820bd2644ee4598e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497953"
---
### <a name="marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a><span data-ttu-id="a76dc-101">Marshal.SizeOf와 Marshal.PtrToStructure 오버로드가 동적 코드를 중단시킵니다.</span><span class="sxs-lookup"><span data-stu-id="a76dc-101">Marshal.SizeOf and Marshal.PtrToStructure overloads break dynamic code</span></span>

#### <a name="details"></a><span data-ttu-id="a76dc-102">설명</span><span class="sxs-lookup"><span data-stu-id="a76dc-102">Details</span></span>

<span data-ttu-id="a76dc-103">.NET Framework 4.5.1부터 <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601>, <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601(%60%600)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Object)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Type)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr)> 또는 <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr,%60%600)> 메서드에 동적으로 바인딩하면(예: Windows PowerShell, IronPython 또는 C# dynamic 키워드를 통해) 이러한 메서드의 새 오버로드가 추가되어 스크립팅 엔진에 모호하게 될 수 있으므로 <code>MethodInvocationExceptions</code>를 발생시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a76dc-103">Beginning in the .NET Framework 4.5.1, dynamically binding to the methods <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601>, <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601(%60%600)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Object)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Type)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr)>, or <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr,%60%600)>, (via Windows PowerShell, IronPython, or the C# dynamic keyword, for example) can result in <code>MethodInvocationExceptions</code> because new overloads of these methods have been added that may be ambiguous to the scripting engines.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a76dc-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="a76dc-104">Suggestion</span></span>

<span data-ttu-id="a76dc-105">사용해야 하는 오버로드를 명확히 표시하도록 스크립트를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a76dc-105">Update scripts to clearly indicate which overload should be used.</span></span> <span data-ttu-id="a76dc-106">이것은 일반적으로 메서드의 형식 매개 변수를 <xref:System.Type>로 명시적 캐스팅하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a76dc-106">This can typically done by explicitly casting the methods' type parameters as <xref:System.Type>.</span></span> <span data-ttu-id="a76dc-107">문제를 해결하는 예제와 자세한 정보는 [이 링크](https://support.microsoft.com/kb/2909958/)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a76dc-107">See [this link](https://support.microsoft.com/kb/2909958/) for more detail and examples of how to workaround the issue.</span></span>

| <span data-ttu-id="a76dc-108">이름</span><span class="sxs-lookup"><span data-stu-id="a76dc-108">Name</span></span>    | <span data-ttu-id="a76dc-109">값</span><span class="sxs-lookup"><span data-stu-id="a76dc-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a76dc-110">Scope</span><span class="sxs-lookup"><span data-stu-id="a76dc-110">Scope</span></span>   |<span data-ttu-id="a76dc-111">부</span><span class="sxs-lookup"><span data-stu-id="a76dc-111">Minor</span></span>|
|<span data-ttu-id="a76dc-112">버전</span><span class="sxs-lookup"><span data-stu-id="a76dc-112">Version</span></span>|<span data-ttu-id="a76dc-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="a76dc-113">4.5.1</span></span>|
|<span data-ttu-id="a76dc-114">형식</span><span class="sxs-lookup"><span data-stu-id="a76dc-114">Type</span></span>|<span data-ttu-id="a76dc-115">런타임</span><span class="sxs-lookup"><span data-stu-id="a76dc-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="a76dc-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="a76dc-116">Affected APIs</span></span>

<span data-ttu-id="a76dc-117">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a76dc-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
