---
title: ICorDebugUnmanagedCallback 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback
helpviewer_keywords:
- ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60a1546068ae6a8c8be1c0af1ef3c7d770c23d70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993761"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="ca229-102">ICorDebugUnmanagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca229-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="ca229-103">CLR (공용 언어 런타임)에 직접 관련 되지 않은 네이티브 이벤트의 알림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca229-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca229-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ca229-104">Methods</span></span>  
  
|<span data-ttu-id="ca229-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ca229-105">Method</span></span>|<span data-ttu-id="ca229-106">설명</span><span class="sxs-lookup"><span data-stu-id="ca229-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca229-107">DebugEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="ca229-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="ca229-108">네이티브 이벤트가 발생 했음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca229-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca229-109">설명</span><span class="sxs-lookup"><span data-stu-id="ca229-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca229-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca229-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca229-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ca229-111">Requirements</span></span>  
 <span data-ttu-id="ca229-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca229-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca229-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca229-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca229-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca229-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca229-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca229-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca229-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="ca229-116">See also</span></span>

- [<span data-ttu-id="ca229-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca229-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
