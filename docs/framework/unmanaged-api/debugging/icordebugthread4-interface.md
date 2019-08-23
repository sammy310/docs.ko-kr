---
title: ICorDebugThread4 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugThread4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4
helpviewer_keywords:
- ICorDebugThread4 interface [.NET Framework debugging]
ms.assetid: a8c7719a-322b-4133-8566-4c27218dc104
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d66a1aed1936d0146d42c8e4a5ad06dfa39c802
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962967"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="b3f64-102">ICorDebugThread4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3f64-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="b3f64-103">스레드 차단 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b3f64-104">메서드</span><span class="sxs-lookup"><span data-stu-id="b3f64-104">Methods</span></span>  
  
|<span data-ttu-id="b3f64-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b3f64-105">Method</span></span>|<span data-ttu-id="b3f64-106">Description</span><span class="sxs-lookup"><span data-stu-id="b3f64-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b3f64-107">GetBlockingObjects 메서드</span><span class="sxs-lookup"><span data-stu-id="b3f64-107">GetBlockingObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="b3f64-108">스레드 차단 정보를 제공 하는 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 구조의 순서가 지정 된 열거형을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-108">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="b3f64-109">HadUnhandledException 메서드</span><span class="sxs-lookup"><span data-stu-id="b3f64-109">HadUnhandledException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="b3f64-110">스레드에 처리 되지 않은 예외가 발생 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="b3f64-111">GetCurrentCustomDebuggerNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="b3f64-111">GetCurrentCustomDebuggerNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="b3f64-112">현재 스레드의 현재 [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3f64-113">설명</span><span class="sxs-lookup"><span data-stu-id="b3f64-113">Remarks</span></span>  
 <span data-ttu-id="b3f64-114">이 인터페이스는 ICorDebugThread, ICorDebugThread2 및 [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) 인터페이스를 논리적으로 확장 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3f64-115">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3f64-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3f64-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3f64-116">Requirements</span></span>  
 <span data-ttu-id="b3f64-117">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b3f64-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3f64-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3f64-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3f64-119">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3f64-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3f64-120">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3f64-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3f64-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="b3f64-121">See also</span></span>

- [<span data-ttu-id="b3f64-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3f64-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="b3f64-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="b3f64-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
