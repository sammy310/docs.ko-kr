---
title: ICorDebugStackWalk::GetFrame 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetFrame
helpviewer_keywords:
- GetFrame method [.NET Framework debugging]
- ICorDebugStackWalk::GetFrame method [.NET Framework debugging]
ms.assetid: 4083b505-5b59-44fb-8c5d-129db6a96c10
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 253a25fdfc1f00adbc20388660caf6c227030a1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111243"
---
# <a name="icordebugstackwalkgetframe-method"></a><span data-ttu-id="f00a4-102">ICorDebugStackWalk::GetFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="f00a4-102">ICorDebugStackWalk::GetFrame Method</span></span>
<span data-ttu-id="f00a4-103">현재 프레임을 가져옵니다 합니다 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f00a4-103">Gets the current frame in the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f00a4-104">구문</span><span class="sxs-lookup"><span data-stu-id="f00a4-104">Syntax</span></span>  
  
```  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f00a4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f00a4-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="f00a4-106">[in] 현재 스택 프레임을 나타내는 만들어진된 프레임 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f00a4-106">[in] A pointer to the address of the created frame object that represents the current frame in the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f00a4-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="f00a4-107">Return Value</span></span>  
 <span data-ttu-id="f00a4-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f00a4-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f00a4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f00a4-109">HRESULT</span></span>|<span data-ttu-id="f00a4-110">설명</span><span class="sxs-lookup"><span data-stu-id="f00a4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f00a4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f00a4-111">S_OK</span></span>|<span data-ttu-id="f00a4-112">런타임은 현재 프레임을 반환 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f00a4-112">The runtime successfully returned the current frame.</span></span>|  
|<span data-ttu-id="f00a4-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f00a4-113">E_FAIL</span></span>|<span data-ttu-id="f00a4-114">현재 프레임을 반환 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="f00a4-114">The current frame was not returned.</span></span>|  
|<span data-ttu-id="f00a4-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f00a4-115">S_FALSE</span></span>|<span data-ttu-id="f00a4-116">현재 프레임은 기본 스택 프레임입니다.</span><span class="sxs-lookup"><span data-stu-id="f00a4-116">The current frame is a native stack frame.</span></span>|  
|<span data-ttu-id="f00a4-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f00a4-117">E_INVALIDARG</span></span>|`pFrame` <span data-ttu-id="f00a4-118">null입니다.</span><span class="sxs-lookup"><span data-stu-id="f00a4-118">is null.</span></span>|  
|<span data-ttu-id="f00a4-119">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="f00a4-119">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="f00a4-120">프레임 포인터 끝 스택;에 이미 따라서 추가 프레임 없음 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f00a4-120">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="f00a4-121">예외</span><span class="sxs-lookup"><span data-stu-id="f00a4-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f00a4-122">설명</span><span class="sxs-lookup"><span data-stu-id="f00a4-122">Remarks</span></span>  
 `ICorDebugStackWalk` <span data-ttu-id="f00a4-123">만 실제 스택 프레임을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f00a4-123">returns only actual stack frames.</span></span> <span data-ttu-id="f00a4-124">사용 된 [ICorDebugThread3::GetActiveInternalFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) 내부 프레임을 반환 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f00a4-124">Use the [ICorDebugThread3::GetActiveInternalFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) method to return internal frames.</span></span> <span data-ttu-id="f00a4-125">(내부 프레임은 임시 데이터를 저장 하는 런타임에서 스택에 밀어 넣은 데이터 구조입니다.)</span><span class="sxs-lookup"><span data-stu-id="f00a4-125">(Internal frames are data structures pushed onto the stack by the runtime to store temporary data.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f00a4-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f00a4-126">Requirements</span></span>  
 <span data-ttu-id="f00a4-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f00a4-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f00a4-128">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f00a4-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f00a4-129">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f00a4-129">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f00a4-130">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="f00a4-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f00a4-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="f00a4-131">See also</span></span>

- [<span data-ttu-id="f00a4-132">ICorDebugStackWalk 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f00a4-132">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)
- [<span data-ttu-id="f00a4-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f00a4-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f00a4-134">디버깅</span><span class="sxs-lookup"><span data-stu-id="f00a4-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
