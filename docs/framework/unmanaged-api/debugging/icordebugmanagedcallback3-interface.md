---
title: ICorDebugManagedCallback3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3
helpviewer_keywords:
- ICorDebugManagedCallback3 interface [.NET Framework debugging]
ms.assetid: a95389d3-cf2e-47a4-9805-61426acc6b65
topic_type:
- apiref
ms.openlocfilehash: 63e3f166c4cbf17f4892dccf770343bfbf6e0284
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209749"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="9d14d-102">ICorDebugManagedCallback3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d14d-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="9d14d-103">활성화된 사용자 지정 디버거 알림이 발생했음을 나타내는 콜백 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9d14d-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9d14d-104">메서드</span><span class="sxs-lookup"><span data-stu-id="9d14d-104">Methods</span></span>  
  
|<span data-ttu-id="9d14d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9d14d-105">Method</span></span>|<span data-ttu-id="9d14d-106">설명</span><span class="sxs-lookup"><span data-stu-id="9d14d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9d14d-107">CustomNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="9d14d-107">CustomNotification Method</span></span>](icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="9d14d-108">사용 하도록 설정 된 사용자 지정 디버거 알림이 발생 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9d14d-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d14d-109">설명</span><span class="sxs-lookup"><span data-stu-id="9d14d-109">Remarks</span></span>  
 <span data-ttu-id="9d14d-110">이 인터페이스는 [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) 및 [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) 인터페이스의 논리적 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="9d14d-110">This interface is a logical extension of the [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d14d-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d14d-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d14d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9d14d-112">Requirements</span></span>  
 <span data-ttu-id="9d14d-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d14d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d14d-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d14d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d14d-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d14d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d14d-116">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d14d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d14d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d14d-117">See also</span></span>

- [<span data-ttu-id="9d14d-118">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d14d-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
- [<span data-ttu-id="9d14d-119">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d14d-119">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="9d14d-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d14d-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9d14d-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="9d14d-121">Debugging</span></span>](index.md)
