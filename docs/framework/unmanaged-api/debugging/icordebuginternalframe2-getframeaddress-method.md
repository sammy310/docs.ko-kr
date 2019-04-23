---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c30115a23f7f73662c9b3f4f4a09d45478ad687
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187293"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a><span data-ttu-id="0ef0d-102">ICorDebugInternalFrame2::GetFrameAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="0ef0d-102">ICorDebugInternalFrame2::GetFrameAddress Method</span></span>
<span data-ttu-id="0ef0d-103">내부 프레임의 스택 주소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef0d-103">Returns the stack address of the internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ef0d-104">구문</span><span class="sxs-lookup"><span data-stu-id="0ef0d-104">Syntax</span></span>  
  
```  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ef0d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0ef0d-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="0ef0d-106">[out] 에 대 한 포인터를 `CORDB_ADDRESS` 내부 프레임에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef0d-106">[out] Pointer to the `CORDB_ADDRESS` for the internal frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ef0d-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="0ef0d-107">Return Value</span></span>  
 <span data-ttu-id="0ef0d-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef0d-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0ef0d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0ef0d-109">HRESULT</span></span>|<span data-ttu-id="0ef0d-110">설명</span><span class="sxs-lookup"><span data-stu-id="0ef0d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0ef0d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0ef0d-111">S_OK</span></span>|<span data-ttu-id="0ef0d-112">내부 프레임의 주소 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0ef0d-112">The address of the internal frame was successfully returned.</span></span>|  
|<span data-ttu-id="0ef0d-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0ef0d-113">E_FAIL</span></span>|<span data-ttu-id="0ef0d-114">내부 프레임의 주소를 반환 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="0ef0d-114">The address of the internal frame could not be returned.</span></span>|  
|<span data-ttu-id="0ef0d-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0ef0d-115">E_INVALIDARG</span></span>|<span data-ttu-id="0ef0d-116">`pAddress`가 `null`인 경우</span><span class="sxs-lookup"><span data-stu-id="0ef0d-116">`pAddress` is `null`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ef0d-117">설명</span><span class="sxs-lookup"><span data-stu-id="0ef0d-117">Remarks</span></span>  
 <span data-ttu-id="0ef0d-118">반환 된 값 `pAddress` 스택의 다른 프레임을 기준으로 내부 프레임의 위치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ef0d-118">The value returned in `pAddress` can be used to determine the location of the internal frame relative to other frames on the stack.</span></span> <span data-ttu-id="0ef0d-119">IA-64 기반 컴퓨터에도 내부 프레임만 스택에 있으며 백업 저장소에 해당 포인터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ef0d-119">Even on IA-64-based computers, the internal frame lives on the stack only, and there is no corresponding pointer to a backing store.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ef0d-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ef0d-120">Requirements</span></span>  
 <span data-ttu-id="0ef0d-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0ef0d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ef0d-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ef0d-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ef0d-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ef0d-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ef0d-124">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ef0d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ef0d-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="0ef0d-125">See also</span></span>

- [<span data-ttu-id="0ef0d-126">ICorDebugInternalFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ef0d-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [<span data-ttu-id="0ef0d-127">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ef0d-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="0ef0d-128">디버깅</span><span class="sxs-lookup"><span data-stu-id="0ef0d-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
