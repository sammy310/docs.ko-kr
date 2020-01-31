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
ms.openlocfilehash: 9e333d71505a055cfe27df2c79a102c939bafc9d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788472"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="ee0a2-102">ICorDebugInternalFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ee0a2-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="ee0a2-103">ICorDebugFrame 개체에 상대적인 스택 주소 및 위치를 비롯하여 내부 프레임에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ee0a2-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee0a2-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ee0a2-104">Methods</span></span>  
  
|<span data-ttu-id="ee0a2-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ee0a2-105">Method</span></span>|<span data-ttu-id="ee0a2-106">설명</span><span class="sxs-lookup"><span data-stu-id="ee0a2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee0a2-107">GetFrameAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="ee0a2-107">GetFrameAddress Method</span></span>](icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="ee0a2-108">내부 프레임의 스택 주소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee0a2-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="ee0a2-109">IsCloserToLeaf 메서드</span><span class="sxs-lookup"><span data-stu-id="ee0a2-109">IsCloserToLeaf Method</span></span>](icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="ee0a2-110">`this` 내부 프레임이 지정 된 ICorDebugFrame 개체 보다 리프에 가까이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee0a2-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee0a2-111">주의</span><span class="sxs-lookup"><span data-stu-id="ee0a2-111">Remarks</span></span>  
 <span data-ttu-id="ee0a2-112">이 인터페이스는 ICorDebugInternalFrame 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee0a2-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee0a2-113">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee0a2-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee0a2-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ee0a2-114">Requirements</span></span>  
 <span data-ttu-id="ee0a2-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee0a2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee0a2-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee0a2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee0a2-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee0a2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee0a2-118">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee0a2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee0a2-119">참조</span><span class="sxs-lookup"><span data-stu-id="ee0a2-119">See also</span></span>

- [<span data-ttu-id="ee0a2-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ee0a2-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ee0a2-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="ee0a2-121">Debugging</span></span>](index.md)
