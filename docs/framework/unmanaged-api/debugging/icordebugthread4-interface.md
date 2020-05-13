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
ms.openlocfilehash: a0d6f3e109f92ad44eeeb1b1dec05e53015992a6
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378356"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="0d8c3-102">ICorDebugThread4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d8c3-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="0d8c3-103">스레드 차단 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0d8c3-104">메서드</span><span class="sxs-lookup"><span data-stu-id="0d8c3-104">Methods</span></span>  
  
|<span data-ttu-id="0d8c3-105">메서드</span><span class="sxs-lookup"><span data-stu-id="0d8c3-105">Method</span></span>|<span data-ttu-id="0d8c3-106">설명</span><span class="sxs-lookup"><span data-stu-id="0d8c3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d8c3-107">GetBlockingObjects 메서드</span><span class="sxs-lookup"><span data-stu-id="0d8c3-107">GetBlockingObjects Method</span></span>](icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="0d8c3-108">스레드 차단 정보를 제공 하는 [CorDebugBlockingObject](cordebugblockingobject-structure.md) 구조의 순서가 지정 된 열거형을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-108">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="0d8c3-109">HadUnhandledException 메서드</span><span class="sxs-lookup"><span data-stu-id="0d8c3-109">HadUnhandledException Method</span></span>](icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="0d8c3-110">스레드에 처리 되지 않은 예외가 발생 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="0d8c3-111">GetCurrentCustomDebuggerNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="0d8c3-111">GetCurrentCustomDebuggerNotification Method</span></span>](icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="0d8c3-112">현재 스레드의 현재 [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d8c3-113">설명</span><span class="sxs-lookup"><span data-stu-id="0d8c3-113">Remarks</span></span>  
 <span data-ttu-id="0d8c3-114">이 인터페이스는 ICorDebugThread, ICorDebugThread2 및 [ICorDebugThread3](icordebugthread3-interface.md) 인터페이스를 논리적으로 확장 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d8c3-115">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d8c3-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d8c3-116">Requirements</span></span>  
 <span data-ttu-id="0d8c3-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d8c3-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d8c3-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d8c3-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d8c3-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d8c3-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d8c3-120">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d8c3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d8c3-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d8c3-121">See also</span></span>

- [<span data-ttu-id="0d8c3-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d8c3-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0d8c3-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="0d8c3-123">Debugging</span></span>](index.md)
