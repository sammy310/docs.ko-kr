---
title: ICorDebugDataTarget2::CreateVirtualUnwinder Method
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c8befed8bc810344b2a3344212a6a4a854300e3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164660"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a><span data-ttu-id="a8940-102">ICorDebugDataTarget2::CreateVirtualUnwinder Method</span><span class="sxs-lookup"><span data-stu-id="a8940-102">ICorDebugDataTarget2::CreateVirtualUnwinder Method</span></span>
<span data-ttu-id="a8940-103">초기 컨텍스트(반드시 스레드의 리프일 필요는 없음)에서 해제를 시작하는 새 스택 해제기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8940-103">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8940-104">구문</span><span class="sxs-lookup"><span data-stu-id="a8940-104">Syntax</span></span>  
  
```  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8940-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a8940-105">Parameters</span></span>  
 <span data-ttu-id="a8940-106">nativeThreadID</span><span class="sxs-lookup"><span data-stu-id="a8940-106">nativeThreadID</span></span>  
 <span data-ttu-id="a8940-107">[in] 스택을 해제할 스레드의 네이티브 스레드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a8940-107">[in] The native thread ID of the thread whose stack is to be unwound.</span></span>  
  
 <span data-ttu-id="a8940-108">contextFlags</span><span class="sxs-lookup"><span data-stu-id="a8940-108">contextFlags</span></span>  
 <span data-ttu-id="a8940-109">[in] `initialContext`에 정의된 컨텍스트 부분을 지정하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="a8940-109">[in] Flags that specify which parts of the context are defined in `initialContext`.</span></span>  
  
 <span data-ttu-id="a8940-110">cbContext</span><span class="sxs-lookup"><span data-stu-id="a8940-110">cbContext</span></span>  
 <span data-ttu-id="a8940-111">[in] `initialContext`의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a8940-111">[in] The size of `initialContext`.</span></span>  
  
 <span data-ttu-id="a8940-112">initialContext</span><span class="sxs-lookup"><span data-stu-id="a8940-112">initialContext</span></span>  
 <span data-ttu-id="a8940-113">[in] 컨텍스트의 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="a8940-113">[in] The data in the context.</span></span>  
  
 <span data-ttu-id="a8940-114">ppUnwinder</span><span class="sxs-lookup"><span data-stu-id="a8940-114">ppUnwinder</span></span>  
 <span data-ttu-id="a8940-115">[out] ICorDebugVirtualUnwinder 인터페이스 개체의 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a8940-115">[out] A pointer to the address of an ICorDebugVirtualUnwinder interface object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8940-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="a8940-116">Return Value</span></span>  
 <span data-ttu-id="a8940-117">성공하는 경우 `S_OK`입니다.</span><span class="sxs-lookup"><span data-stu-id="a8940-117">`S_OK` if successful.</span></span> <span data-ttu-id="a8940-118">기타 `HRESULT`는 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a8940-118">Any other `HRESULT` indicates failure.</span></span> <span data-ttu-id="a8940-119">모든 실패 `HRESULT` mscordbi에 수신 심각한 오류로 간주 됩니다 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 반환 하는 메서드 `CORDBG_E_DATA_TARGET_ERROR`합니다.</span><span class="sxs-lookup"><span data-stu-id="a8940-119">Any failing `HRESULT` received by mscordbi is considered fatal and causes [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8940-120">설명</span><span class="sxs-lookup"><span data-stu-id="a8940-120">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8940-121">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8940-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8940-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a8940-122">Requirements</span></span>  
 <span data-ttu-id="a8940-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a8940-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8940-124">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8940-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8940-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8940-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8940-126">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8940-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8940-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="a8940-127">See also</span></span>

- [<span data-ttu-id="a8940-128">ICorDebugDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a8940-128">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="a8940-129">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a8940-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
