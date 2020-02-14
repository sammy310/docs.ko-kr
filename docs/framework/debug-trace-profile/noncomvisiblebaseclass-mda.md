---
title: nonComVisibleBaseClass MDA
ms.date: 03/30/2017
helpviewer_keywords:
- visible classes
- managed debugging assistants (MDAs), COM visible classes
- nonComVisibleBaseClass MDA
- COM visible classes
- QueryInterface call failures
- MDAs (managed debugging assistants), COM visible classes
ms.assetid: 9ec1af27-604b-477e-9ee2-e833eb10d3ce
ms.openlocfilehash: b46d5c6ffbf12efbae113a95bbfccd5742ec9ec9
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217294"
---
# <a name="noncomvisiblebaseclass-mda"></a><span data-ttu-id="6009d-102">nonComVisibleBaseClass MDA</span><span class="sxs-lookup"><span data-stu-id="6009d-102">nonComVisibleBaseClass MDA</span></span>
<span data-ttu-id="6009d-103">`nonComVisibleBaseClass` MDA(관리 디버깅 도우미)는 COM 노출이 아닌 기본 클래스에서 파생된 COM 노출 관리되는 클래스의 COM CCW(호출 가능 래퍼)에서 네이티브 코드 또는 비관리 코드에 의해 `QueryInterface` 호출이 수행될 때 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="6009d-103">The `nonComVisibleBaseClass` managed debugging assistant (MDA) is activated when a `QueryInterface` call is made by native or unmanaged code on the COM callable wrapper (CCW) of a COM-visible managed class that derives from a base class that is not COM visible.</span></span>  <span data-ttu-id="6009d-104">`QueryInterface` 호출은 호출에서 클래스 인터페이스 또는 COM 노출 관리되는 클래스의 기본 `IDispatch`를 요청하는 경우에만 MDA가 활성화되게 합니다.</span><span class="sxs-lookup"><span data-stu-id="6009d-104">The `QueryInterface` call causes the MDA to activate only in cases where call requests the class interface or default `IDispatch` of the COM-visible managed class.</span></span>  <span data-ttu-id="6009d-105">`QueryInterface` 특성이 적용되고 COM 노출 클래스에 의해 명시적으로 구현된 명시적 인터페이스에 대한 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>인 경우에는 MDA가 활성화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6009d-105">The MDA is not activated when the `QueryInterface` is for an explicit interface that has the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute applied and is explicitly implemented by the COM-visible class.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="6009d-106">증상</span><span class="sxs-lookup"><span data-stu-id="6009d-106">Symptoms</span></span>  
 <span data-ttu-id="6009d-107">COR_E_INVALIDOPERATION HRESULT로 인해 실패하는 네이티브 코드에서 `QueryInterface` 호출이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6009d-107">A `QueryInterface` call made from native code that is failing with a COR_E_INVALIDOPERATION HRESULT.</span></span>  <span data-ttu-id="6009d-108">HRESULT는 런타임에서 `QueryInterface` 호출을 허용하지 않아 이 MDA의 활성화가 발생하기 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6009d-108">The HRESULT might be due to the runtime disallowing `QueryInterface` calls that would cause the activation of this MDA.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="6009d-109">원인</span><span class="sxs-lookup"><span data-stu-id="6009d-109">Cause</span></span>  
 <span data-ttu-id="6009d-110">런타임에서 잠재적 버전 관리 문제 때문에 COM 노출이 아닌 클래스에서 파생된 COM 노출 클래스의 클래스 인터페이스 또는 기본 `QueryInterface` 인터페이스에 대해 `IDispatch` 호출을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6009d-110">The runtime cannot allow `QueryInterface` calls for the class interface or default `IDispatch` interface of a COM-visible class that derives from a class that is not COM-visible because of potential versioning problems.</span></span>  <span data-ttu-id="6009d-111">예를 들어 public 멤버가 COM 노출이 아닌 기본 클래스에 추가된 경우 기본 클래스 멤버를 포함하는 파생 클래스의 vtable이 이러한 변경 내용으로 인해 변경되기 때문에 파생 클래스를 사용하는 기존 COM 클라이언트가 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6009d-111">For example, if any public members were added to the base class that is not COM-visible, existing COM clients using the derived class could potentially break because the vtable of the derived class, which contains the base class members, would be altered by such a change.</span></span>  <span data-ttu-id="6009d-112">COM에 노출되는 명시적 인터페이스는 vtable에 인터페이스의 기본 멤버가 포함되지 않으므로 이 문제가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6009d-112">Explicit interfaces exposed to COM do not have this problem because they do not include the base members of interfaces in the vtable.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="6009d-113">해결 방법</span><span class="sxs-lookup"><span data-stu-id="6009d-113">Resolution</span></span>  
 <span data-ttu-id="6009d-114">클래스 인터페이스를 노출하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="6009d-114">Do not expose the class interface.</span></span> <span data-ttu-id="6009d-115">명시적 인터페이스를 정의하고 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="6009d-115">Define an explicit interface and apply the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute to it.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="6009d-116">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="6009d-116">Effect on the Runtime</span></span>  
 <span data-ttu-id="6009d-117">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6009d-117">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="6009d-118">출력</span><span class="sxs-lookup"><span data-stu-id="6009d-118">Output</span></span>  
 <span data-ttu-id="6009d-119">다음은 COM 노출이 아닌 클래스 `QueryInterface`에서 파생된 COM 노출 클래스 `Derived`에 대한 `Base` 호출의 예제 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="6009d-119">The following is an example message for a `QueryInterface` call on a COM-visible class `Derived` that derives from a non-COM-visible class `Base`.</span></span>  
  
```output
A QueryInterface call was made requesting the class interface of COM   
visible managed class 'Derived'. However since this class derives from   
non COM visible class 'Base', the QueryInterface call will fail. This   
is done to prevent the non COM visible base class from being   
constrained by the COM versioning rules.   
```  
  
## <a name="configuration"></a><span data-ttu-id="6009d-120">구성</span><span class="sxs-lookup"><span data-stu-id="6009d-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <nonComVisibleBaseClass />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6009d-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6009d-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="6009d-122">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="6009d-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="6009d-123">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="6009d-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
