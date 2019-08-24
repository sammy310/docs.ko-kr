---
title: ICorDebugAssemblyEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum
helpviewer_keywords:
- ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: 891ceb43-5161-421e-a0bf-299962fd7efd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c557df3c69b9d18b95ebf33815b92dcb9097f4e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69987543"
---
# <a name="icordebugassemblyenum-interface"></a><span data-ttu-id="dd6c8-102">ICorDebugAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dd6c8-102">ICorDebugAssemblyEnum Interface</span></span>

<span data-ttu-id="dd6c8-103">ICorDebugEnum 메서드를 구현 하 고 ICorDebugAssembly 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd6c8-103">Implements ICorDebugEnum methods and enumerates ICorDebugAssembly arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dd6c8-104">메서드</span><span class="sxs-lookup"><span data-stu-id="dd6c8-104">Methods</span></span>  
  
|<span data-ttu-id="dd6c8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="dd6c8-105">Method</span></span>|<span data-ttu-id="dd6c8-106">Description</span><span class="sxs-lookup"><span data-stu-id="dd6c8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dd6c8-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="dd6c8-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-next-method.md)|<span data-ttu-id="dd6c8-108">현재 위치에서 시작 하 `ICorDebugAssembly` 여 열거형의 지정 된 수의 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dd6c8-108">Gets the specified number of `ICorDebugAssembly` instances in the enumeration, starting from the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd6c8-109">설명</span><span class="sxs-lookup"><span data-stu-id="dd6c8-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dd6c8-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd6c8-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd6c8-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dd6c8-111">Requirements</span></span>  
 <span data-ttu-id="dd6c8-112">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dd6c8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd6c8-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd6c8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd6c8-114">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd6c8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd6c8-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd6c8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd6c8-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="dd6c8-116">See also</span></span>

- [<span data-ttu-id="dd6c8-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dd6c8-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
