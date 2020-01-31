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
ms.openlocfilehash: fa31b8a6cc96935319e9bef3e561790b65e33a87
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777586"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="aa8f0-102">ICorDebugHeapValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa8f0-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="aa8f0-103">CLR (공용 언어 런타임) 가비지 수집기에 의해 수집 된 개체를 나타내는 "ICorDebugValue"의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8f0-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa8f0-104">메서드</span><span class="sxs-lookup"><span data-stu-id="aa8f0-104">Methods</span></span>  
  
|<span data-ttu-id="aa8f0-105">메서드</span><span class="sxs-lookup"><span data-stu-id="aa8f0-105">Method</span></span>|<span data-ttu-id="aa8f0-106">설명</span><span class="sxs-lookup"><span data-stu-id="aa8f0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aa8f0-107">CreateRelocBreakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="aa8f0-107">CreateRelocBreakpoint Method</span></span>](icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="aa8f0-108">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="aa8f0-108">Not implemented.</span></span>|  
|[<span data-ttu-id="aa8f0-109">IsValid 메서드</span><span class="sxs-lookup"><span data-stu-id="aa8f0-109">IsValid Method</span></span>](icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="aa8f0-110">이 `ICorDebugHeapValue` 나타내는 개체가 유효한 지 또는 가비지 수집기에 의해 회수 되었는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="aa8f0-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="aa8f0-111">이 메서드는 .NET Framework 버전 2.0에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa8f0-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa8f0-112">주의</span><span class="sxs-lookup"><span data-stu-id="aa8f0-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aa8f0-113">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa8f0-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa8f0-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa8f0-114">Requirements</span></span>  
 <span data-ttu-id="aa8f0-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa8f0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa8f0-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa8f0-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa8f0-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa8f0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa8f0-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa8f0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa8f0-119">참조</span><span class="sxs-lookup"><span data-stu-id="aa8f0-119">See also</span></span>

- [<span data-ttu-id="aa8f0-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa8f0-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
