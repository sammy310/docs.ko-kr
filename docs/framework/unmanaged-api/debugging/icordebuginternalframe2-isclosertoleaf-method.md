---
title: ICorDebugInternalFrame2::IsCloserToLeaf 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96deee943f6a4c636a52b41c8f4c2fda86c6bd18
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493721"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="35fbf-102">ICorDebugInternalFrame2::IsCloserToLeaf 메서드</span><span class="sxs-lookup"><span data-stu-id="35fbf-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="35fbf-103">확인 여부는 `this` 내부 프레임에 더 가까운 리프 지정된 ICorDebugFrame 개체 보다 합니다.</span><span class="sxs-lookup"><span data-stu-id="35fbf-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35fbf-104">구문</span><span class="sxs-lookup"><span data-stu-id="35fbf-104">Syntax</span></span>  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35fbf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="35fbf-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="35fbf-106">[in] 비교에 대 한 포인터 `ICorDebugFrame` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="35fbf-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="35fbf-107">[out] `true` 경우는 `this` 내부 프레임 보다에 더 가까운 리프 지정한 프레임 `pFrameToCompare`이 고, 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="35fbf-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35fbf-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="35fbf-108">Return Value</span></span>  
 <span data-ttu-id="35fbf-109">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="35fbf-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="35fbf-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="35fbf-110">HRESULT</span></span>|<span data-ttu-id="35fbf-111">설명</span><span class="sxs-lookup"><span data-stu-id="35fbf-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="35fbf-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="35fbf-112">S_OK</span></span>|<span data-ttu-id="35fbf-113">비교는 성공적으로 수행 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="35fbf-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="35fbf-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="35fbf-114">E_FAIL</span></span>|<span data-ttu-id="35fbf-115">비교를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35fbf-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="35fbf-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="35fbf-116">E_INVALIDARG</span></span>|<span data-ttu-id="35fbf-117">`pFrameToCompare` 또는 `pIsCloser`이 null입니다.</span><span class="sxs-lookup"><span data-stu-id="35fbf-117">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35fbf-118">설명</span><span class="sxs-lookup"><span data-stu-id="35fbf-118">Remarks</span></span>  
 <span data-ttu-id="35fbf-119">`IsCloserToLeaf` 인터리빙 스택의 다른 프레임을 사용 하 여 내부 프레임에 대 한 정책을 구현 하려면 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35fbf-119">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35fbf-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="35fbf-120">Requirements</span></span>  
 <span data-ttu-id="35fbf-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="35fbf-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35fbf-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35fbf-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35fbf-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35fbf-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35fbf-124">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35fbf-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35fbf-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="35fbf-125">See also</span></span>
- [<span data-ttu-id="35fbf-126">ICorDebugInternalFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35fbf-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [<span data-ttu-id="35fbf-127">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35fbf-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="35fbf-128">디버깅</span><span class="sxs-lookup"><span data-stu-id="35fbf-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
