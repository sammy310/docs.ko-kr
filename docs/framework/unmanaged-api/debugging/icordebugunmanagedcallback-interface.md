---
description: '자세히 알아보기: ICorDebugUnmanagedCallback 인터페이스'
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
ms.openlocfilehash: 6d8aa398ff7121e360c3da66671781cd169b6228
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690550"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="aa3e0-103">ICorDebugUnmanagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa3e0-103">ICorDebugUnmanagedCallback Interface</span></span>

<span data-ttu-id="aa3e0-104">CLR (공용 언어 런타임)과 직접적으로 관련 되지 않은 네이티브 이벤트에 대 한 알림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3e0-104">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa3e0-105">메서드</span><span class="sxs-lookup"><span data-stu-id="aa3e0-105">Methods</span></span>  
  
|<span data-ttu-id="aa3e0-106">메서드</span><span class="sxs-lookup"><span data-stu-id="aa3e0-106">Method</span></span>|<span data-ttu-id="aa3e0-107">설명</span><span class="sxs-lookup"><span data-stu-id="aa3e0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aa3e0-108">DebugEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="aa3e0-108">DebugEvent Method</span></span>](icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="aa3e0-109">네이티브 이벤트가 발생 했음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="aa3e0-109">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa3e0-110">설명</span><span class="sxs-lookup"><span data-stu-id="aa3e0-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aa3e0-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa3e0-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa3e0-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa3e0-112">Requirements</span></span>  

 <span data-ttu-id="aa3e0-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa3e0-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa3e0-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa3e0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa3e0-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa3e0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa3e0-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa3e0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa3e0-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa3e0-117">See also</span></span>

- [<span data-ttu-id="aa3e0-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa3e0-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
