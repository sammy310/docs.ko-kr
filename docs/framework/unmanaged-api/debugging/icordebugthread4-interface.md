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
ms.openlocfilehash: 8779dbc95a8bef13d45605295bd68b1d3f16851d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122427"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="b0bba-102">ICorDebugThread4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0bba-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="b0bba-103">스레드 차단 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bba-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b0bba-104">메서드</span><span class="sxs-lookup"><span data-stu-id="b0bba-104">Methods</span></span>  
  
|<span data-ttu-id="b0bba-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b0bba-105">Method</span></span>|<span data-ttu-id="b0bba-106">설명</span><span class="sxs-lookup"><span data-stu-id="b0bba-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b0bba-107">GetBlockingObjects 메서드</span><span class="sxs-lookup"><span data-stu-id="b0bba-107">GetBlockingObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="b0bba-108">스레드 차단 정보를 제공 하는 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 구조의 순서가 지정 된 열거형을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bba-108">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="b0bba-109">HadUnhandledException 메서드</span><span class="sxs-lookup"><span data-stu-id="b0bba-109">HadUnhandledException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="b0bba-110">스레드에 처리 되지 않은 예외가 발생 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b0bba-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="b0bba-111">GetCurrentCustomDebuggerNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="b0bba-111">GetCurrentCustomDebuggerNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="b0bba-112">현재 스레드의 현재 [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b0bba-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0bba-113">주의</span><span class="sxs-lookup"><span data-stu-id="b0bba-113">Remarks</span></span>  
 <span data-ttu-id="b0bba-114">이 인터페이스는 ICorDebugThread, ICorDebugThread2 및 [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) 인터페이스를 논리적으로 확장 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b0bba-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b0bba-115">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0bba-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0bba-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b0bba-116">Requirements</span></span>  
 <span data-ttu-id="b0bba-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0bba-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0bba-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0bba-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0bba-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0bba-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0bba-120">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0bba-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0bba-121">참조</span><span class="sxs-lookup"><span data-stu-id="b0bba-121">See also</span></span>

- [<span data-ttu-id="b0bba-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0bba-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="b0bba-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="b0bba-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
