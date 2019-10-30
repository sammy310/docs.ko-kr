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
ms.openlocfilehash: b1ee5a155afa4e33340108e7295adef2309986cf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122700"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="e4b6e-102">ICorDebugInternalFrame 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e4b6e-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="e4b6e-103">스택의 런타임 내부 프레임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="e4b6e-104">이 인터페이스는 ICorDebugFrame 인터페이스의 하위 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e4b6e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e4b6e-105">Methods</span></span>  
  
|<span data-ttu-id="e4b6e-106">메서드</span><span class="sxs-lookup"><span data-stu-id="e4b6e-106">Method</span></span>|<span data-ttu-id="e4b6e-107">설명</span><span class="sxs-lookup"><span data-stu-id="e4b6e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e4b6e-108">GetFrameType 메서드</span><span class="sxs-lookup"><span data-stu-id="e4b6e-108">GetFrameType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="e4b6e-109">이 내부 프레임의 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4b6e-110">주의</span><span class="sxs-lookup"><span data-stu-id="e4b6e-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e4b6e-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4b6e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4b6e-112">Requirements</span></span>  
 <span data-ttu-id="e4b6e-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e4b6e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4b6e-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4b6e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4b6e-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4b6e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4b6e-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4b6e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4b6e-117">참조</span><span class="sxs-lookup"><span data-stu-id="e4b6e-117">See also</span></span>

- [<span data-ttu-id="e4b6e-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e4b6e-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
