---
title: ICorDebugILFrame3::GetReturnValueForILOffset 메서드
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
api_name:
- ICorDebugILFrame3.GetReturnValueForILOffset
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 06522727-5f64-4391-9331-11386883c352
topic_type:
- apiref
ms.openlocfilehash: 7a96385ccc6e7f9089365c19bb8f150015bba81c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788523"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a><span data-ttu-id="03674-102">ICorDebugILFrame3::GetReturnValueForILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="03674-102">ICorDebugILFrame3::GetReturnValueForILOffset Method</span></span>
<span data-ttu-id="03674-103">함수의 반환 값을 캡슐화 하는 "ICorDebugValue" 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="03674-103">Gets an "ICorDebugValue" object that encapsulates the return value of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03674-104">구문</span><span class="sxs-lookup"><span data-stu-id="03674-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,   
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03674-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="03674-105">Parameters</span></span>  
 `ILOffset`  
 <span data-ttu-id="03674-106">IL 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="03674-106">The IL offset.</span></span> <span data-ttu-id="03674-107">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03674-107">See the Remarks section.</span></span>  
  
 `ppReturnValue`  
 <span data-ttu-id="03674-108">함수 호출의 반환 값에 대 한 정보를 제공 하는 "ICorDebugValue" 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="03674-108">A pointer to the address of an "ICorDebugValue" interface object that provides information about the return value of a function call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03674-109">주의</span><span class="sxs-lookup"><span data-stu-id="03674-109">Remarks</span></span>  
 <span data-ttu-id="03674-110">이 메서드는 [ICorDebugCode3:: GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) 메서드와 함께 메서드의 반환 값을 가져오는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03674-110">This method is used along with the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method to get the return value of a method.</span></span> <span data-ttu-id="03674-111">다음 두 코드 예제와 같이 반환 값이 무시 되는 메서드의 경우 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="03674-111">It is particularly useful in the case of methods whose return values are ignored, as in the following two code examples.</span></span> <span data-ttu-id="03674-112">첫 번째 예제에서는 <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> 메서드를 호출 하지만 메서드의 반환 값을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="03674-112">The first example calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method, but ignores the method's return value.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 <span data-ttu-id="03674-113">두 번째 예제에서는 디버깅에서 훨씬 일반적인 문제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03674-113">The second example illustrates a much more common problem in debugging.</span></span> <span data-ttu-id="03674-114">메서드는 메서드 호출에서 인수로 사용 되므로 해당 반환 값은 디버거가 호출 된 메서드를 통해 단계를 수행 하는 경우에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03674-114">Because a method is used as an argument in a method call, its return value is accessible only when the debugger steps through the called method.</span></span> <span data-ttu-id="03674-115">대부분의 경우 호출 된 메서드가 외부 라이브러리에서 정의 된 경우에는 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="03674-115">In many cases, particularly when the called method is defined in an external library, that is not possible.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 <span data-ttu-id="03674-116">[ICorDebugCode3:: GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) 메서드를 함수 호출 사이트에 대 한 IL 오프셋으로 전달 하는 경우 하나 이상의 네이티브 오프셋을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="03674-116">If you pass the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method an IL offset to a function call site, it returns one or more native offsets.</span></span> <span data-ttu-id="03674-117">그런 다음 디버거는 함수에서 이러한 네이티브 오프셋에 중단점을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03674-117">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="03674-118">디버거가 중단점 중 하나에 적중 하면이 메서드에 전달 된 것과 동일한 IL 오프셋을 전달 하 여 반환 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03674-118">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to get the return value.</span></span> <span data-ttu-id="03674-119">그런 다음 디버거는 설정 된 모든 중단점을 지워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03674-119">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="03674-120">[ICorDebugCode3:: GetReturnValueLiveOffset 메서드](icordebugcode3-getreturnvalueliveoffset-method.md) 및 `ICorDebugILFrame3::GetReturnValueForILOffset` 메서드를 사용 하 여 참조 형식에 대해서만 반환 값 정보를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03674-120">The [ICorDebugCode3::GetReturnValueLiveOffset Method](icordebugcode3-getreturnvalueliveoffset-method.md) and `ICorDebugILFrame3::GetReturnValueForILOffset` methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="03674-121">값 형식에서 반환 값 정보를 검색할 수 있습니다. 즉, <xref:System.ValueType>에서 파생 되는 모든 형식은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03674-121">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="03674-122">`ILOffset` 매개 변수로 지정 된 IL 오프셋은 함수 호출 사이트에 있어야 하며, 디버기는 동일한 IL 오프셋에 대해 [ICorDebugCode3:: GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) 메서드에서 반환 되는 네이티브 오프셋에 설정 된 중단점에서 중지 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03674-122">The IL offset specified by the `ILOffset` parameter should be at a function call site, and the debuggee should be stopped at a breakpoint set at the native offset returned by the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method for the same IL offset.</span></span> <span data-ttu-id="03674-123">디버기가 지정 된 IL 오프셋의 올바른 위치에서 중지 되지 않은 경우 API가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="03674-123">If the debuggee is not stopped at the correct location for the specified IL offset, the API will fail.</span></span>  
  
 <span data-ttu-id="03674-124">함수 호출에서 값을 반환 하지 않는 경우 API가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="03674-124">If the function call doesn't return a value, the API will fail.</span></span>  
  
 <span data-ttu-id="03674-125">`ICorDebugILFrame3::GetReturnValueForILOffset` 메서드는 x86 기반 및 AMD64 시스템 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03674-125">The `ICorDebugILFrame3::GetReturnValueForILOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03674-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="03674-126">Requirements</span></span>  
 <span data-ttu-id="03674-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03674-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03674-128">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03674-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03674-129">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03674-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03674-130">**.NET Framework 버전:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03674-130">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03674-131">참조</span><span class="sxs-lookup"><span data-stu-id="03674-131">See also</span></span>

- [<span data-ttu-id="03674-132">GetReturnValueLiveOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="03674-132">GetReturnValueLiveOffset Method</span></span>](icordebugcode3-getreturnvalueliveoffset-method.md)
- [<span data-ttu-id="03674-133">ICorDebugILFrame3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="03674-133">ICorDebugILFrame3 Interface</span></span>](icordebugilframe3-interface.md)
