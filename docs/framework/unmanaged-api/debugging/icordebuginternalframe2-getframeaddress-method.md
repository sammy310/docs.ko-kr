---
description: '자세히 알아보기: ICorDebugInternalFrame2:: Get프레임 주소 메서드'
title: ICorDebugInternalFrame2::GetFrameAddress 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.GetFrameAddress Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type:
- apiref
ms.openlocfilehash: bb745424680c5b9a5277badfbe2d96db46e2e3d8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791116"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a><span data-ttu-id="2bcaf-103">ICorDebugInternalFrame2::GetFrameAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="2bcaf-103">ICorDebugInternalFrame2::GetFrameAddress Method</span></span>

<span data-ttu-id="2bcaf-104">내부 프레임의 스택 주소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bcaf-104">Returns the stack address of the internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bcaf-105">구문</span><span class="sxs-lookup"><span data-stu-id="2bcaf-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bcaf-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2bcaf-106">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="2bcaf-107">제한이 `CORDB_ADDRESS` 내부 프레임의에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2bcaf-107">[out] Pointer to the `CORDB_ADDRESS` for the internal frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2bcaf-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="2bcaf-108">Return Value</span></span>  

 <span data-ttu-id="2bcaf-109">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2bcaf-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2bcaf-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2bcaf-110">HRESULT</span></span>|<span data-ttu-id="2bcaf-111">설명</span><span class="sxs-lookup"><span data-stu-id="2bcaf-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2bcaf-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2bcaf-112">S_OK</span></span>|<span data-ttu-id="2bcaf-113">내부 프레임의 주소가 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2bcaf-113">The address of the internal frame was successfully returned.</span></span>|  
|<span data-ttu-id="2bcaf-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2bcaf-114">E_FAIL</span></span>|<span data-ttu-id="2bcaf-115">내부 프레임의 주소를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2bcaf-115">The address of the internal frame could not be returned.</span></span>|  
|<span data-ttu-id="2bcaf-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2bcaf-116">E_INVALIDARG</span></span>|<span data-ttu-id="2bcaf-117">`pAddress`이(가) `null`인 경우</span><span class="sxs-lookup"><span data-stu-id="2bcaf-117">`pAddress` is `null`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2bcaf-118">설명</span><span class="sxs-lookup"><span data-stu-id="2bcaf-118">Remarks</span></span>  

 <span data-ttu-id="2bcaf-119">에서 반환 된 값을 `pAddress` 사용 하 여 스택의 다른 프레임을 기준으로 내부 프레임의 위치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bcaf-119">The value returned in `pAddress` can be used to determine the location of the internal frame relative to other frames on the stack.</span></span> <span data-ttu-id="2bcaf-120">IA-64 기반 컴퓨터의 경우에도 내부 프레임은 스택에만 있고 백업 저장소에는 해당 하는 포인터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2bcaf-120">Even on IA-64-based computers, the internal frame lives on the stack only, and there is no corresponding pointer to a backing store.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bcaf-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2bcaf-121">Requirements</span></span>  

 <span data-ttu-id="2bcaf-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2bcaf-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bcaf-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2bcaf-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2bcaf-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bcaf-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bcaf-125">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bcaf-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bcaf-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2bcaf-126">See also</span></span>

- [<span data-ttu-id="2bcaf-127">ICorDebugInternalFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2bcaf-127">ICorDebugInternalFrame2 Interface</span></span>](icordebuginternalframe2-interface.md)
- [<span data-ttu-id="2bcaf-128">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2bcaf-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2bcaf-129">디버깅</span><span class="sxs-lookup"><span data-stu-id="2bcaf-129">Debugging</span></span>](index.md)
