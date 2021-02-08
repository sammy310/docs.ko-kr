---
description: '자세히 알아보기: ICorDebugInternalFrame2 인터페이스'
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
ms.openlocfilehash: 3edc666c043513562b2fcece478b2879f294ce33
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791103"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="a9fa2-103">ICorDebugInternalFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a9fa2-103">ICorDebugInternalFrame2 Interface</span></span>

<span data-ttu-id="a9fa2-104">ICorDebugFrame 개체에 상대적인 스택 주소 및 위치를 비롯하여 내부 프레임에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a9fa2-104">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a9fa2-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a9fa2-105">Methods</span></span>  
  
|<span data-ttu-id="a9fa2-106">메서드</span><span class="sxs-lookup"><span data-stu-id="a9fa2-106">Method</span></span>|<span data-ttu-id="a9fa2-107">설명</span><span class="sxs-lookup"><span data-stu-id="a9fa2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a9fa2-108">GetFrameAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="a9fa2-108">GetFrameAddress Method</span></span>](icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="a9fa2-109">내부 프레임의 스택 주소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9fa2-109">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="a9fa2-110">IsCloserToLeaf 메서드</span><span class="sxs-lookup"><span data-stu-id="a9fa2-110">IsCloserToLeaf Method</span></span>](icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="a9fa2-111">`this`내부 프레임이 지정 된 ICorDebugFrame 개체 보다 리프에 가까이 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9fa2-111">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9fa2-112">설명</span><span class="sxs-lookup"><span data-stu-id="a9fa2-112">Remarks</span></span>  

 <span data-ttu-id="a9fa2-113">이 인터페이스는 ICorDebugInternalFrame 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9fa2-113">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a9fa2-114">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9fa2-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9fa2-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a9fa2-115">Requirements</span></span>  

 <span data-ttu-id="a9fa2-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a9fa2-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9fa2-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9fa2-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9fa2-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9fa2-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9fa2-119">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9fa2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9fa2-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9fa2-120">See also</span></span>

- [<span data-ttu-id="a9fa2-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a9fa2-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a9fa2-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="a9fa2-122">Debugging</span></span>](index.md)
