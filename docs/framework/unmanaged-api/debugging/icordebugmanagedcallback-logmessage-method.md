---
description: '자세히 알아보기: ICorDebugManagedCallback:: LogMessage 메서드'
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
ms.openlocfilehash: 199f1f5dca7889a62ef351b4a2731fdb360768d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660520"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="13e17-103">ICorDebugManagedCallback::LogMessage 메서드</span><span class="sxs-lookup"><span data-stu-id="13e17-103">ICorDebugManagedCallback::LogMessage Method</span></span>

<span data-ttu-id="13e17-104">CLR (공용 언어 런타임) 관리 스레드가 클래스의 메서드를 호출 하 여 이벤트를 기록 한다고 디버거에 알립니다 <xref:System.Diagnostics.EventLog> .</span><span class="sxs-lookup"><span data-stu-id="13e17-104">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13e17-105">구문</span><span class="sxs-lookup"><span data-stu-id="13e17-105">Syntax</span></span>  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13e17-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="13e17-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="13e17-107">진행 이벤트를 기록한 관리 되는 스레드가 포함 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="13e17-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="13e17-108">진행 관리 되는 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="13e17-108">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="13e17-109">진행 이벤트 로그에 기록 된 설명 메시지의 심각도 수준을 나타내는 [LoggingLevelEnum](logginglevelenum-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="13e17-109">[in] A value of the [LoggingLevelEnum](logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="13e17-110">진행 추적 스위치의 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="13e17-110">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="13e17-111">진행 이벤트 로그에 기록 된 메시지에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="13e17-111">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13e17-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="13e17-112">Requirements</span></span>  

 <span data-ttu-id="13e17-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13e17-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13e17-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13e17-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13e17-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13e17-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13e17-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13e17-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13e17-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13e17-117">See also</span></span>

- [<span data-ttu-id="13e17-118">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13e17-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
