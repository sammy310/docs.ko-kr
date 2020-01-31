---
title: ICorDebugFunctionBreakpoint 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint
helpviewer_keywords:
- ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 9c149303-14b1-4138-83d7-e8c3e0fcd332
topic_type:
- apiref
ms.openlocfilehash: 5e3804335bacefad61c4f521ea1ef1444b7b1fed
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777702"
---
# <a name="icordebugfunctionbreakpoint-interface"></a><span data-ttu-id="6fea5-102">ICorDebugFunctionBreakpoint 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6fea5-102">ICorDebugFunctionBreakpoint Interface</span></span>

<span data-ttu-id="6fea5-103">ICorDebugBreakpoint 인터페이스를 확장 하 여 함수 내에서 중단점을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fea5-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6fea5-104">메서드</span><span class="sxs-lookup"><span data-stu-id="6fea5-104">Methods</span></span>  
  
|<span data-ttu-id="6fea5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="6fea5-105">Method</span></span>|<span data-ttu-id="6fea5-106">설명</span><span class="sxs-lookup"><span data-stu-id="6fea5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6fea5-107">GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="6fea5-107">GetFunction Method</span></span>](icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="6fea5-108">중단점이 설정 된 함수를 참조 하는 ICorDebugFunction에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6fea5-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="6fea5-109">GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="6fea5-109">GetOffset Method</span></span>](icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="6fea5-110">함수 내에서 중단점의 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6fea5-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fea5-111">주의</span><span class="sxs-lookup"><span data-stu-id="6fea5-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6fea5-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fea5-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fea5-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6fea5-113">Requirements</span></span>  
 <span data-ttu-id="6fea5-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6fea5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fea5-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6fea5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6fea5-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fea5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fea5-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fea5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fea5-118">참조</span><span class="sxs-lookup"><span data-stu-id="6fea5-118">See also</span></span>

- [<span data-ttu-id="6fea5-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6fea5-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
