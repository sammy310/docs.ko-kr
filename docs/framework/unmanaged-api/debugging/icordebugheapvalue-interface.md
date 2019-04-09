---
title: ICorDebugHeapValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue
helpviewer_keywords:
- ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d5fcd8c17c4006714fa9d11aece5cccc57c97087
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075498"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="2b541-102">ICorDebugHeapValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b541-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="2b541-103">공용 언어 런타임 (CLR) 가비지 수집기에 의해 수집 된 개체를 나타내는 "ICorDebugValue"의 하위 클래스.</span><span class="sxs-lookup"><span data-stu-id="2b541-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2b541-104">메서드</span><span class="sxs-lookup"><span data-stu-id="2b541-104">Methods</span></span>  
  
|<span data-ttu-id="2b541-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2b541-105">Method</span></span>|<span data-ttu-id="2b541-106">설명</span><span class="sxs-lookup"><span data-stu-id="2b541-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2b541-107">CreateRelocBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="2b541-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="2b541-108">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="2b541-108">Not implemented.</span></span>|  
|[<span data-ttu-id="2b541-109">IsValid 메서드</span><span class="sxs-lookup"><span data-stu-id="2b541-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="2b541-110">이 나타내는 개체가 있는지 여부를 나타내는 값을 가져옵니다 `ICorDebugHeapValue` 잘못 되었거나 가비지 수집기에서 회수 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b541-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="2b541-111">이 메서드는.NET Framework 버전 2.0에서에서 더 이상 사용 되지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2b541-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b541-112">설명</span><span class="sxs-lookup"><span data-stu-id="2b541-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b541-113">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b541-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b541-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b541-114">Requirements</span></span>  
 <span data-ttu-id="2b541-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2b541-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b541-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b541-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b541-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b541-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2b541-118">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="2b541-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2b541-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="2b541-119">See also</span></span>

- [<span data-ttu-id="2b541-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b541-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
