---
title: ICorDebugProcessEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum
helpviewer_keywords:
- ICorDebugProcessEnum interface [.NET Framework debugging]
ms.assetid: b63a507a-ca97-4be0-8e4f-401cce2125f6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3651a4be94fa624d0dd6ab64b8c3f8169945de0d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175320"
---
# <a name="icordebugprocessenum-interface"></a><span data-ttu-id="b3c58-102">ICorDebugProcessEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3c58-102">ICorDebugProcessEnum Interface</span></span>
<span data-ttu-id="b3c58-103">ICorDebugEnum 메서드를 구현 하 고 ICorDebugProcess 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c58-103">Implements ICorDebugEnum methods and enumerates ICorDebugProcess arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b3c58-104">메서드</span><span class="sxs-lookup"><span data-stu-id="b3c58-104">Methods</span></span>  
  
|<span data-ttu-id="b3c58-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b3c58-105">Method</span></span>|<span data-ttu-id="b3c58-106">설명</span><span class="sxs-lookup"><span data-stu-id="b3c58-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b3c58-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="b3c58-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-next-method.md)|<span data-ttu-id="b3c58-108">지정 된 수를 가져옵니다 `ICorDebugProcess` 인스턴스는 열거형에서 현재 위치에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c58-108">Gets the specified number of `ICorDebugProcess` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3c58-109">설명</span><span class="sxs-lookup"><span data-stu-id="b3c58-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3c58-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c58-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3c58-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3c58-111">Requirements</span></span>  
 <span data-ttu-id="b3c58-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b3c58-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3c58-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3c58-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3c58-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3c58-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b3c58-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="b3c58-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b3c58-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="b3c58-116">See also</span></span>

- [<span data-ttu-id="b3c58-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3c58-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
