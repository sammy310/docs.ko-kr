---
title: ICorDebugNativeFrame2::IsMatchingParentFrame 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsMatchingParentFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsMatchingParentFrame
helpviewer_keywords:
- IsMatchingParentFrame method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsMatchingParentFrame method [.NET Framework debugging]
ms.assetid: d2ca20db-df22-4528-a0dd-a09ea62c8998
topic_type:
- apiref
ms.openlocfilehash: aa06b7db6b7371e66853ed242f5e118fb5e5ff0c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096196"
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a><span data-ttu-id="e5505-102">ICorDebugNativeFrame2::IsMatchingParentFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="e5505-102">ICorDebugNativeFrame2::IsMatchingParentFrame Method</span></span>
<span data-ttu-id="e5505-103">지정 된 프레임이 현재 프레임의 부모 인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5505-103">Determines whether the specified frame is the parent of the current frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5505-104">구문</span><span class="sxs-lookup"><span data-stu-id="e5505-104">Syntax</span></span>  
  
```cpp  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5505-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e5505-105">Parameters</span></span>  
 `pPotentialParentFrame`  
 <span data-ttu-id="e5505-106">진행 부모 상태를 평가 하려는 프레임 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e5505-106">[in] A pointer to the frame object that you want to evaluate for parent status.</span></span>  
  
 `pIsParent`  
 <span data-ttu-id="e5505-107">[out] 현재 프레임의 부모 `pPotentialParentFrame` 이면를 `true` 합니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="e5505-107">[out] `true` if `pPotentialParentFrame` is the current frame’s parent; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5505-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="e5505-108">Return Value</span></span>  
 <span data-ttu-id="e5505-109">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e5505-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e5505-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e5505-110">HRESULT</span></span>|<span data-ttu-id="e5505-111">설명</span><span class="sxs-lookup"><span data-stu-id="e5505-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e5505-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="e5505-112">S_OK</span></span>|<span data-ttu-id="e5505-113">부모 상태가 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e5505-113">The parent status was successfully returned.</span></span>|  
|<span data-ttu-id="e5505-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e5505-114">E_FAIL</span></span>|<span data-ttu-id="e5505-115">부모 상태를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5505-115">The parent status could not be returned.</span></span>|  
|<span data-ttu-id="e5505-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e5505-116">E_INVALIDARG</span></span>|<span data-ttu-id="e5505-117">`pPotentialParentFrame` 또는 `pIsParent`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="e5505-117">`pPotentialParentFrame` or `pIsParent` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="e5505-118">예외</span><span class="sxs-lookup"><span data-stu-id="e5505-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5505-119">주의</span><span class="sxs-lookup"><span data-stu-id="e5505-119">Remarks</span></span>  
 <span data-ttu-id="e5505-120">메서드에 전달 하는 프레임 개체가 메서드가 호출 된 프레임 개체의 부모인 경우 `IsMatchingParentFrame` `true`를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5505-120">`IsMatchingParentFrame` returns `true` if the frame object you pass to the method is the parent of the frame object on which the method was called.</span></span> <span data-ttu-id="e5505-121">지정 된 프레임의 자식이 아닌 프레임에서 메서드를 호출 하는 경우 오류를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5505-121">If you call the method on a frame that is not a child of the specified frame, it returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5505-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5505-122">Requirements</span></span>  
 <span data-ttu-id="e5505-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5505-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5505-124">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5505-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5505-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5505-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5505-126">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5505-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5505-127">참조</span><span class="sxs-lookup"><span data-stu-id="e5505-127">See also</span></span>

- [<span data-ttu-id="e5505-128">ICorDebugNativeFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5505-128">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="e5505-129">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5505-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="e5505-130">디버깅</span><span class="sxs-lookup"><span data-stu-id="e5505-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
