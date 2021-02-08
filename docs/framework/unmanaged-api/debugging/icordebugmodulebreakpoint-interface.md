---
description: '자세히 알아보기: ICorDebugModuleBreakpoint 인터페이스'
title: ICorDebugModuleBreakpoint 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint
helpviewer_keywords:
- ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: 34667162-f314-475f-ae1b-ce9cb0fcbb83
topic_type:
- apiref
ms.openlocfilehash: c864850400471c9a3580de9bb94262c62656edf0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790752"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="2f586-103">ICorDebugModuleBreakpoint 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f586-103">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="2f586-104">특정 모듈에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f586-104">Provides access to specific modules.</span></span> <span data-ttu-id="2f586-105">이 인터페이스는 ICorDebugBreakpoint 인터페이스의 하위 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="2f586-105">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2f586-106">메서드</span><span class="sxs-lookup"><span data-stu-id="2f586-106">Methods</span></span>  
  
|<span data-ttu-id="2f586-107">메서드</span><span class="sxs-lookup"><span data-stu-id="2f586-107">Method</span></span>|<span data-ttu-id="2f586-108">설명</span><span class="sxs-lookup"><span data-stu-id="2f586-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2f586-109">GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="2f586-109">GetModule Method</span></span>](icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="2f586-110">이 중단점이 설정 된 모듈을 참조 하는 ICorDebugModule에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2f586-110">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f586-111">설명</span><span class="sxs-lookup"><span data-stu-id="2f586-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2f586-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f586-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f586-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f586-113">Requirements</span></span>  

 <span data-ttu-id="2f586-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2f586-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f586-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f586-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f586-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f586-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f586-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f586-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f586-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f586-118">See also</span></span>

- [<span data-ttu-id="2f586-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f586-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
