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
ms.openlocfilehash: f213a35a12bfb5cc92558a76e122a1494d567f93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170800"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="26cfa-102">ICorDebugThread4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="26cfa-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="26cfa-103">스레드 차단 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="26cfa-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="26cfa-104">메서드</span><span class="sxs-lookup"><span data-stu-id="26cfa-104">Methods</span></span>  
  
|<span data-ttu-id="26cfa-105">메서드</span><span class="sxs-lookup"><span data-stu-id="26cfa-105">Method</span></span>|<span data-ttu-id="26cfa-106">설명</span><span class="sxs-lookup"><span data-stu-id="26cfa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="26cfa-107">GetBlockingObjects 메서드</span><span class="sxs-lookup"><span data-stu-id="26cfa-107">GetBlockingObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="26cfa-108">순서가 지정 된 열거형을 제공 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 스레드 차단 정보를 제공 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="26cfa-108">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="26cfa-109">HadUnhandledException 메서드</span><span class="sxs-lookup"><span data-stu-id="26cfa-109">HadUnhandledException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="26cfa-110">스레드 처리 되지 않은 예외가 한 적이 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="26cfa-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="26cfa-111">GetCurrentCustomDebuggerNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="26cfa-111">GetCurrentCustomDebuggerNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="26cfa-112">현재 가져옵니다 [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) 현재 스레드에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="26cfa-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26cfa-113">설명</span><span class="sxs-lookup"><span data-stu-id="26cfa-113">Remarks</span></span>  
 <span data-ttu-id="26cfa-114">이 인터페이스는 ICorDebugThread, ICorDebugThread2 논리적으로 확장 하 고 [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="26cfa-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26cfa-115">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26cfa-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26cfa-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="26cfa-116">Requirements</span></span>  
 <span data-ttu-id="26cfa-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="26cfa-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26cfa-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26cfa-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26cfa-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26cfa-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="26cfa-120">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="26cfa-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="26cfa-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="26cfa-121">See also</span></span>

- [<span data-ttu-id="26cfa-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="26cfa-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="26cfa-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="26cfa-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
