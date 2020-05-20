---
title: LoggingLevelEnum 열거형
ms.date: 03/30/2017
api_name:
- LoggingLevelEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LoggingLevelEnum
helpviewer_keywords:
- LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type:
- apiref
ms.openlocfilehash: 62ea982f30a6a73648d9bf36722c0b5a49a68896
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420749"
---
# <a name="logginglevelenum-enumeration"></a><span data-ttu-id="b1536-102">LoggingLevelEnum 열거형</span><span class="sxs-lookup"><span data-stu-id="b1536-102">LoggingLevelEnum Enumeration</span></span>
<span data-ttu-id="b1536-103">관리되는 스레드가 이벤트를 기록할 때 이벤트 로그에 기록되는 설명 메시지의 보안 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1536-103">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1536-104">구문</span><span class="sxs-lookup"><span data-stu-id="b1536-104">Syntax</span></span>  
  
```cpp  
typedef enum LoggingLevelEnum {  
    LTraceLevel0 = 0,  
    LTraceLevel1,  
    LTraceLevel2,  
    LTraceLevel3,  
    LTraceLevel4,  
    LStatusLevel0 = 20,  
    LStatusLevel1,  
    LStatusLevel2,  
    LStatusLevel3,  
    LStatusLevel4,  
    LWarningLevel = 40,  
    LErrorLevel = 50,  
    LPanicLevel = 100  
} LoggingLevelEnum;  
```  
  
## <a name="members"></a><span data-ttu-id="b1536-105">멤버</span><span class="sxs-lookup"><span data-stu-id="b1536-105">Members</span></span>  
  
|<span data-ttu-id="b1536-106">멤버</span><span class="sxs-lookup"><span data-stu-id="b1536-106">Member</span></span>|<span data-ttu-id="b1536-107">설명</span><span class="sxs-lookup"><span data-stu-id="b1536-107">Description</span></span>|  
|------------|-----------------|  
|`LTraceLevel0`|<span data-ttu-id="b1536-108">메시지는 추적 수준 0입니다.</span><span class="sxs-lookup"><span data-stu-id="b1536-108">The message is a trace level 0.</span></span>|  
|`LTraceLevel1`|<span data-ttu-id="b1536-109">메시지는 추적 수준 1입니다.</span><span class="sxs-lookup"><span data-stu-id="b1536-109">The message is a trace level 1.</span></span>|  
|`LTraceLevel2`|<span data-ttu-id="b1536-110">메시지는 추적 수준 2입니다.</span><span class="sxs-lookup"><span data-stu-id="b1536-110">The message is a trace level 2.</span></span>|  
|`LTraceLevel3`|<span data-ttu-id="b1536-111">메시지는 추적 수준 3입니다.</span><span class="sxs-lookup"><span data-stu-id="b1536-111">The message is a trace level 3.</span></span>|  
|`LTraceLevel4`|<span data-ttu-id="b1536-112">메시지는 추적 수준 4입니다.</span><span class="sxs-lookup"><span data-stu-id="b1536-112">The message is a trace level 4.</span></span>|  
|`LStatusLevel0`|<span data-ttu-id="b1536-113">메시지의 상태 수준은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="b1536-113">The message is a status level 0.</span></span>|  
|`LStatusLevel1`|<span data-ttu-id="b1536-114">메시지는 상태 수준 1입니다.</span><span class="sxs-lookup"><span data-stu-id="b1536-114">The message is a status level 1.</span></span>|  
|`LStatusLevel2`|<span data-ttu-id="b1536-115">메시지는 상태 수준 2입니다.</span><span class="sxs-lookup"><span data-stu-id="b1536-115">The message is a status level 2.</span></span>|  
|`LStatusLevel3`|<span data-ttu-id="b1536-116">메시지는 상태 수준 3입니다.</span><span class="sxs-lookup"><span data-stu-id="b1536-116">The message is a status level 3.</span></span>|  
|`LStatusLevel4`|<span data-ttu-id="b1536-117">메시지는 상태 수준 4입니다.</span><span class="sxs-lookup"><span data-stu-id="b1536-117">The message is a status level 4.</span></span>|  
|`LWarningLevel`|<span data-ttu-id="b1536-118">메시지는 경고 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="b1536-118">The message is a warning level.</span></span>|  
|`LErrorLevel`|<span data-ttu-id="b1536-119">메시지는 오류 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="b1536-119">The message is an error level.</span></span>|  
|`LPanicLevel`|<span data-ttu-id="b1536-120">메시지는 비상 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="b1536-120">The message is a panic level.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1536-121">설명</span><span class="sxs-lookup"><span data-stu-id="b1536-121">Remarks</span></span>  
 <span data-ttu-id="b1536-122">CLR (공용 언어 런타임)은 [ICorDebugManagedCallback:: LogMessage](icordebugmanagedcallback-logmessage-method.md) 메서드를 호출 하 여 관리 되는 스레드가 이벤트를 기록 했음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b1536-122">The common language runtime (CLR) calls the [ICorDebugManagedCallback::LogMessage](icordebugmanagedcallback-logmessage-method.md) method to notify the debugger that a managed thread has logged an event.</span></span> <span data-ttu-id="b1536-123">CLR은 열거형 값을 전달 `LoggingLevelEnum` 하 여 관리 되는 스레드가 이벤트 로그에 기록 하는 메시지의 심각도 수준을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1536-123">The CLR passes a value of the `LoggingLevelEnum` enumeration to indicate the severity level of the message that the managed thread wrote to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1536-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b1536-124">Requirements</span></span>  
 <span data-ttu-id="b1536-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b1536-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1536-126">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1536-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1536-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1536-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1536-128">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1536-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1536-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1536-129">See also</span></span>

- <xref:System.Diagnostics.EventLog>
- [<span data-ttu-id="b1536-130">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="b1536-130">Debugging Enumerations</span></span>](debugging-enumerations.md)
