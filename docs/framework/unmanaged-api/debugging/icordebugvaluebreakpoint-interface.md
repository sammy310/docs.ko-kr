---
description: '자세히 알아보기: ICorDebugValueBreakpoint 인터페이스'
title: ICorDebugValueBreakpoint 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint
helpviewer_keywords:
- ICorDebugValueBreakpoint interface [.NET Framework debugging]
ms.assetid: c02338fe-da6c-467f-9567-70ebb387e901
topic_type:
- apiref
ms.openlocfilehash: ff53b1f6e1557a3e98cc642f80eaaa2feaeac473
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790687"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="c7e50-103">ICorDebugValueBreakpoint 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7e50-103">ICorDebugValueBreakpoint Interface</span></span>

<span data-ttu-id="c7e50-104">특정 값에 대 한 액세스를 제공 하기 위해 ICorDebugBreakpoint 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e50-104">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c7e50-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c7e50-105">Methods</span></span>  
  
|<span data-ttu-id="c7e50-106">메서드</span><span class="sxs-lookup"><span data-stu-id="c7e50-106">Method</span></span>|<span data-ttu-id="c7e50-107">설명</span><span class="sxs-lookup"><span data-stu-id="c7e50-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c7e50-108">GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="c7e50-108">GetValue Method</span></span>](icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="c7e50-109">중단점이 설정 된 개체의 값을 나타내는 ICorDebugValue 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c7e50-109">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7e50-110">설명</span><span class="sxs-lookup"><span data-stu-id="c7e50-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7e50-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e50-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7e50-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7e50-112">Requirements</span></span>  

 <span data-ttu-id="c7e50-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7e50-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7e50-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7e50-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7e50-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7e50-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7e50-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7e50-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7e50-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7e50-117">See also</span></span>

- [<span data-ttu-id="c7e50-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7e50-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
