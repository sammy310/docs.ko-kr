---
title: ICorDebugInternalFrame 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame
helpviewer_keywords:
- ICorDebugInternalFrame interface [.NET Framework debugging]
ms.assetid: bb4772ca-0d54-4185-b738-7a6ffe9ea85a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f16b4628215bee2410708edeb337b41fbdc0311
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109826"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="d4a4d-102">ICorDebugInternalFrame 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d4a4d-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="d4a4d-103">스택에 런타임 내부 프레임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d4a4d-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="d4a4d-104">이 인터페이스는 ICorDebugFrame 인터페이스의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d4a4d-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d4a4d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d4a4d-105">Methods</span></span>  
  
|<span data-ttu-id="d4a4d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="d4a4d-106">Method</span></span>|<span data-ttu-id="d4a4d-107">설명</span><span class="sxs-lookup"><span data-stu-id="d4a4d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d4a4d-108">GetFrameType 메서드</span><span class="sxs-lookup"><span data-stu-id="d4a4d-108">GetFrameType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="d4a4d-109">이 내부 프레임의 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d4a4d-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4a4d-110">설명</span><span class="sxs-lookup"><span data-stu-id="d4a4d-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4a4d-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4a4d-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4a4d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d4a4d-112">Requirements</span></span>  
 <span data-ttu-id="d4a4d-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d4a4d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4a4d-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4a4d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4a4d-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4a4d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4a4d-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4a4d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4a4d-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="d4a4d-117">See also</span></span>

- [<span data-ttu-id="d4a4d-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d4a4d-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
