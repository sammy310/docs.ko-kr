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
ms.openlocfilehash: 0d1ef6c1369fd399f5b36b24a21c4b5d7f1e80fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178810"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a><span data-ttu-id="37edc-102">ICorDebugILFrame3::GetReturnValueForILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="37edc-102">ICorDebugILFrame3::GetReturnValueForILOffset Method</span></span>
<span data-ttu-id="37edc-103">함수의 반환 값을 캡슐화하는 "ICorDebugValue" 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37edc-103">Gets an "ICorDebugValue" object that encapsulates the return value of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37edc-104">구문</span><span class="sxs-lookup"><span data-stu-id="37edc-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37edc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="37edc-105">Parameters</span></span>  
 `ILOffset`  
 <span data-ttu-id="37edc-106">IL 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="37edc-106">The IL offset.</span></span> <span data-ttu-id="37edc-107">주의 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="37edc-107">See the Remarks section.</span></span>  
  
 `ppReturnValue`  
 <span data-ttu-id="37edc-108">함수 호출의 반환 값에 대한 정보를 제공하는 "ICorDebugValue" 인터페이스 개체의 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="37edc-108">A pointer to the address of an "ICorDebugValue" interface object that provides information about the return value of a function call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37edc-109">설명</span><span class="sxs-lookup"><span data-stu-id="37edc-109">Remarks</span></span>  
 <span data-ttu-id="37edc-110">이 메서드는 [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) 메서드와 함께 사용 되어 메서드의 반환 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37edc-110">This method is used along with the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method to get the return value of a method.</span></span> <span data-ttu-id="37edc-111">다음 두 코드 예제와 같이 반환 값이 무시되는 메서드의 경우 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="37edc-111">It is particularly useful in the case of methods whose return values are ignored, as in the following two code examples.</span></span> <span data-ttu-id="37edc-112">첫 번째 예제에서는 메서드를 <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> 호출하지만 메서드의 반환 값을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="37edc-112">The first example calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method, but ignores the method's return value.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 <span data-ttu-id="37edc-113">두 번째 예제에서는 디버깅에서 훨씬 더 일반적인 문제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="37edc-113">The second example illustrates a much more common problem in debugging.</span></span> <span data-ttu-id="37edc-114">메서드는 메서드 호출에서 인수로 사용되므로 디버거가 호출된 메서드를 단계화할 때만 반환 값에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37edc-114">Because a method is used as an argument in a method call, its return value is accessible only when the debugger steps through the called method.</span></span> <span data-ttu-id="37edc-115">대부분의 경우, 특히 호출된 메서드가 외부 라이브러리에서 정의된 경우 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="37edc-115">In many cases, particularly when the called method is defined in an external library, that is not possible.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 <span data-ttu-id="37edc-116">[ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) 메서드함수 오프셋함수 호출 사이트에 전달 하면 하나 이상의 네이티브 오프셋을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="37edc-116">If you pass the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method an IL offset to a function call site, it returns one or more native offsets.</span></span> <span data-ttu-id="37edc-117">그런 다음 디버거는 함수의 이러한 네이티브 오프셋에 중단점을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37edc-117">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="37edc-118">디버거가 중단점 중 하나에 도달하면 반환 값을 얻기 위해 이 메서드에 전달한 것과 동일한 IL 오프셋을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37edc-118">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to get the return value.</span></span> <span data-ttu-id="37edc-119">그런 다음 디버거가 설정한 모든 중단점을 지워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37edc-119">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="37edc-120">[ICorDebugCode3:GetReturnValueLiveOffset 메서드](icordebugcode3-getreturnvalueliveoffset-method.md) 및 `ICorDebugILFrame3::GetReturnValueForILOffset` 메서드를 사용하면 참조 형식에 대해서만 반환 값 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37edc-120">The [ICorDebugCode3::GetReturnValueLiveOffset Method](icordebugcode3-getreturnvalueliveoffset-method.md) and `ICorDebugILFrame3::GetReturnValueForILOffset` methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="37edc-121">값 형식(즉, 파생되는 모든 <xref:System.ValueType>형식)에서 반환 값 정보를 검색하는 것은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37edc-121">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="37edc-122">매개 변수에 `ILOffset` 의해 지정된 IL 오프셋은 함수 호출 사이트에 있어야 하며, 디버그지는 동일한 IL 오프셋에 대해 [ICorDebugCode3:GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) 메서드에서 반환되는 네이티브 오프셋의 중단점 집합에서 중지되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37edc-122">The IL offset specified by the `ILOffset` parameter should be at a function call site, and the debuggee should be stopped at a breakpoint set at the native offset returned by the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method for the same IL offset.</span></span> <span data-ttu-id="37edc-123">지정된 IL 오프셋의 올바른 위치에서 디버그가 중지되지 않으면 API가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="37edc-123">If the debuggee is not stopped at the correct location for the specified IL offset, the API will fail.</span></span>  
  
 <span data-ttu-id="37edc-124">함수 호출이 값을 반환하지 않으면 API가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="37edc-124">If the function call doesn't return a value, the API will fail.</span></span>  
  
 <span data-ttu-id="37edc-125">이 `ICorDebugILFrame3::GetReturnValueForILOffset` 방법은 x86 기반 및 AMD64 시스템에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37edc-125">The `ICorDebugILFrame3::GetReturnValueForILOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37edc-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="37edc-126">Requirements</span></span>  
 <span data-ttu-id="37edc-127">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37edc-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37edc-128">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="37edc-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37edc-129">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37edc-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37edc-130">**.NET Framework 버전:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37edc-130">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37edc-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37edc-131">See also</span></span>

- [<span data-ttu-id="37edc-132">GetReturnValueLiveOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="37edc-132">GetReturnValueLiveOffset Method</span></span>](icordebugcode3-getreturnvalueliveoffset-method.md)
- [<span data-ttu-id="37edc-133">ICorDebugILFrame3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37edc-133">ICorDebugILFrame3 Interface</span></span>](icordebugilframe3-interface.md)
