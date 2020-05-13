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
ms.openlocfilehash: 5f80125a67e634dda05b9427b5f46db8f21b29f8
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379208"
---
# <a name="icordebugstackwalkgetframe-method"></a><span data-ttu-id="46c3d-102">ICorDebugStackWalk::GetFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="46c3d-102">ICorDebugStackWalk::GetFrame Method</span></span>
<span data-ttu-id="46c3d-103">[ICorDebugStackWalk](icordebugstackwalk-interface.md) 개체의 현재 프레임을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="46c3d-103">Gets the current frame in the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46c3d-104">구문</span><span class="sxs-lookup"><span data-stu-id="46c3d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46c3d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46c3d-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="46c3d-106">진행 스택의 현재 프레임을 나타내는 만들어진 프레임 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="46c3d-106">[in] A pointer to the address of the created frame object that represents the current frame in the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46c3d-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="46c3d-107">Return Value</span></span>  
 <span data-ttu-id="46c3d-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="46c3d-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="46c3d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="46c3d-109">HRESULT</span></span>|<span data-ttu-id="46c3d-110">설명</span><span class="sxs-lookup"><span data-stu-id="46c3d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="46c3d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="46c3d-111">S_OK</span></span>|<span data-ttu-id="46c3d-112">런타임에서 현재 프레임을 성공적으로 반환 했습니다.</span><span class="sxs-lookup"><span data-stu-id="46c3d-112">The runtime successfully returned the current frame.</span></span>|  
|<span data-ttu-id="46c3d-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="46c3d-113">E_FAIL</span></span>|<span data-ttu-id="46c3d-114">현재 프레임이 반환 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="46c3d-114">The current frame was not returned.</span></span>|  
|<span data-ttu-id="46c3d-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="46c3d-115">S_FALSE</span></span>|<span data-ttu-id="46c3d-116">현재 프레임은 네이티브 스택 프레임입니다.</span><span class="sxs-lookup"><span data-stu-id="46c3d-116">The current frame is a native stack frame.</span></span>|  
|<span data-ttu-id="46c3d-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="46c3d-117">E_INVALIDARG</span></span>|<span data-ttu-id="46c3d-118">`pFrame`가 null인 경우</span><span class="sxs-lookup"><span data-stu-id="46c3d-118">`pFrame` is null.</span></span>|  
|<span data-ttu-id="46c3d-119">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="46c3d-119">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="46c3d-120">프레임 포인터가 이미 스택의 끝에 있습니다. 따라서 추가 프레임에는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46c3d-120">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="46c3d-121">예외</span><span class="sxs-lookup"><span data-stu-id="46c3d-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46c3d-122">설명</span><span class="sxs-lookup"><span data-stu-id="46c3d-122">Remarks</span></span>  
 <span data-ttu-id="46c3d-123">`ICorDebugStackWalk`실제 스택 프레임만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c3d-123">`ICorDebugStackWalk` returns only actual stack frames.</span></span> <span data-ttu-id="46c3d-124">[ICorDebugThread3:: GetActiveInternalFrames](icordebugthread3-getactiveinternalframes-method.md) 메서드를 사용 하 여 내부 프레임을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="46c3d-124">Use the [ICorDebugThread3::GetActiveInternalFrames](icordebugthread3-getactiveinternalframes-method.md) method to return internal frames.</span></span> <span data-ttu-id="46c3d-125">내부 프레임은 런타임에서 임시 데이터를 저장 하기 위해 스택에 푸시되는 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="46c3d-125">(Internal frames are data structures pushed onto the stack by the runtime to store temporary data.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46c3d-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46c3d-126">Requirements</span></span>  
 <span data-ttu-id="46c3d-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46c3d-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46c3d-128">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46c3d-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46c3d-129">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46c3d-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46c3d-130">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46c3d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46c3d-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46c3d-131">See also</span></span>

- [<span data-ttu-id="46c3d-132">ICorDebugStackWalk 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46c3d-132">ICorDebugStackWalk Interface</span></span>](icordebugstackwalk-interface.md)
- [<span data-ttu-id="46c3d-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46c3d-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="46c3d-134">디버깅</span><span class="sxs-lookup"><span data-stu-id="46c3d-134">Debugging</span></span>](index.md)
