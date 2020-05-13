---
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
ms.openlocfilehash: 7026d135b02563b6c718be4096d2c5cad9d33cec
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212284"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="09cc7-102">ICorDebugModuleBreakpoint 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09cc7-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="09cc7-103">특정 모듈에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="09cc7-103">Provides access to specific modules.</span></span> <span data-ttu-id="09cc7-104">이 인터페이스는 ICorDebugBreakpoint 인터페이스의 하위 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="09cc7-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="09cc7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="09cc7-105">Methods</span></span>  
  
|<span data-ttu-id="09cc7-106">메서드</span><span class="sxs-lookup"><span data-stu-id="09cc7-106">Method</span></span>|<span data-ttu-id="09cc7-107">설명</span><span class="sxs-lookup"><span data-stu-id="09cc7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="09cc7-108">GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="09cc7-108">GetModule Method</span></span>](icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="09cc7-109">이 중단점이 설정 된 모듈을 참조 하는 ICorDebugModule에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="09cc7-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09cc7-110">설명</span><span class="sxs-lookup"><span data-stu-id="09cc7-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="09cc7-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09cc7-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09cc7-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09cc7-112">Requirements</span></span>  
 <span data-ttu-id="09cc7-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09cc7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09cc7-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09cc7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09cc7-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09cc7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09cc7-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09cc7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09cc7-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09cc7-117">See also</span></span>

- [<span data-ttu-id="09cc7-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09cc7-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
