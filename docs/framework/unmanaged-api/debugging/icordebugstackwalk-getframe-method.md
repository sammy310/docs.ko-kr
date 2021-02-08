---
description: '자세히 알아보기: ICorDebugStackWalk:: GetFrame 메서드'
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
ms.openlocfilehash: b00ddb6a475aff4263a922f5a20b866cd0e1b2ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794743"
---
# <a name="icordebugstackwalkgetframe-method"></a><span data-ttu-id="d10b4-103">ICorDebugStackWalk::GetFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="d10b4-103">ICorDebugStackWalk::GetFrame Method</span></span>

<span data-ttu-id="d10b4-104">[ICorDebugStackWalk](icordebugstackwalk-interface.md) 개체의 현재 프레임을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d10b4-104">Gets the current frame in the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d10b4-105">구문</span><span class="sxs-lookup"><span data-stu-id="d10b4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d10b4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d10b4-106">Parameters</span></span>  

 `pFrame`  
 <span data-ttu-id="d10b4-107">진행 스택의 현재 프레임을 나타내는 만들어진 프레임 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d10b4-107">[in] A pointer to the address of the created frame object that represents the current frame in the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d10b4-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="d10b4-108">Return Value</span></span>  

 <span data-ttu-id="d10b4-109">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d10b4-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d10b4-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d10b4-110">HRESULT</span></span>|<span data-ttu-id="d10b4-111">설명</span><span class="sxs-lookup"><span data-stu-id="d10b4-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d10b4-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d10b4-112">S_OK</span></span>|<span data-ttu-id="d10b4-113">런타임에서 현재 프레임을 성공적으로 반환 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d10b4-113">The runtime successfully returned the current frame.</span></span>|  
|<span data-ttu-id="d10b4-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d10b4-114">E_FAIL</span></span>|<span data-ttu-id="d10b4-115">현재 프레임이 반환 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d10b4-115">The current frame was not returned.</span></span>|  
|<span data-ttu-id="d10b4-116">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d10b4-116">S_FALSE</span></span>|<span data-ttu-id="d10b4-117">현재 프레임은 네이티브 스택 프레임입니다.</span><span class="sxs-lookup"><span data-stu-id="d10b4-117">The current frame is a native stack frame.</span></span>|  
|<span data-ttu-id="d10b4-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d10b4-118">E_INVALIDARG</span></span>|<span data-ttu-id="d10b4-119">`pFrame`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="d10b4-119">`pFrame` is null.</span></span>|  
|<span data-ttu-id="d10b4-120">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="d10b4-120">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="d10b4-121">프레임 포인터가 이미 스택의 끝에 있습니다. 따라서 추가 프레임에는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d10b4-121">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="d10b4-122">예외</span><span class="sxs-lookup"><span data-stu-id="d10b4-122">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d10b4-123">설명</span><span class="sxs-lookup"><span data-stu-id="d10b4-123">Remarks</span></span>  

 <span data-ttu-id="d10b4-124">`ICorDebugStackWalk` 실제 스택 프레임만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d10b4-124">`ICorDebugStackWalk` returns only actual stack frames.</span></span> <span data-ttu-id="d10b4-125">[ICorDebugThread3:: GetActiveInternalFrames](icordebugthread3-getactiveinternalframes-method.md) 메서드를 사용 하 여 내부 프레임을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d10b4-125">Use the [ICorDebugThread3::GetActiveInternalFrames](icordebugthread3-getactiveinternalframes-method.md) method to return internal frames.</span></span> <span data-ttu-id="d10b4-126">내부 프레임은 런타임에서 임시 데이터를 저장 하기 위해 스택에 푸시되는 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="d10b4-126">(Internal frames are data structures pushed onto the stack by the runtime to store temporary data.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d10b4-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d10b4-127">Requirements</span></span>  

 <span data-ttu-id="d10b4-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d10b4-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d10b4-129">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d10b4-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d10b4-130">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d10b4-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d10b4-131">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d10b4-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d10b4-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d10b4-132">See also</span></span>

- [<span data-ttu-id="d10b4-133">ICorDebugStackWalk 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d10b4-133">ICorDebugStackWalk Interface</span></span>](icordebugstackwalk-interface.md)
- [<span data-ttu-id="d10b4-134">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d10b4-134">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d10b4-135">디버깅</span><span class="sxs-lookup"><span data-stu-id="d10b4-135">Debugging</span></span>](index.md)
