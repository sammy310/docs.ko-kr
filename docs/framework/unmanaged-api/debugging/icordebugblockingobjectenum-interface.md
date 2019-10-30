---
title: ICorDebugBlockingObjectEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum
helpviewer_keywords:
- ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
ms.assetid: 208e5c2d-3f3f-404e-8b3c-7cccc14ddb16
topic_type:
- apiref
ms.openlocfilehash: bfd61d985eac3ab56d8a5df9474b2b1a9f641f3e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122853"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="77be9-102">ICorDebugBlockingObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="77be9-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="77be9-103">[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 구조체의 목록에 대 한 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="77be9-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="77be9-104">이 인터페이스는 ICorDebugEnum 인터페이스의 하위 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="77be9-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="77be9-105">메서드</span><span class="sxs-lookup"><span data-stu-id="77be9-105">Methods</span></span>  
  
|<span data-ttu-id="77be9-106">메서드</span><span class="sxs-lookup"><span data-stu-id="77be9-106">Method</span></span>|<span data-ttu-id="77be9-107">설명</span><span class="sxs-lookup"><span data-stu-id="77be9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="77be9-108">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="77be9-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="77be9-109">[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 구조체 목록을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="77be9-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77be9-110">주의</span><span class="sxs-lookup"><span data-stu-id="77be9-110">Remarks</span></span>  
 <span data-ttu-id="77be9-111">각 `CorDebugBlockingObject` 구조체는 스레드를 차단하는 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="77be9-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="77be9-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77be9-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77be9-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="77be9-113">Requirements</span></span>  
 <span data-ttu-id="77be9-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77be9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77be9-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77be9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77be9-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77be9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77be9-117">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77be9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77be9-118">참조</span><span class="sxs-lookup"><span data-stu-id="77be9-118">See also</span></span>

- [<span data-ttu-id="77be9-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="77be9-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="77be9-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="77be9-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
