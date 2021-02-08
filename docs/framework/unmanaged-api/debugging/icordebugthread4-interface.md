---
description: '자세히 알아보기: ICorDebugThread4 인터페이스'
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
ms.openlocfilehash: 4ad587cee81ce635df0a8917b7a6d68e60aaf0b3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800918"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="4d37a-103">ICorDebugThread4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4d37a-103">ICorDebugThread4 Interface</span></span>

<span data-ttu-id="4d37a-104">스레드 차단 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4d37a-104">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4d37a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4d37a-105">Methods</span></span>  
  
|<span data-ttu-id="4d37a-106">메서드</span><span class="sxs-lookup"><span data-stu-id="4d37a-106">Method</span></span>|<span data-ttu-id="4d37a-107">설명</span><span class="sxs-lookup"><span data-stu-id="4d37a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4d37a-108">GetBlockingObjects 메서드</span><span class="sxs-lookup"><span data-stu-id="4d37a-108">GetBlockingObjects Method</span></span>](icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="4d37a-109">스레드 차단 정보를 제공 하는 [CorDebugBlockingObject](cordebugblockingobject-structure.md) 구조의 순서가 지정 된 열거형을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d37a-109">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="4d37a-110">HadUnhandledException 메서드</span><span class="sxs-lookup"><span data-stu-id="4d37a-110">HadUnhandledException Method</span></span>](icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="4d37a-111">스레드에 처리 되지 않은 예외가 발생 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4d37a-111">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="4d37a-112">GetCurrentCustomDebuggerNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="4d37a-112">GetCurrentCustomDebuggerNotification Method</span></span>](icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="4d37a-113">현재 스레드의 현재 [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4d37a-113">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d37a-114">설명</span><span class="sxs-lookup"><span data-stu-id="4d37a-114">Remarks</span></span>  

 <span data-ttu-id="4d37a-115">이 인터페이스는 ICorDebugThread, ICorDebugThread2 및 [ICorDebugThread3](icordebugthread3-interface.md) 인터페이스를 논리적으로 확장 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4d37a-115">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4d37a-116">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d37a-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d37a-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4d37a-117">Requirements</span></span>  

 <span data-ttu-id="4d37a-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d37a-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d37a-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d37a-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d37a-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d37a-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d37a-121">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d37a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d37a-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d37a-122">See also</span></span>

- [<span data-ttu-id="4d37a-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4d37a-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4d37a-124">디버깅</span><span class="sxs-lookup"><span data-stu-id="4d37a-124">Debugging</span></span>](index.md)
