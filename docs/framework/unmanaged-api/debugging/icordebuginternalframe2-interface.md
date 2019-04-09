---
title: ICorDebugInternalFrame2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2
helpviewer_keywords:
- ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2cf75de6a71cfbe25cbde281f837060b88e93753
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087237"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="c3280-102">ICorDebugInternalFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3280-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="c3280-103">스택 주소 및 ICorDebugFrame 개체와 관련 하 여 위치를 포함 하 여 내부 프레임에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3280-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c3280-104">메서드</span><span class="sxs-lookup"><span data-stu-id="c3280-104">Methods</span></span>  
  
|<span data-ttu-id="c3280-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c3280-105">Method</span></span>|<span data-ttu-id="c3280-106">설명</span><span class="sxs-lookup"><span data-stu-id="c3280-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c3280-107">GetFrameAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="c3280-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="c3280-108">내부 프레임의 스택 주소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c3280-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="c3280-109">IsCloserToLeaf 메서드</span><span class="sxs-lookup"><span data-stu-id="c3280-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="c3280-110">확인 여부는 `this` 내부 프레임에 더 가까운 리프 지정된 ICorDebugFrame 개체 보다 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3280-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3280-111">설명</span><span class="sxs-lookup"><span data-stu-id="c3280-111">Remarks</span></span>  
 <span data-ttu-id="c3280-112">이 인터페이스는 ICorDebugInternalFrame 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3280-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3280-113">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3280-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3280-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3280-114">Requirements</span></span>  
 <span data-ttu-id="c3280-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c3280-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3280-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3280-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3280-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3280-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c3280-118">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="c3280-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c3280-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="c3280-119">See also</span></span>

- [<span data-ttu-id="c3280-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3280-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c3280-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="c3280-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
