---
title: ICorDebugValue2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2
helpviewer_keywords:
- ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0925cf217afafe57abf82cf51a77b1992bad5152
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966838"
---
# <a name="icordebugvalue2-interface"></a><span data-ttu-id="7a0f0-102">ICorDebugValue2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a0f0-102">ICorDebugValue2 Interface</span></span>
<span data-ttu-id="7a0f0-103">"ICorDebugValue" 인터페이스를 확장 하 여 "ICorDebugType" 개체에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a0f0-103">Extends the "ICorDebugValue" interface to provide support for "ICorDebugType" objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7a0f0-104">메서드</span><span class="sxs-lookup"><span data-stu-id="7a0f0-104">Methods</span></span>  
  
|<span data-ttu-id="7a0f0-105">메서드</span><span class="sxs-lookup"><span data-stu-id="7a0f0-105">Method</span></span>|<span data-ttu-id="7a0f0-106">설명</span><span class="sxs-lookup"><span data-stu-id="7a0f0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7a0f0-107">GetExactType 메서드</span><span class="sxs-lookup"><span data-stu-id="7a0f0-107">GetExactType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)|<span data-ttu-id="7a0f0-108">이 값의을 `ICorDebugType` <xref:System.Type> 나타내는 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7a0f0-108">Gets an interface pointer to an `ICorDebugType` object that represents the <xref:System.Type> of this value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a0f0-109">설명</span><span class="sxs-lookup"><span data-stu-id="7a0f0-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7a0f0-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a0f0-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a0f0-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7a0f0-111">Requirements</span></span>  
 <span data-ttu-id="7a0f0-112">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7a0f0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a0f0-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a0f0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a0f0-114">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a0f0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a0f0-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a0f0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a0f0-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="7a0f0-116">See also</span></span>

- [<span data-ttu-id="7a0f0-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a0f0-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

- [<span data-ttu-id="7a0f0-118">ICorDebugValue3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a0f0-118">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
