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
ms.openlocfilehash: 0bb25d060853abb20316a344bae3755b2f8b4dc7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791331"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="c31b5-102">ICorDebugThread4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c31b5-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="c31b5-103">스레드 차단 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c31b5-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c31b5-104">메서드</span><span class="sxs-lookup"><span data-stu-id="c31b5-104">Methods</span></span>  
  
|<span data-ttu-id="c31b5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c31b5-105">Method</span></span>|<span data-ttu-id="c31b5-106">설명</span><span class="sxs-lookup"><span data-stu-id="c31b5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c31b5-107">GetBlockingObjects 메서드</span><span class="sxs-lookup"><span data-stu-id="c31b5-107">GetBlockingObjects Method</span></span>](icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="c31b5-108">스레드 차단 정보를 제공 하는 [CorDebugBlockingObject](cordebugblockingobject-structure.md) 구조의 순서가 지정 된 열거형을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c31b5-108">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="c31b5-109">HadUnhandledException 메서드</span><span class="sxs-lookup"><span data-stu-id="c31b5-109">HadUnhandledException Method</span></span>](icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="c31b5-110">스레드에 처리 되지 않은 예외가 발생 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c31b5-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="c31b5-111">GetCurrentCustomDebuggerNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="c31b5-111">GetCurrentCustomDebuggerNotification Method</span></span>](icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="c31b5-112">현재 스레드의 현재 [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c31b5-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c31b5-113">주의</span><span class="sxs-lookup"><span data-stu-id="c31b5-113">Remarks</span></span>  
 <span data-ttu-id="c31b5-114">이 인터페이스는 ICorDebugThread, ICorDebugThread2 및 [ICorDebugThread3](icordebugthread3-interface.md) 인터페이스를 논리적으로 확장 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c31b5-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c31b5-115">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c31b5-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c31b5-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c31b5-116">Requirements</span></span>  
 <span data-ttu-id="c31b5-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c31b5-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c31b5-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c31b5-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c31b5-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c31b5-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c31b5-120">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c31b5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c31b5-121">참조</span><span class="sxs-lookup"><span data-stu-id="c31b5-121">See also</span></span>

- [<span data-ttu-id="c31b5-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c31b5-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c31b5-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="c31b5-123">Debugging</span></span>](index.md)
