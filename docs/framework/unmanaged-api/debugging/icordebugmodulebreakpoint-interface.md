---
title: ICorDebugModuleBreakpoint 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint
helpviewer_keywords:
- ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: 34667162-f314-475f-ae1b-ce9cb0fcbb83
topic_type:
- apiref
ms.openlocfilehash: 2bc5c21d2e1256d0e79390bea10aafcdefbed0d3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110330"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="98df8-102">ICorDebugModuleBreakpoint 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98df8-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="98df8-103">특정 모듈에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="98df8-103">Provides access to specific modules.</span></span> <span data-ttu-id="98df8-104">이 인터페이스는 ICorDebugBreakpoint 인터페이스의 하위 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="98df8-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="98df8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="98df8-105">Methods</span></span>  
  
|<span data-ttu-id="98df8-106">메서드</span><span class="sxs-lookup"><span data-stu-id="98df8-106">Method</span></span>|<span data-ttu-id="98df8-107">설명</span><span class="sxs-lookup"><span data-stu-id="98df8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="98df8-108">GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="98df8-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="98df8-109">이 중단점이 설정 된 모듈을 참조 하는 ICorDebugModule에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="98df8-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98df8-110">주의</span><span class="sxs-lookup"><span data-stu-id="98df8-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="98df8-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98df8-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98df8-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="98df8-112">Requirements</span></span>  
 <span data-ttu-id="98df8-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98df8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98df8-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98df8-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98df8-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98df8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98df8-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98df8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98df8-117">참조</span><span class="sxs-lookup"><span data-stu-id="98df8-117">See also</span></span>

- [<span data-ttu-id="98df8-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98df8-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
