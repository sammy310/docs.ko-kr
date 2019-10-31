---
title: ICorDebugManagedCallback::LogSwitch 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type:
- apiref
ms.openlocfilehash: a72eabb1b405c67f5603164e56a589a237603d2f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130690"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a><span data-ttu-id="b6c7d-102">ICorDebugManagedCallback::LogSwitch 메서드</span><span class="sxs-lookup"><span data-stu-id="b6c7d-102">ICorDebugManagedCallback::LogSwitch Method</span></span>
<span data-ttu-id="b6c7d-103">디버깅/추적 스위치를 만들거나 수정 하거나 삭제 하기 위해 CLR (공용 언어 런타임) 관리 스레드가 <xref:System.Diagnostics.Switch> 클래스에서 메서드를 호출 했음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b6c7d-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.Switch> class to create, modify, or delete a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6c7d-104">구문</span><span class="sxs-lookup"><span data-stu-id="b6c7d-104">Syntax</span></span>  
  
```cpp  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6c7d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b6c7d-105">Parameters</span></span>  
 `PAppDomain`  
 <span data-ttu-id="b6c7d-106">진행 디버깅/추적 스위치를 만들거나, 수정 하거나, 삭제 한 관리 되는 스레드가 포함 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b6c7d-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that created, modified, or deleted a debugging/tracing switch.</span></span>  
  
 `pThread`  
 <span data-ttu-id="b6c7d-107">진행 관리 되는 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b6c7d-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="b6c7d-108">진행 이벤트 로그에 기록 된 설명 메시지의 심각도 수준을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b6c7d-108">[in] A value that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `ulReason`  
 <span data-ttu-id="b6c7d-109">진행 디버깅/추적 스위치에 대해 수행 된 작업을 나타내는 [Logswitchcallreason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b6c7d-109">[in] A value of the [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) enumeration that indicates the operation performed on the debugging/tracing switch.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="b6c7d-110">진행 디버깅/추적 스위치의 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b6c7d-110">[in] A pointer to the name of the debugging/tracing switch.</span></span>  
  
 `pParentName`  
 <span data-ttu-id="b6c7d-111">진행 디버깅/추적 스위치의 부모 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b6c7d-111">[in] A pointer to the name of the parent of the debugging/tracing switch.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6c7d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6c7d-112">Requirements</span></span>  
 <span data-ttu-id="b6c7d-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6c7d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6c7d-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6c7d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6c7d-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6c7d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6c7d-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6c7d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6c7d-117">참조</span><span class="sxs-lookup"><span data-stu-id="b6c7d-117">See also</span></span>

- [<span data-ttu-id="b6c7d-118">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6c7d-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
