---
title: invalidMemberDeclaration MDA
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fe15d718a9c5f91bfae4f37c04e726990e2fbd45
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052580"
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="76286-102">invalidMemberDeclaration MDA</span><span class="sxs-lookup"><span data-stu-id="76286-102">invalidMemberDeclaration MDA</span></span>
<span data-ttu-id="76286-103">`invalidMemberDeclaration` MDA(관리 디버깅 도우미)는 COM에서 호출할 멤버의 매개 변수를 마샬링하는 방법을 결정하는 동안 발생 하는 오류를 보고하기 위해 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="76286-103">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="76286-104">증상</span><span class="sxs-lookup"><span data-stu-id="76286-104">Symptoms</span></span>  
 <span data-ttu-id="76286-105">호출된 관리되는 메서드 없이 실패 HRESULT가 COM에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="76286-105">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="76286-106">원인</span><span class="sxs-lookup"><span data-stu-id="76286-106">Cause</span></span>  
 <span data-ttu-id="76286-107">이는 매개 변수 중 하나의 호환되지 않는 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성 때문일 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="76286-107">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="76286-108">해결 방법</span><span class="sxs-lookup"><span data-stu-id="76286-108">Resolution</span></span>  
 <span data-ttu-id="76286-109">매개 변수에서 유효한 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="76286-109">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="76286-110">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="76286-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="76286-111">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76286-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="76286-112">출력</span><span class="sxs-lookup"><span data-stu-id="76286-112">Output</span></span>  
 <span data-ttu-id="76286-113">멤버 이름, 형식 이름 및 오류 메시지를 포함하는 정보 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="76286-113">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="76286-114">Configuration</span><span class="sxs-lookup"><span data-stu-id="76286-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="76286-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="76286-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="76286-116">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="76286-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="76286-117">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="76286-117">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
