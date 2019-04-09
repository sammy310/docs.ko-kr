---
title: ICorDebugNativeFrame2::IsChild 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsChild Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsChild
helpviewer_keywords:
- IsChild method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsChild method [.NET Framework debugging]
ms.assetid: 9e2aae09-49cb-4fbd-81e5-e29cd864a88b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9503c12da9e98fbd43f3904aad25c5d10655cec2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075563"
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="52c8a-102">ICorDebugNativeFrame2::IsChild 메서드</span><span class="sxs-lookup"><span data-stu-id="52c8a-102">ICorDebugNativeFrame2::IsChild Method</span></span>
<span data-ttu-id="52c8a-103">현재 프레임 자식 프레임 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="52c8a-103">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52c8a-104">구문</span><span class="sxs-lookup"><span data-stu-id="52c8a-104">Syntax</span></span>  
  
```  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52c8a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="52c8a-105">Parameters</span></span>  
 `pIsChild`  
 <span data-ttu-id="52c8a-106">[out] 현재 프레임 자식 프레임을 여부를 지정 하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="52c8a-106">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52c8a-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="52c8a-107">Return Value</span></span>  
 <span data-ttu-id="52c8a-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="52c8a-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="52c8a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="52c8a-109">HRESULT</span></span>|<span data-ttu-id="52c8a-110">설명</span><span class="sxs-lookup"><span data-stu-id="52c8a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="52c8a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="52c8a-111">S_OK</span></span>|<span data-ttu-id="52c8a-112">자식 상태가 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="52c8a-112">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="52c8a-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="52c8a-113">E_FAIL</span></span>|<span data-ttu-id="52c8a-114">자식 상태를 반환 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="52c8a-114">The child status could not be returned.</span></span>|  
|<span data-ttu-id="52c8a-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="52c8a-115">E_INVALIDARG</span></span>|`pIsChild` <span data-ttu-id="52c8a-116">null입니다.</span><span class="sxs-lookup"><span data-stu-id="52c8a-116">is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="52c8a-117">예외</span><span class="sxs-lookup"><span data-stu-id="52c8a-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52c8a-118">설명</span><span class="sxs-lookup"><span data-stu-id="52c8a-118">Remarks</span></span>  
 <span data-ttu-id="52c8a-119">합니다 `IsChild` 메서드가 반환 되는 `true` 프레임 개체 메서드를 호출 하는 다른 프레임의 자식인 경우.</span><span class="sxs-lookup"><span data-stu-id="52c8a-119">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="52c8a-120">이 경우 사용 합니다 [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) 프레임 부모 인지 여부를 확인 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="52c8a-120">If this is the case, use the [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52c8a-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="52c8a-121">Requirements</span></span>  
 <span data-ttu-id="52c8a-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="52c8a-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52c8a-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52c8a-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52c8a-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52c8a-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="52c8a-125">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="52c8a-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="52c8a-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="52c8a-126">See also</span></span>

- [<span data-ttu-id="52c8a-127">ICorDebugNativeFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52c8a-127">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="52c8a-128">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52c8a-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="52c8a-129">디버깅</span><span class="sxs-lookup"><span data-stu-id="52c8a-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
