---
description: '자세히 알아보기: ICorDebugFunctionBreakpoint 인터페이스'
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
ms.openlocfilehash: 5d7597369241272d91de4b94a60d787304dc1c6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661131"
---
# <a name="icordebugfunctionbreakpoint-interface"></a><span data-ttu-id="99ae7-103">ICorDebugFunctionBreakpoint 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99ae7-103">ICorDebugFunctionBreakpoint Interface</span></span>

<span data-ttu-id="99ae7-104">ICorDebugBreakpoint 인터페이스를 확장 하 여 함수 내에서 중단점을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="99ae7-104">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="99ae7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="99ae7-105">Methods</span></span>  
  
|<span data-ttu-id="99ae7-106">메서드</span><span class="sxs-lookup"><span data-stu-id="99ae7-106">Method</span></span>|<span data-ttu-id="99ae7-107">설명</span><span class="sxs-lookup"><span data-stu-id="99ae7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="99ae7-108">GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="99ae7-108">GetFunction Method</span></span>](icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="99ae7-109">중단점이 설정 된 함수를 참조 하는 ICorDebugFunction에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99ae7-109">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="99ae7-110">GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="99ae7-110">GetOffset Method</span></span>](icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="99ae7-111">함수 내에서 중단점의 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99ae7-111">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99ae7-112">설명</span><span class="sxs-lookup"><span data-stu-id="99ae7-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="99ae7-113">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99ae7-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99ae7-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99ae7-114">Requirements</span></span>  

 <span data-ttu-id="99ae7-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99ae7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99ae7-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99ae7-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99ae7-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99ae7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99ae7-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99ae7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99ae7-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99ae7-119">See also</span></span>

- [<span data-ttu-id="99ae7-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99ae7-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
