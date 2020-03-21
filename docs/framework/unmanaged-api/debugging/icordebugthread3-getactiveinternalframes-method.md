---
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
ms.openlocfilehash: 680af5afa3ebef5bcaf9e34580e421dcc8093aaf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178461"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a><span data-ttu-id="6f042-102">ICorDebugThread3::GetActiveInternalFrames 메서드</span><span class="sxs-lookup"><span data-stu-id="6f042-102">ICorDebugThread3::GetActiveInternalFrames Method</span></span>
<span data-ttu-id="6f042-103">스택에서 내부[프레임(ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) 개체)의 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6f042-103">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f042-104">구문</span><span class="sxs-lookup"><span data-stu-id="6f042-104">Syntax</span></span>  
  
```cpp
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f042-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6f042-105">Parameters</span></span>  
 `cInternalFrames`  
 <span data-ttu-id="6f042-106">【인】 에서 예상되는 내부 프레임 `ppInternalFrames`수입니다.</span><span class="sxs-lookup"><span data-stu-id="6f042-106">[in] The number of internal frames expected in `ppInternalFrames`.</span></span>  
  
 `pcInternalFrames`  
 <span data-ttu-id="6f042-107">【아웃】 스택의 내부 `ULONG32` 프레임 수를 포함하는 a에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6f042-107">[out] A pointer to a `ULONG32` that contains the number of internal frames on the stack.</span></span>  
  
 `ppInternalFrames`  
 <span data-ttu-id="6f042-108">【인, 아웃】 스택의 내부 프레임 배열주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6f042-108">[in, out] A pointer to the address of an array of internal frames on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f042-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="6f042-109">Return Value</span></span>  
 <span data-ttu-id="6f042-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6f042-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6f042-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6f042-111">HRESULT</span></span>|<span data-ttu-id="6f042-112">Description</span><span class="sxs-lookup"><span data-stu-id="6f042-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6f042-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="6f042-113">S_OK</span></span>|<span data-ttu-id="6f042-114">[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) 개체가 성공적으로 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="6f042-114">The [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) object was successfully created.</span></span>|  
|<span data-ttu-id="6f042-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6f042-115">E_INVALIDARG</span></span>|<span data-ttu-id="6f042-116">`cInternalFrames`0이 `ppInternalFrames` 아니며 `null`은 `pcInternalFrames` . `null`</span><span class="sxs-lookup"><span data-stu-id="6f042-116">`cInternalFrames` is not zero and `ppInternalFrames` is `null`, or `pcInternalFrames` is `null`.</span></span>|  
|<span data-ttu-id="6f042-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="6f042-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="6f042-118">`ppInternalFrames`는 내부 프레임의 개수보다 작습니다.</span><span class="sxs-lookup"><span data-stu-id="6f042-118">`ppInternalFrames` is smaller than the count of internal frames.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="6f042-119">예외</span><span class="sxs-lookup"><span data-stu-id="6f042-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f042-120">설명</span><span class="sxs-lookup"><span data-stu-id="6f042-120">Remarks</span></span>  
 <span data-ttu-id="6f042-121">내부 프레임은 임시 데이터를 저장하기 위해 런타임에 의해 스택에 푸시된 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="6f042-121">Internal frames are data structures pushed onto the stack by the runtime to store temporary data.</span></span>  
  
 <span data-ttu-id="6f042-122">호출할 `GetActiveInternalFrames`때 매개 변수를 `cInternalFrames` 0(0)으로 설정하고 `ppInternalFrames` 매개 변수를 null로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f042-122">When you first call `GetActiveInternalFrames`, you should set the `cInternalFrames` parameter to 0 (zero), and the `ppInternalFrames` parameter to null.</span></span> <span data-ttu-id="6f042-123">처음 `GetActiveInternalFrames` 반환할 `pcInternalFrames` 때 스택의 내부 프레임 수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f042-123">When `GetActiveInternalFrames` first returns, `pcInternalFrames` contains the count of the internal frames on the stack.</span></span>  
  
 <span data-ttu-id="6f042-124">`GetActiveInternalFrames`두 번째로 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f042-124">`GetActiveInternalFrames` should then be called a second time.</span></span> <span data-ttu-id="6f042-125">매개 변수에서 적절한`pcInternalFrames`개수 () 를 전달하고 에서 적절한 크기의 배열에 대한 포인터를 지정해야 합니다. `ppInternalFrames` `cInternalFrames`</span><span class="sxs-lookup"><span data-stu-id="6f042-125">You should pass the proper count (`pcInternalFrames`) in the `cInternalFrames` parameter, and specify a pointer to an appropriately sized array in `ppInternalFrames`.</span></span>  
  
 <span data-ttu-id="6f042-126">[ICorDebugStackWalk::GetFrame](icordebugthread3-getactiveinternalframes-method.md) 메서드를 사용하여 실제 스택 프레임을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6f042-126">Use the [ICorDebugStackWalk::GetFrame](icordebugthread3-getactiveinternalframes-method.md) method to return actual stack frames.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f042-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6f042-127">Requirements</span></span>  
 <span data-ttu-id="6f042-128">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f042-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f042-129">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f042-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f042-130">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f042-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f042-131">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f042-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f042-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f042-132">See also</span></span>

- [<span data-ttu-id="6f042-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6f042-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="6f042-134">디버깅</span><span class="sxs-lookup"><span data-stu-id="6f042-134">Debugging</span></span>](index.md)
