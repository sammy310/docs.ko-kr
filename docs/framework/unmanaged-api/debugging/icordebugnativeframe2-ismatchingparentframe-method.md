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
ms.openlocfilehash: 213bee96531fa0bbc9bf0ae76b2505019833abfc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724704"
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a><span data-ttu-id="c37a3-102">ICorDebugNativeFrame2::IsMatchingParentFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="c37a3-102">ICorDebugNativeFrame2::IsMatchingParentFrame Method</span></span>

<span data-ttu-id="c37a3-103">지정 된 프레임이 현재 프레임의 부모 인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c37a3-103">Determines whether the specified frame is the parent of the current frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c37a3-104">구문</span><span class="sxs-lookup"><span data-stu-id="c37a3-104">Syntax</span></span>  
  
```cpp  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c37a3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c37a3-105">Parameters</span></span>  

 `pPotentialParentFrame`  
 <span data-ttu-id="c37a3-106">진행 부모 상태를 평가 하려는 프레임 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c37a3-106">[in] A pointer to the frame object that you want to evaluate for parent status.</span></span>  
  
 `pIsParent`  
 <span data-ttu-id="c37a3-107">[out] `true` `pPotentialParentFrame` 가 현재 프레임의 부모 이면이 고, 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="c37a3-107">[out] `true` if `pPotentialParentFrame` is the current frame’s parent; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c37a3-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="c37a3-108">Return Value</span></span>  

 <span data-ttu-id="c37a3-109">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c37a3-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c37a3-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c37a3-110">HRESULT</span></span>|<span data-ttu-id="c37a3-111">설명</span><span class="sxs-lookup"><span data-stu-id="c37a3-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c37a3-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c37a3-112">S_OK</span></span>|<span data-ttu-id="c37a3-113">부모 상태가 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c37a3-113">The parent status was successfully returned.</span></span>|  
|<span data-ttu-id="c37a3-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c37a3-114">E_FAIL</span></span>|<span data-ttu-id="c37a3-115">부모 상태를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c37a3-115">The parent status could not be returned.</span></span>|  
|<span data-ttu-id="c37a3-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c37a3-116">E_INVALIDARG</span></span>|<span data-ttu-id="c37a3-117">`pPotentialParentFrame` 또는 `pIsParent`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="c37a3-117">`pPotentialParentFrame` or `pIsParent` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="c37a3-118">예외</span><span class="sxs-lookup"><span data-stu-id="c37a3-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c37a3-119">설명</span><span class="sxs-lookup"><span data-stu-id="c37a3-119">Remarks</span></span>  

 <span data-ttu-id="c37a3-120">`IsMatchingParentFrame``true`메서드에 전달 하는 프레임 개체가 메서드가 호출 된 프레임 개체의 부모 이면를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c37a3-120">`IsMatchingParentFrame` returns `true` if the frame object you pass to the method is the parent of the frame object on which the method was called.</span></span> <span data-ttu-id="c37a3-121">지정 된 프레임의 자식이 아닌 프레임에서 메서드를 호출 하는 경우 오류를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c37a3-121">If you call the method on a frame that is not a child of the specified frame, it returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c37a3-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c37a3-122">Requirements</span></span>  

 <span data-ttu-id="c37a3-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c37a3-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c37a3-124">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c37a3-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c37a3-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c37a3-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c37a3-126">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c37a3-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c37a3-127">참조</span><span class="sxs-lookup"><span data-stu-id="c37a3-127">See also</span></span>

- [<span data-ttu-id="c37a3-128">ICorDebugNativeFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c37a3-128">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="c37a3-129">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c37a3-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c37a3-130">디버깅</span><span class="sxs-lookup"><span data-stu-id="c37a3-130">Debugging</span></span>](index.md)
