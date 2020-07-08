---
title: invalidMemberDeclaration MDA
description: 관리 되는 메서드를 호출 하지 않고 오류 HRESULT가 COM에 반환 되는 경우 호출 되는 invalidMemberDeclaration 관리 디버깅 도우미를 검토 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
ms.openlocfilehash: 5dbfba2baec3263d91746c06379438e97a81f005
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051716"
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="54c05-103">invalidMemberDeclaration MDA</span><span class="sxs-lookup"><span data-stu-id="54c05-103">invalidMemberDeclaration MDA</span></span>
<span data-ttu-id="54c05-104">`invalidMemberDeclaration` MDA(관리 디버깅 도우미)는 COM에서 호출할 멤버의 매개 변수를 마샬링하는 방법을 결정하는 동안 발생 하는 오류를 보고하기 위해 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="54c05-104">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="54c05-105">증상</span><span class="sxs-lookup"><span data-stu-id="54c05-105">Symptoms</span></span>  
 <span data-ttu-id="54c05-106">호출된 관리되는 메서드 없이 실패 HRESULT가 COM에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="54c05-106">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="54c05-107">원인</span><span class="sxs-lookup"><span data-stu-id="54c05-107">Cause</span></span>  
 <span data-ttu-id="54c05-108">이는 매개 변수 중 하나의 호환되지 않는 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성 때문일 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="54c05-108">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="54c05-109">해결 방법</span><span class="sxs-lookup"><span data-stu-id="54c05-109">Resolution</span></span>  
 <span data-ttu-id="54c05-110">매개 변수에서 유효한 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="54c05-110">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="54c05-111">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="54c05-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="54c05-112">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54c05-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="54c05-113">출력</span><span class="sxs-lookup"><span data-stu-id="54c05-113">Output</span></span>  
 <span data-ttu-id="54c05-114">멤버 이름, 형식 이름 및 오류 메시지를 포함하는 정보 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="54c05-114">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="54c05-115">Configuration</span><span class="sxs-lookup"><span data-stu-id="54c05-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="54c05-116">참조</span><span class="sxs-lookup"><span data-stu-id="54c05-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="54c05-117">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="54c05-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="54c05-118">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="54c05-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
