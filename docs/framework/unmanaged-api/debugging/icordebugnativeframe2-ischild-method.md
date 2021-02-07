---
description: '자세히 알아보기: ICorDebugNativeFrame2:: IsChild 메서드'
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
ms.openlocfilehash: 7c698c5a49ee445b4ba9c591c96f700f86a86c32
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722297"
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="d7e25-103">ICorDebugNativeFrame2::IsChild 메서드</span><span class="sxs-lookup"><span data-stu-id="d7e25-103">ICorDebugNativeFrame2::IsChild Method</span></span>

<span data-ttu-id="d7e25-104">현재 프레임이 자식 프레임 인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e25-104">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7e25-105">구문</span><span class="sxs-lookup"><span data-stu-id="d7e25-105">Syntax</span></span>  
  
```cpp  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7e25-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d7e25-106">Parameters</span></span>  

 `pIsChild`  
 <span data-ttu-id="d7e25-107">제한이 현재 프레임이 자식 프레임 인지 여부를 지정 하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d7e25-107">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7e25-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="d7e25-108">Return Value</span></span>  

 <span data-ttu-id="d7e25-109">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e25-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d7e25-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d7e25-110">HRESULT</span></span>|<span data-ttu-id="d7e25-111">설명</span><span class="sxs-lookup"><span data-stu-id="d7e25-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d7e25-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d7e25-112">S_OK</span></span>|<span data-ttu-id="d7e25-113">자식 상태가 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e25-113">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="d7e25-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d7e25-114">E_FAIL</span></span>|<span data-ttu-id="d7e25-115">자식 상태를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e25-115">The child status could not be returned.</span></span>|  
|<span data-ttu-id="d7e25-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d7e25-116">E_INVALIDARG</span></span>|<span data-ttu-id="d7e25-117">`pIsChild`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="d7e25-117">`pIsChild` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="d7e25-118">예외</span><span class="sxs-lookup"><span data-stu-id="d7e25-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7e25-119">설명</span><span class="sxs-lookup"><span data-stu-id="d7e25-119">Remarks</span></span>  

 <span data-ttu-id="d7e25-120">메서드는 `IsChild` `true` 메서드를 호출 하는 프레임 개체가 다른 프레임의 자식인 경우를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e25-120">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="d7e25-121">이 경우 [IsMatchingParentFrame](icordebugnativeframe2-ismatchingparentframe-method.md) 메서드를 사용 하 여 프레임이 부모 인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e25-121">If this is the case, use the [IsMatchingParentFrame](icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7e25-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7e25-122">Requirements</span></span>  

 <span data-ttu-id="d7e25-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7e25-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7e25-124">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7e25-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7e25-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7e25-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7e25-126">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7e25-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7e25-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7e25-127">See also</span></span>

- [<span data-ttu-id="d7e25-128">ICorDebugNativeFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7e25-128">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="d7e25-129">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7e25-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d7e25-130">디버깅</span><span class="sxs-lookup"><span data-stu-id="d7e25-130">Debugging</span></span>](index.md)
