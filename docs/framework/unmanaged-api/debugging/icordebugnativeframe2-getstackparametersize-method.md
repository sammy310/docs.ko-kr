---
title: ICorDebugNativeFrame2::GetStackParameterSize 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.GetStackParameterSize Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47968d7550c3d16d201680caab705c0d7c85c784
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200144"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="f005d-102">ICorDebugNativeFrame2::GetStackParameterSize 메서드</span><span class="sxs-lookup"><span data-stu-id="f005d-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="f005d-103">X86 운영 체제의 스택에 누적 크기 매개 변수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f005d-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f005d-104">구문</span><span class="sxs-lookup"><span data-stu-id="f005d-104">Syntax</span></span>  
  
```  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a><span data-ttu-id="f005d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f005d-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="f005d-106">[out] 스택에 매개 변수의 누적 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f005d-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f005d-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="f005d-107">Return Value</span></span>  
 <span data-ttu-id="f005d-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f005d-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f005d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f005d-109">HRESULT</span></span>|<span data-ttu-id="f005d-110">설명</span><span class="sxs-lookup"><span data-stu-id="f005d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f005d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f005d-111">S_OK</span></span>|<span data-ttu-id="f005d-112">스택 크기를 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f005d-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="f005d-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f005d-113">S_FALSE</span></span>|`GetStackParameterSize` <span data-ttu-id="f005d-114">비 x86 플랫폼에서 호출 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f005d-114">was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="f005d-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f005d-115">E_FAIL</span></span>|`The size of the parameters could not be returned`<span data-ttu-id="f005d-116">.</span><span class="sxs-lookup"><span data-stu-id="f005d-116">.</span></span>|  
|<span data-ttu-id="f005d-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f005d-117">E_INVALIDARG</span></span>|`pSize` <span data-ttu-id="f005d-118">`null`합니다.</span><span class="sxs-lookup"><span data-stu-id="f005d-118">Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="f005d-119">예외</span><span class="sxs-lookup"><span data-stu-id="f005d-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f005d-120">설명</span><span class="sxs-lookup"><span data-stu-id="f005d-120">Remarks</span></span>  
 <span data-ttu-id="f005d-121">합니다 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) 메서드 스택에 푸시된 매개 변수에 대 한 스택 포인터를 조정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="f005d-121">The [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="f005d-122">반환 된 값을 대신 사용할 수 `GetStackParameterSize` 스택 포인터 매개 변수를 조정 하는 네이티브 언를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f005d-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f005d-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f005d-123">Requirements</span></span>  
 <span data-ttu-id="f005d-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f005d-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f005d-125">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f005d-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f005d-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f005d-126">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f005d-127">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="f005d-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f005d-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="f005d-128">See also</span></span>

- [<span data-ttu-id="f005d-129">ICorDebugNativeFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f005d-129">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="f005d-130">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f005d-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f005d-131">디버깅</span><span class="sxs-lookup"><span data-stu-id="f005d-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
