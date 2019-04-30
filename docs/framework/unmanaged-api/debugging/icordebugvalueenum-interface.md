---
title: ICorDebugValueEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum
helpviewer_keywords:
- ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: 88989482-a09f-4bd0-9adb-16f47b0291fd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9484f211ff31c4fa71692db646ef3c556df0acad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986806"
---
# <a name="icordebugvalueenum-interface"></a><span data-ttu-id="22be6-102">ICorDebugValueEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="22be6-102">ICorDebugValueEnum Interface</span></span>
<span data-ttu-id="22be6-103">"ICorDebugEnum" 메서드를 구현 하 고 "ICorDebugValue" 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="22be6-103">Implements "ICorDebugEnum" methods and enumerates "ICorDebugValue" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22be6-104">메서드</span><span class="sxs-lookup"><span data-stu-id="22be6-104">Methods</span></span>  
  
|<span data-ttu-id="22be6-105">메서드</span><span class="sxs-lookup"><span data-stu-id="22be6-105">Method</span></span>|<span data-ttu-id="22be6-106">설명</span><span class="sxs-lookup"><span data-stu-id="22be6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22be6-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="22be6-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalueenum-next-method.md)|<span data-ttu-id="22be6-108">지정 된 수를 가져옵니다 `ICorDebugValue` 인스턴스는 열거형에서 현재 위치에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="22be6-108">Gets the specified number of `ICorDebugValue` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22be6-109">설명</span><span class="sxs-lookup"><span data-stu-id="22be6-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22be6-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22be6-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22be6-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="22be6-111">Requirements</span></span>  
 <span data-ttu-id="22be6-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="22be6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22be6-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22be6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22be6-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22be6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22be6-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22be6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22be6-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="22be6-116">See also</span></span>

- [<span data-ttu-id="22be6-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="22be6-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
