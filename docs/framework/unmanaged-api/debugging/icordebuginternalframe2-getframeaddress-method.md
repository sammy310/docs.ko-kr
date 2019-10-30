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
ms.openlocfilehash: 40e64bdb35cff4e6ad6132c0806cfddd2767443c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122682"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a><span data-ttu-id="465bb-102">ICorDebugInternalFrame2::GetFrameAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="465bb-102">ICorDebugInternalFrame2::GetFrameAddress Method</span></span>
<span data-ttu-id="465bb-103">내부 프레임의 스택 주소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="465bb-103">Returns the stack address of the internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="465bb-104">구문</span><span class="sxs-lookup"><span data-stu-id="465bb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="465bb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="465bb-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="465bb-106">제한이 내부 프레임의 `CORDB_ADDRESS`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="465bb-106">[out] Pointer to the `CORDB_ADDRESS` for the internal frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="465bb-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="465bb-107">Return Value</span></span>  
 <span data-ttu-id="465bb-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="465bb-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="465bb-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="465bb-109">HRESULT</span></span>|<span data-ttu-id="465bb-110">설명</span><span class="sxs-lookup"><span data-stu-id="465bb-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="465bb-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="465bb-111">S_OK</span></span>|<span data-ttu-id="465bb-112">내부 프레임의 주소가 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="465bb-112">The address of the internal frame was successfully returned.</span></span>|  
|<span data-ttu-id="465bb-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="465bb-113">E_FAIL</span></span>|<span data-ttu-id="465bb-114">내부 프레임의 주소를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="465bb-114">The address of the internal frame could not be returned.</span></span>|  
|<span data-ttu-id="465bb-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="465bb-115">E_INVALIDARG</span></span>|<span data-ttu-id="465bb-116">`pAddress`가 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="465bb-116">`pAddress` is `null`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="465bb-117">주의</span><span class="sxs-lookup"><span data-stu-id="465bb-117">Remarks</span></span>  
 <span data-ttu-id="465bb-118">`pAddress`에서 반환 된 값을 사용 하 여 스택의 다른 프레임을 기준으로 내부 프레임의 위치를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465bb-118">The value returned in `pAddress` can be used to determine the location of the internal frame relative to other frames on the stack.</span></span> <span data-ttu-id="465bb-119">IA-64 기반 컴퓨터의 경우에도 내부 프레임은 스택에만 있고 백업 저장소에는 해당 하는 포인터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="465bb-119">Even on IA-64-based computers, the internal frame lives on the stack only, and there is no corresponding pointer to a backing store.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="465bb-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="465bb-120">Requirements</span></span>  
 <span data-ttu-id="465bb-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="465bb-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="465bb-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="465bb-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="465bb-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="465bb-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="465bb-124">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="465bb-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="465bb-125">참조</span><span class="sxs-lookup"><span data-stu-id="465bb-125">See also</span></span>

- [<span data-ttu-id="465bb-126">ICorDebugInternalFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="465bb-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [<span data-ttu-id="465bb-127">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="465bb-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="465bb-128">디버깅</span><span class="sxs-lookup"><span data-stu-id="465bb-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
