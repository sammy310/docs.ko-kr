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
ms.openlocfilehash: 759ba7bd46f8231143e743aa5ffcabffeb99c3b6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205105"
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="1b742-102">ICorDebugNativeFrame2::IsChild 메서드</span><span class="sxs-lookup"><span data-stu-id="1b742-102">ICorDebugNativeFrame2::IsChild Method</span></span>
<span data-ttu-id="1b742-103">현재 프레임이 자식 프레임 인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b742-103">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b742-104">구문</span><span class="sxs-lookup"><span data-stu-id="1b742-104">Syntax</span></span>  
  
```cpp  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b742-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1b742-105">Parameters</span></span>  
 `pIsChild`  
 <span data-ttu-id="1b742-106">제한이 현재 프레임이 자식 프레임 인지 여부를 지정 하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1b742-106">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b742-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="1b742-107">Return Value</span></span>  
 <span data-ttu-id="1b742-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1b742-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1b742-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1b742-109">HRESULT</span></span>|<span data-ttu-id="1b742-110">설명</span><span class="sxs-lookup"><span data-stu-id="1b742-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1b742-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1b742-111">S_OK</span></span>|<span data-ttu-id="1b742-112">자식 상태가 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1b742-112">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="1b742-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1b742-113">E_FAIL</span></span>|<span data-ttu-id="1b742-114">자식 상태를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b742-114">The child status could not be returned.</span></span>|  
|<span data-ttu-id="1b742-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1b742-115">E_INVALIDARG</span></span>|<span data-ttu-id="1b742-116">`pIsChild`가 null인 경우</span><span class="sxs-lookup"><span data-stu-id="1b742-116">`pIsChild` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="1b742-117">예외</span><span class="sxs-lookup"><span data-stu-id="1b742-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b742-118">설명</span><span class="sxs-lookup"><span data-stu-id="1b742-118">Remarks</span></span>  
 <span data-ttu-id="1b742-119">메서드는 `IsChild` `true` 메서드를 호출 하는 프레임 개체가 다른 프레임의 자식인 경우를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b742-119">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="1b742-120">이 경우 [IsMatchingParentFrame](icordebugnativeframe2-ismatchingparentframe-method.md) 메서드를 사용 하 여 프레임이 부모 인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b742-120">If this is the case, use the [IsMatchingParentFrame](icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b742-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1b742-121">Requirements</span></span>  
 <span data-ttu-id="1b742-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1b742-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b742-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b742-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b742-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b742-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b742-125">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b742-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b742-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b742-126">See also</span></span>

- [<span data-ttu-id="1b742-127">ICorDebugNativeFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1b742-127">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="1b742-128">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1b742-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="1b742-129">디버깅</span><span class="sxs-lookup"><span data-stu-id="1b742-129">Debugging</span></span>](index.md)
