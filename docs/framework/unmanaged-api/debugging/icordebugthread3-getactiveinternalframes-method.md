---
description: '자세히 알아보기: ICorDebugThread3:: GetActiveInternalFrames 메서드'
title: ICorDebugThread3::GetActiveInternalFrames 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.GetActiveInternalFrames Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type:
- apiref
ms.openlocfilehash: f228dd84708478bb364ac09407a68df3e8d971b6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800983"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a><span data-ttu-id="e12fb-103">ICorDebugThread3::GetActiveInternalFrames 메서드</span><span class="sxs-lookup"><span data-stu-id="e12fb-103">ICorDebugThread3::GetActiveInternalFrames Method</span></span>

<span data-ttu-id="e12fb-104">스택에서 내부 프레임 ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) 개체)의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12fb-104">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e12fb-105">구문</span><span class="sxs-lookup"><span data-stu-id="e12fb-105">Syntax</span></span>  
  
```cpp
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a><span data-ttu-id="e12fb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e12fb-106">Parameters</span></span>  

 `cInternalFrames`  
 <span data-ttu-id="e12fb-107">진행 에 예상 되는 내부 프레임의 수입니다 `ppInternalFrames` .</span><span class="sxs-lookup"><span data-stu-id="e12fb-107">[in] The number of internal frames expected in `ppInternalFrames`.</span></span>  
  
 `pcInternalFrames`  
 <span data-ttu-id="e12fb-108">제한이 `ULONG32` 스택의 내부 프레임 수를 포함 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e12fb-108">[out] A pointer to a `ULONG32` that contains the number of internal frames on the stack.</span></span>  
  
 `ppInternalFrames`  
 <span data-ttu-id="e12fb-109">[in, out] 스택의 내부 프레임 배열 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e12fb-109">[in, out] A pointer to the address of an array of internal frames on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e12fb-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="e12fb-110">Return Value</span></span>  

 <span data-ttu-id="e12fb-111">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e12fb-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e12fb-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e12fb-112">HRESULT</span></span>|<span data-ttu-id="e12fb-113">설명</span><span class="sxs-lookup"><span data-stu-id="e12fb-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e12fb-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="e12fb-114">S_OK</span></span>|<span data-ttu-id="e12fb-115">[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) 개체를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="e12fb-115">The [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) object was successfully created.</span></span>|  
|<span data-ttu-id="e12fb-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e12fb-116">E_INVALIDARG</span></span>|<span data-ttu-id="e12fb-117">`cInternalFrames` 가 0이 아니고 `ppInternalFrames` 가 `null` 이거나 `pcInternalFrames` 가 `null` 입니다.</span><span class="sxs-lookup"><span data-stu-id="e12fb-117">`cInternalFrames` is not zero and `ppInternalFrames` is `null`, or `pcInternalFrames` is `null`.</span></span>|  
|<span data-ttu-id="e12fb-118">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="e12fb-118">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="e12fb-119">`ppInternalFrames` 가 내부 프레임 수보다 작은 경우</span><span class="sxs-lookup"><span data-stu-id="e12fb-119">`ppInternalFrames` is smaller than the count of internal frames.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="e12fb-120">예외</span><span class="sxs-lookup"><span data-stu-id="e12fb-120">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e12fb-121">설명</span><span class="sxs-lookup"><span data-stu-id="e12fb-121">Remarks</span></span>  

 <span data-ttu-id="e12fb-122">내부 프레임은 런타임에서 임시 데이터를 저장 하기 위해 스택에 푸시되는 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="e12fb-122">Internal frames are data structures pushed onto the stack by the runtime to store temporary data.</span></span>  
  
 <span data-ttu-id="e12fb-123">을 처음 호출할 때 `GetActiveInternalFrames` `cInternalFrames` 매개 변수를 0 (영)으로 설정 하 고 `ppInternalFrames` 매개 변수를 null로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12fb-123">When you first call `GetActiveInternalFrames`, you should set the `cInternalFrames` parameter to 0 (zero), and the `ppInternalFrames` parameter to null.</span></span> <span data-ttu-id="e12fb-124">`GetActiveInternalFrames`처음 반환 될 때 `pcInternalFrames` 스택에 있는 내부 프레임의 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12fb-124">When `GetActiveInternalFrames` first returns, `pcInternalFrames` contains the count of the internal frames on the stack.</span></span>  
  
 <span data-ttu-id="e12fb-125">`GetActiveInternalFrames` 그런 다음를 두 번째로 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12fb-125">`GetActiveInternalFrames` should then be called a second time.</span></span> <span data-ttu-id="e12fb-126">매개 변수에서 적절 한 개수 ( `pcInternalFrames` )를 전달 `cInternalFrames` 하 고에서 적절 하 게 크기가 지정 된 배열에 대 한 포인터를 지정 해야 합니다 `ppInternalFrames` .</span><span class="sxs-lookup"><span data-stu-id="e12fb-126">You should pass the proper count (`pcInternalFrames`) in the `cInternalFrames` parameter, and specify a pointer to an appropriately sized array in `ppInternalFrames`.</span></span>  
  
 <span data-ttu-id="e12fb-127">[ICorDebugStackWalk:: GetFrame](icordebugthread3-getactiveinternalframes-method.md) 메서드를 사용 하 여 실제 스택 프레임을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e12fb-127">Use the [ICorDebugStackWalk::GetFrame](icordebugthread3-getactiveinternalframes-method.md) method to return actual stack frames.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e12fb-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e12fb-128">Requirements</span></span>  

 <span data-ttu-id="e12fb-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e12fb-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e12fb-130">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e12fb-130">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e12fb-131">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e12fb-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e12fb-132">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e12fb-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e12fb-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e12fb-133">See also</span></span>

- [<span data-ttu-id="e12fb-134">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e12fb-134">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e12fb-135">디버깅</span><span class="sxs-lookup"><span data-stu-id="e12fb-135">Debugging</span></span>](index.md)
