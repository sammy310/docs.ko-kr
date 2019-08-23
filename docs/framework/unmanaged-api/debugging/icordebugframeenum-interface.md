---
title: ICorDebugFrameEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum
helpviewer_keywords:
- ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: ee3f85d3-044e-46b8-945c-93ebfa5d9e91
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9ea398c32762be31f93002533b15bcf3851b870
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910239"
---
# <a name="icordebugframeenum-interface"></a><span data-ttu-id="0a529-102">ICorDebugFrameEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a529-102">ICorDebugFrameEnum Interface</span></span>

<span data-ttu-id="0a529-103">ICorDebugEnum 메서드를 구현 하 고 ICorDebugFrame 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a529-103">Implements ICorDebugEnum methods, and enumerates ICorDebugFrame arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0a529-104">메서드</span><span class="sxs-lookup"><span data-stu-id="0a529-104">Methods</span></span>  
  
|<span data-ttu-id="0a529-105">메서드</span><span class="sxs-lookup"><span data-stu-id="0a529-105">Method</span></span>|<span data-ttu-id="0a529-106">설명</span><span class="sxs-lookup"><span data-stu-id="0a529-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0a529-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="0a529-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-next-method.md)|<span data-ttu-id="0a529-108">현재 위치에서 시작 하 `ICorDebugFrame` 여 열거형에서 지정 된 수의 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0a529-108">Gets the specified number of `ICorDebugFrame` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a529-109">설명</span><span class="sxs-lookup"><span data-stu-id="0a529-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0a529-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a529-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a529-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a529-111">Requirements</span></span>  
 <span data-ttu-id="0a529-112">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0a529-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a529-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a529-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a529-114">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a529-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a529-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a529-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a529-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="0a529-116">See also</span></span>

- [<span data-ttu-id="0a529-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a529-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
