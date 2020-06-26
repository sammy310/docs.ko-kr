---
title: exceptionSwallowedOnCallFromCom MDA
description: .NET에서 exceptionSwallowedOnCallFromCOM 관리 디버깅 길잡이를 검토 합니다. 이 MDA는 예외가 throw 되었지만이를 보고할 좋은 방법이 없는 경우에 발생 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- messages, informational
- informational messages
- managed debugging assistants (MDAs), exceptions
- exception handling, managed debugging assistants
- MDAs (managed debugging assistants), exceptions
- ExceptionSwallowedOnCallFromCOM MDA
ms.assetid: 55d6ab12-f251-4aab-aa64-aacbe9d9f974
ms.openlocfilehash: 434f06cf953147d5c245e625db997bed6dbef700
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415955"
---
# <a name="exceptionswallowedoncallfromcom-mda"></a><span data-ttu-id="4c7bd-104">exceptionSwallowedOnCallFromCom MDA</span><span class="sxs-lookup"><span data-stu-id="4c7bd-104">exceptionSwallowedOnCallFromCom MDA</span></span>
<span data-ttu-id="4c7bd-105">`exceptionSwallowedOnCallFromCOM` MDA(관리 디버깅 도우미)는 관리되지 않는 HRESULT 반환 형식이 없는 메서드를 통해 COM에서 호출된 CLR(공용 언어 런타임) 코드에서 예외가 throw되면 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c7bd-105">The `exceptionSwallowedOnCallFromCOM` managed debugging assistant (MDA) is activated when an exception is thrown from common language runtime (CLR) code called from COM via a method that does not have an unmanaged HRESULT return type.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="4c7bd-106">증상</span><span class="sxs-lookup"><span data-stu-id="4c7bd-106">Symptoms</span></span>  
 <span data-ttu-id="4c7bd-107">COM에서 관리되는 구성 요소에 대한 호출이 FALSE 또는 0 값으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c7bd-107">A call to a managed component from COM returns with a value of FALSE or 0.</span></span> <span data-ttu-id="4c7bd-108">또는 메서드의 반환 형식이 void인 경우 메서드 실행 중에 예외가 throw되었음을 나타내는 표시가 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c7bd-108">Alternatively, if the method has a void return type, there may be no indication that an exception was thrown during the execution of the method.</span></span> <span data-ttu-id="4c7bd-109">이 경우 예외가 자동으로 catch되고 실행이 COM 호출자에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c7bd-109">In this case, the exception will be silently caught and execution will return to the COM caller.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="4c7bd-110">원인</span><span class="sxs-lookup"><span data-stu-id="4c7bd-110">Cause</span></span>  
 <span data-ttu-id="4c7bd-111">예외가 throw되었지만 해당 예외를 보고할 유효한 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c7bd-111">An exception was thrown, but there is no valid way to report it.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="4c7bd-112">해결 방법</span><span class="sxs-lookup"><span data-stu-id="4c7bd-112">Resolution</span></span>  
 <span data-ttu-id="4c7bd-113">정보 제공의 목적이며, 반드시 버그를 의미하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4c7bd-113">Informational only, not necessarily indicative of a bug.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="4c7bd-114">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="4c7bd-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="4c7bd-115">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c7bd-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="4c7bd-116">자동으로 catch된 예외에 대한 데이터를 보고할 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="4c7bd-116">It only reports data about silently caught exceptions.</span></span>  
  
## <a name="output"></a><span data-ttu-id="4c7bd-117">출력</span><span class="sxs-lookup"><span data-stu-id="4c7bd-117">Output</span></span>  
 <span data-ttu-id="4c7bd-118">메서드 이름, 형식 이름 및 예외 메시지를 포함하는 정보 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="4c7bd-118">Informational message containing the method name, type name, and exception message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="4c7bd-119">구성</span><span class="sxs-lookup"><span data-stu-id="4c7bd-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <exceptionSwallowedOnCallFromCom />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4c7bd-120">추가 정보</span><span class="sxs-lookup"><span data-stu-id="4c7bd-120">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="4c7bd-121">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="4c7bd-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="4c7bd-122">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="4c7bd-122">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
