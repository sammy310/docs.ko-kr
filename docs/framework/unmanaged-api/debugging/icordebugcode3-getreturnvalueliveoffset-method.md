---
description: '자세히 알아보기: ICorDebugCode3:: GetReturnValueLiveOffset 메서드'
title: ICorDebugCode3::GetReturnValueLiveOffset 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugCode3.GetReturnValueLiveOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type:
- apiref
ms.openlocfilehash: 6ec9a342805c047d7331c3ce2af2a4ffba596a26
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711013"
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a><span data-ttu-id="14948-103">ICorDebugCode3::GetReturnValueLiveOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="14948-103">ICorDebugCode3::GetReturnValueLiveOffset Method</span></span>

<span data-ttu-id="14948-104">지정 된 IL 오프셋의 경우 디버거가 함수에서 반환 값을 가져올 수 있도록 중단점이 배치 되어야 하는 네이티브 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="14948-104">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14948-105">구문</span><span class="sxs-lookup"><span data-stu-id="14948-105">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,
    [out] ULONG32 *pFetched,
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14948-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="14948-106">Parameters</span></span>  

 `ILoffset`  
 <span data-ttu-id="14948-107">IL 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="14948-107">The IL offset.</span></span> <span data-ttu-id="14948-108">함수 호출 사이트 여야 합니다. 그렇지 않으면 함수 호출이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="14948-108">It must be a function call site or the function call will fail.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="14948-109">저장 하는 데 사용할 수 있는 바이트 수 `pOffsets` 입니다.</span><span class="sxs-lookup"><span data-stu-id="14948-109">The number of bytes available to store `pOffsets`.</span></span>  
  
 `pFetched`  
 <span data-ttu-id="14948-110">실제로 반환 된 오프셋 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="14948-110">A pointer to the number of offsets actually returned.</span></span> <span data-ttu-id="14948-111">일반적으로 해당 값은 1 이지만 단일 IL 명령은 여러 어셈블리 명령에 매핑할 수 있습니다 `CALL` .</span><span class="sxs-lookup"><span data-stu-id="14948-111">Usually, its value is 1, but a single IL instruction can map to multiple `CALL` assembly instructions.</span></span>  
  
 `pOffsets`  
 <span data-ttu-id="14948-112">네이티브 오프셋의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="14948-112">An array of native offsets.</span></span> <span data-ttu-id="14948-113">일반적으로에는 단일 `pOffsets` 오프셋이 포함 되지만 단일 IL 명령은 여러 어셈블리 명령에 매핑할 수 있습니다 `CALL` .</span><span class="sxs-lookup"><span data-stu-id="14948-113">Typically, `pOffsets` contains a single offset, although a single IL instruction can map to multiple map to multiple `CALL` assembly instructions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14948-114">설명</span><span class="sxs-lookup"><span data-stu-id="14948-114">Remarks</span></span>  

 <span data-ttu-id="14948-115">이 메서드는 [ICorDebugILFrame3:: GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) 메서드와 함께 사용 되어 참조 형식을 반환 하는 메서드의 반환 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="14948-115">This method is used along with the [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value of a method that returns a reference type.</span></span> <span data-ttu-id="14948-116">함수 호출 사이트에 대 한 IL 오프셋을이 메서드에 전달 하면 하나 이상의 네이티브 오프셋을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="14948-116">Passing an IL offset to a function call site to this method returns one or more native offsets.</span></span> <span data-ttu-id="14948-117">그런 다음 디버거는 함수에서 이러한 네이티브 오프셋에 중단점을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14948-117">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="14948-118">디버거가 중단점 중 하나에 적중 하면이 메서드에 전달 된 것과 동일한 IL 오프셋을 [ICorDebugILFrame3:: GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) 메서드에 전달 하 여 반환 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14948-118">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to the [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value.</span></span> <span data-ttu-id="14948-119">그런 다음 디버거는 설정 된 모든 중단점을 지워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14948-119">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="14948-120">`ICorDebugCode3::GetReturnValueLiveOffset`및 [ICorDebugILFrame3:: GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) 메서드를 사용 하 여 참조 형식에 대해서만 반환 값 정보를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14948-120">The `ICorDebugCode3::GetReturnValueLiveOffset` and [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="14948-121">값 형식에서 반환 값 정보를 검색 하는 경우 (즉,에서 파생 되는 모든 형식 <xref:System.ValueType> )은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14948-121">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="14948-122">함수는 `HRESULT` 다음 표에 나와 있는 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="14948-122">The function returns the `HRESULT` values shown in the following table.</span></span>  
  
|<span data-ttu-id="14948-123">`HRESULT` 값</span><span class="sxs-lookup"><span data-stu-id="14948-123">`HRESULT` value</span></span>|<span data-ttu-id="14948-124">설명</span><span class="sxs-lookup"><span data-stu-id="14948-124">Description</span></span>|  
|---------------------|-----------------|  
|`S_OK`|<span data-ttu-id="14948-125">성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="14948-125">Success.</span></span>|  
|`CORDBG_E_INVALID_OPCODE`|<span data-ttu-id="14948-126">지정 된 IL 오프셋 사이트가 호출 명령이 아니거나 함수가를 반환 `void` 합니다.</span><span class="sxs-lookup"><span data-stu-id="14948-126">The given IL offset site is not a call instruction, or the function returns `void`.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="14948-127">지정 된 IL 오프셋은 적절 한 호출 이지만 반환 형식은 반환 값을 가져오는 데 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14948-127">The given IL offset is a proper call, but the return type is unsupported for getting a return value.</span></span>|  
  
 <span data-ttu-id="14948-128">`ICorDebugCode3::GetReturnValueLiveOffset`메서드는 x86 기반 및 AMD64 시스템 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14948-128">The `ICorDebugCode3::GetReturnValueLiveOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14948-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="14948-129">Requirements</span></span>  

 <span data-ttu-id="14948-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14948-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14948-131">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14948-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14948-132">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14948-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14948-133">**.NET Framework 버전:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14948-133">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14948-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14948-134">See also</span></span>

- [<span data-ttu-id="14948-135">GetReturnValueForILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="14948-135">GetReturnValueForILOffset Method</span></span>](icordebugilframe3-getreturnvalueforiloffset-method.md)
- [<span data-ttu-id="14948-136">ICorDebugCode3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="14948-136">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
