---
description: '자세히 알아보기: ICorDebugInternalFrame2:: IsCloserToLeaf 메서드'
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
ms.openlocfilehash: d773f8670f600a5bcd2a8dad7f23fe243195957c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801282"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="94c01-103">ICorDebugInternalFrame2::IsCloserToLeaf 메서드</span><span class="sxs-lookup"><span data-stu-id="94c01-103">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>

<span data-ttu-id="94c01-104">`this`내부 프레임이 지정 된 ICorDebugFrame 개체 보다 리프에 가까이 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c01-104">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94c01-105">구문</span><span class="sxs-lookup"><span data-stu-id="94c01-105">Syntax</span></span>  
  
```cpp  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94c01-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="94c01-106">Parameters</span></span>  

 `pFrameToCompare`  
 <span data-ttu-id="94c01-107">진행 비교 개체에 대 한 포인터 `ICorDebugFrame` 입니다.</span><span class="sxs-lookup"><span data-stu-id="94c01-107">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="94c01-108">[out] `true` `this` 내부 프레임이에 지정 된 프레임 보다 리프에 가까이 있으면 `pFrameToCompare` 이 고, 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="94c01-108">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94c01-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="94c01-109">Return Value</span></span>  

 <span data-ttu-id="94c01-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="94c01-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="94c01-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="94c01-111">HRESULT</span></span>|<span data-ttu-id="94c01-112">설명</span><span class="sxs-lookup"><span data-stu-id="94c01-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="94c01-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="94c01-113">S_OK</span></span>|<span data-ttu-id="94c01-114">비교가 성공적으로 수행 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="94c01-114">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="94c01-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="94c01-115">E_FAIL</span></span>|<span data-ttu-id="94c01-116">비교를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94c01-116">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="94c01-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="94c01-117">E_INVALIDARG</span></span>|<span data-ttu-id="94c01-118">`pFrameToCompare` 또는 `pIsCloser`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="94c01-118">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94c01-119">설명</span><span class="sxs-lookup"><span data-stu-id="94c01-119">Remarks</span></span>  

 <span data-ttu-id="94c01-120">`IsCloserToLeaf` 를 사용 하 여 스택의 다른 프레임으로 내부 프레임을 인터리브 하는 정책을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94c01-120">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94c01-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="94c01-121">Requirements</span></span>  

 <span data-ttu-id="94c01-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94c01-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94c01-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94c01-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94c01-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94c01-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94c01-125">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94c01-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94c01-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94c01-126">See also</span></span>

- [<span data-ttu-id="94c01-127">ICorDebugInternalFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94c01-127">ICorDebugInternalFrame2 Interface</span></span>](icordebuginternalframe2-interface.md)
- [<span data-ttu-id="94c01-128">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94c01-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="94c01-129">디버깅</span><span class="sxs-lookup"><span data-stu-id="94c01-129">Debugging</span></span>](index.md)
