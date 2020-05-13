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
ms.openlocfilehash: 36a485413490045ca49b99fca4fe5d43edc37114
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213012"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="5aa02-102">ICorDebugHeapValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5aa02-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="5aa02-103">CLR (공용 언어 런타임) 가비지 수집기에 의해 수집 된 개체를 나타내는 "ICorDebugValue"의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5aa02-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5aa02-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5aa02-104">Methods</span></span>  
  
|<span data-ttu-id="5aa02-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5aa02-105">Method</span></span>|<span data-ttu-id="5aa02-106">설명</span><span class="sxs-lookup"><span data-stu-id="5aa02-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5aa02-107">CreateRelocBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="5aa02-107">CreateRelocBreakpoint Method</span></span>](icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="5aa02-108">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="5aa02-108">Not implemented.</span></span>|  
|[<span data-ttu-id="5aa02-109">IsValid 메서드</span><span class="sxs-lookup"><span data-stu-id="5aa02-109">IsValid Method</span></span>](icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="5aa02-110">이가 나타내는 개체가 `ICorDebugHeapValue` 유효한 지, 아니면 가비지 수집기에서 회수 되었는지를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5aa02-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="5aa02-111">이 메서드는 .NET Framework 버전 2.0에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5aa02-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5aa02-112">설명</span><span class="sxs-lookup"><span data-stu-id="5aa02-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5aa02-113">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5aa02-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5aa02-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5aa02-114">Requirements</span></span>  
 <span data-ttu-id="5aa02-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5aa02-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5aa02-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5aa02-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5aa02-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5aa02-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5aa02-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5aa02-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aa02-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5aa02-119">See also</span></span>

- [<span data-ttu-id="5aa02-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5aa02-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
