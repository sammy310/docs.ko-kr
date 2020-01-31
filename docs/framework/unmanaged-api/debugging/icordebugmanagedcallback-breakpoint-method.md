---
title: ICorDebugManagedCallback::Breakpoint 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Breakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Breakpoint
helpviewer_keywords:
- ICorDebugManagedCallback::Breakpoint method [.NET Framework debugging]
- Breakpoint method [.NET Framework debugging]
ms.assetid: 60b279b0-a726-46d2-8c53-76986a007ebb
topic_type:
- apiref
ms.openlocfilehash: ac91a9c662a82c5ab870d01cb4b5d87c7af6b6ba
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782069"
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="cebe1-102">ICorDebugManagedCallback::Breakpoint 메서드</span><span class="sxs-lookup"><span data-stu-id="cebe1-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="cebe1-103">중단점에 도달 하면 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="cebe1-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cebe1-104">구문</span><span class="sxs-lookup"><span data-stu-id="cebe1-104">Syntax</span></span>  
  
```cpp  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cebe1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cebe1-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="cebe1-106">진행 중단점이 포함 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cebe1-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="cebe1-107">진행 중단점이 포함 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cebe1-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="cebe1-108">진행 중단점을 나타내는 ICorDebugBreakpoint 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cebe1-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cebe1-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cebe1-109">Requirements</span></span>  
 <span data-ttu-id="cebe1-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cebe1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cebe1-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cebe1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cebe1-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cebe1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cebe1-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cebe1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cebe1-114">참조</span><span class="sxs-lookup"><span data-stu-id="cebe1-114">See also</span></span>

- [<span data-ttu-id="cebe1-115">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cebe1-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
