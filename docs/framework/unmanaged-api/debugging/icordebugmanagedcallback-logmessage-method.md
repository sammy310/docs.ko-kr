---
title: ICorDebugManagedCallback::LogMessage 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogMessage
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogMessage
helpviewer_keywords:
- ICorDebugManagedCallback::LogMessage method [.NET Framework debugging]
- LogMessage method [.NET Framework debugging]
ms.assetid: d218554a-bf42-4d88-833d-ede30de67a53
topic_type:
- apiref
ms.openlocfilehash: d95662167dbc8fcda049fb6a7b3e6ff1dfb6e736
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130700"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="5362e-102">ICorDebugManagedCallback::LogMessage 메서드</span><span class="sxs-lookup"><span data-stu-id="5362e-102">ICorDebugManagedCallback::LogMessage Method</span></span>
<span data-ttu-id="5362e-103">CLR (공용 언어 런타임) 관리 되는 스레드가 <xref:System.Diagnostics.EventLog> 클래스의 메서드를 호출 하 여 이벤트를 기록 했음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5362e-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5362e-104">구문</span><span class="sxs-lookup"><span data-stu-id="5362e-104">Syntax</span></span>  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5362e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5362e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5362e-106">진행 이벤트를 기록한 관리 되는 스레드가 포함 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5362e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="5362e-107">진행 관리 되는 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5362e-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="5362e-108">진행 이벤트 로그에 기록 된 설명 메시지의 심각도 수준을 나타내는 [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5362e-108">[in] A value of the [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="5362e-109">진행 추적 스위치의 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5362e-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="5362e-110">진행 이벤트 로그에 기록 된 메시지에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5362e-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5362e-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5362e-111">Requirements</span></span>  
 <span data-ttu-id="5362e-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5362e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5362e-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5362e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5362e-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5362e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5362e-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5362e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5362e-116">참조</span><span class="sxs-lookup"><span data-stu-id="5362e-116">See also</span></span>

- [<span data-ttu-id="5362e-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5362e-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
