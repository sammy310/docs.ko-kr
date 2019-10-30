---
title: ICorDebugAssembly2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2
helpviewer_keywords:
- ICorDebugAssembly2 interface [.NET Framework debugging]
ms.assetid: c0766e29-e573-4f9a-a928-167d1de5aa7e
topic_type:
- apiref
ms.openlocfilehash: a0482ff451b05ec50c199a75a3c3fabd68c28e21
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133991"
---
# <a name="icordebugassembly2-interface"></a><span data-ttu-id="c604b-102">ICorDebugAssembly2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c604b-102">ICorDebugAssembly2 Interface</span></span>

<span data-ttu-id="c604b-103">어셈블리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c604b-103">Represents an assembly.</span></span> <span data-ttu-id="c604b-104">이 인터페이스는 ICorDebugAssembly 인터페이스의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="c604b-104">This interface is an extension of the ICorDebugAssembly interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c604b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c604b-105">Methods</span></span>  
  
|<span data-ttu-id="c604b-106">메서드</span><span class="sxs-lookup"><span data-stu-id="c604b-106">Method</span></span>|<span data-ttu-id="c604b-107">설명</span><span class="sxs-lookup"><span data-stu-id="c604b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c604b-108">IsFullyTrusted 메서드</span><span class="sxs-lookup"><span data-stu-id="c604b-108">IsFullyTrusted Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly2-isfullytrusted-method.md)|<span data-ttu-id="c604b-109">어셈블리에 런타임 보안 시스템에서 완전 신뢰를 부여 했는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c604b-109">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c604b-110">주의</span><span class="sxs-lookup"><span data-stu-id="c604b-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c604b-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c604b-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c604b-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c604b-112">Requirements</span></span>  
 <span data-ttu-id="c604b-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c604b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c604b-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c604b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c604b-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c604b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c604b-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c604b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c604b-117">참조</span><span class="sxs-lookup"><span data-stu-id="c604b-117">See also</span></span>

- [<span data-ttu-id="c604b-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c604b-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
