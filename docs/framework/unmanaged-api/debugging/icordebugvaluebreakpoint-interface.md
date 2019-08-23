---
title: ICorDebugValueBreakpoint 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint
helpviewer_keywords:
- ICorDebugValueBreakpoint interface [.NET Framework debugging]
ms.assetid: c02338fe-da6c-467f-9567-70ebb387e901
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f77268e069d322d0f491f78b154cf63b691e3e38
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966821"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="2855e-102">ICorDebugValueBreakpoint 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2855e-102">ICorDebugValueBreakpoint Interface</span></span>
<span data-ttu-id="2855e-103">특정 값에 대 한 액세스를 제공 하기 위해 ICorDebugBreakpoint 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2855e-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2855e-104">메서드</span><span class="sxs-lookup"><span data-stu-id="2855e-104">Methods</span></span>  
  
|<span data-ttu-id="2855e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2855e-105">Method</span></span>|<span data-ttu-id="2855e-106">Description</span><span class="sxs-lookup"><span data-stu-id="2855e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2855e-107">GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="2855e-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="2855e-108">중단점이 설정 된 개체의 값을 나타내는 ICorDebugValue 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2855e-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2855e-109">설명</span><span class="sxs-lookup"><span data-stu-id="2855e-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2855e-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2855e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2855e-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2855e-111">Requirements</span></span>  
 <span data-ttu-id="2855e-112">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2855e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2855e-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2855e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2855e-114">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2855e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2855e-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2855e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2855e-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="2855e-116">See also</span></span>

- [<span data-ttu-id="2855e-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2855e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
