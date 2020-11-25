---
title: ICorDebugBreakpointEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum
helpviewer_keywords:
- ICorDebugBreakpointEnum interface [.NET Framework debugging]
ms.assetid: 4c6f4f6e-52cc-402e-881b-7b8526544c90
topic_type:
- apiref
ms.openlocfilehash: 97e06a2f20dcc2bb3815b98ba29ff230e37ff29d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730164"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="10b30-102">ICorDebugBreakpointEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10b30-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="10b30-103">ICorDebugEnum 메서드를 구현 하 고 ICorDebugBreakpoint 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="10b30-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="10b30-104">메서드</span><span class="sxs-lookup"><span data-stu-id="10b30-104">Methods</span></span>  
  
|<span data-ttu-id="10b30-105">메서드</span><span class="sxs-lookup"><span data-stu-id="10b30-105">Method</span></span>|<span data-ttu-id="10b30-106">설명</span><span class="sxs-lookup"><span data-stu-id="10b30-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="10b30-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="10b30-107">Next Method</span></span>](icordebugbreakpointenum-next-method.md)|<span data-ttu-id="10b30-108">`ICorDebugBreakpoint`현재 위치에서 시작 하 여 열거형에서 지정 된 수의 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="10b30-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10b30-109">설명</span><span class="sxs-lookup"><span data-stu-id="10b30-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="10b30-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10b30-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10b30-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="10b30-111">Requirements</span></span>  

 <span data-ttu-id="10b30-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10b30-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10b30-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10b30-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10b30-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10b30-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10b30-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10b30-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10b30-116">참조</span><span class="sxs-lookup"><span data-stu-id="10b30-116">See also</span></span>

- [<span data-ttu-id="10b30-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10b30-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
