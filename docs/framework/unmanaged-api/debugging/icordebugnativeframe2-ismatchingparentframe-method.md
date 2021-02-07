---
description: '자세히 알아보기: ICorDebugNativeFrame2:: IsMatchingParentFrame 메서드'
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
ms.openlocfilehash: 6dff1cb7f5205ad742ac4b886f72938dd28bd88f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722206"
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a><span data-ttu-id="c6048-103">ICorDebugNativeFrame2::IsMatchingParentFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="c6048-103">ICorDebugNativeFrame2::IsMatchingParentFrame Method</span></span>

<span data-ttu-id="c6048-104">지정 된 프레임이 현재 프레임의 부모 인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6048-104">Determines whether the specified frame is the parent of the current frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6048-105">구문</span><span class="sxs-lookup"><span data-stu-id="c6048-105">Syntax</span></span>  
  
```cpp  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6048-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c6048-106">Parameters</span></span>  

 `pPotentialParentFrame`  
 <span data-ttu-id="c6048-107">진행 부모 상태를 평가 하려는 프레임 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c6048-107">[in] A pointer to the frame object that you want to evaluate for parent status.</span></span>  
  
 `pIsParent`  
 <span data-ttu-id="c6048-108">[out] `true` `pPotentialParentFrame` 가 현재 프레임의 부모 이면이 고, 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="c6048-108">[out] `true` if `pPotentialParentFrame` is the current frame’s parent; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6048-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="c6048-109">Return Value</span></span>  

 <span data-ttu-id="c6048-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c6048-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c6048-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c6048-111">HRESULT</span></span>|<span data-ttu-id="c6048-112">설명</span><span class="sxs-lookup"><span data-stu-id="c6048-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c6048-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c6048-113">S_OK</span></span>|<span data-ttu-id="c6048-114">부모 상태가 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c6048-114">The parent status was successfully returned.</span></span>|  
|<span data-ttu-id="c6048-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c6048-115">E_FAIL</span></span>|<span data-ttu-id="c6048-116">부모 상태를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c6048-116">The parent status could not be returned.</span></span>|  
|<span data-ttu-id="c6048-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c6048-117">E_INVALIDARG</span></span>|<span data-ttu-id="c6048-118">`pPotentialParentFrame` 또는 `pIsParent`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="c6048-118">`pPotentialParentFrame` or `pIsParent` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="c6048-119">예외</span><span class="sxs-lookup"><span data-stu-id="c6048-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6048-120">설명</span><span class="sxs-lookup"><span data-stu-id="c6048-120">Remarks</span></span>  

 <span data-ttu-id="c6048-121">`IsMatchingParentFrame``true`메서드에 전달 하는 프레임 개체가 메서드가 호출 된 프레임 개체의 부모 이면를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6048-121">`IsMatchingParentFrame` returns `true` if the frame object you pass to the method is the parent of the frame object on which the method was called.</span></span> <span data-ttu-id="c6048-122">지정 된 프레임의 자식이 아닌 프레임에서 메서드를 호출 하는 경우 오류를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6048-122">If you call the method on a frame that is not a child of the specified frame, it returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6048-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6048-123">Requirements</span></span>  

 <span data-ttu-id="c6048-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6048-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6048-125">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6048-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6048-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6048-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6048-127">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6048-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6048-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6048-128">See also</span></span>

- [<span data-ttu-id="c6048-129">ICorDebugNativeFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6048-129">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="c6048-130">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6048-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c6048-131">디버깅</span><span class="sxs-lookup"><span data-stu-id="c6048-131">Debugging</span></span>](index.md)
