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
ms.openlocfilehash: 6de440d10f02f177e62ca3d2bd29fd5e98ea9388
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137137"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="747fe-102">ICorDebugUnmanagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="747fe-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="747fe-103">CLR (공용 언어 런타임)과 직접적으로 관련 되지 않은 네이티브 이벤트에 대 한 알림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="747fe-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="747fe-104">메서드</span><span class="sxs-lookup"><span data-stu-id="747fe-104">Methods</span></span>  
  
|<span data-ttu-id="747fe-105">메서드</span><span class="sxs-lookup"><span data-stu-id="747fe-105">Method</span></span>|<span data-ttu-id="747fe-106">설명</span><span class="sxs-lookup"><span data-stu-id="747fe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="747fe-107">DebugEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="747fe-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="747fe-108">네이티브 이벤트가 발생 했음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="747fe-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="747fe-109">주의</span><span class="sxs-lookup"><span data-stu-id="747fe-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="747fe-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="747fe-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="747fe-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="747fe-111">Requirements</span></span>  
 <span data-ttu-id="747fe-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="747fe-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="747fe-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="747fe-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="747fe-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="747fe-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="747fe-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="747fe-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="747fe-116">참조</span><span class="sxs-lookup"><span data-stu-id="747fe-116">See also</span></span>

- [<span data-ttu-id="747fe-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="747fe-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
