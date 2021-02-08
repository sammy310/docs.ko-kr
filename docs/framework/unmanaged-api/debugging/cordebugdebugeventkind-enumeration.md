---
description: '자세한 정보: CorDebugDebugEventKind 열거형'
title: CorDebugDebugEventKind 열거형
ms.date: 03/30/2017
api_name:
- CorDebugDebugEventKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6075a6cd-97e6-4472-a090-0dd14860d1f3
topic_type:
- apiref
ms.openlocfilehash: 62094c934873a74fdab01fad87c42126e28cb0f4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801711"
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="c8c48-103">CorDebugDebugEventKind 열거형</span><span class="sxs-lookup"><span data-stu-id="c8c48-103">CorDebugDebugEventKind Enumeration</span></span>

<span data-ttu-id="c8c48-104">[DecodeEvent](icordebugprocess6-decodeevent-method.md) 메서드가 정보를 디코딩하는 이벤트의 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c8c48-104">Indicates the type of event whose information is decoded by the [DecodeEvent](icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8c48-105">구문</span><span class="sxs-lookup"><span data-stu-id="c8c48-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDebugEventKind {  
    DEBUG_EVENT_KIND_MODULE_LOADED                          = 1,  
    DEBUG_EVENT_KIND_MODULE_UNLOADED                        = 2,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE         = 3,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE    = 4,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND  = 5,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED            = 6  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="c8c48-106">구성원</span><span class="sxs-lookup"><span data-stu-id="c8c48-106">Members</span></span>  
  
|<span data-ttu-id="c8c48-107">멤버</span><span class="sxs-lookup"><span data-stu-id="c8c48-107">Member</span></span>|<span data-ttu-id="c8c48-108">설명</span><span class="sxs-lookup"><span data-stu-id="c8c48-108">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="c8c48-109">모듈 로드 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="c8c48-109">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="c8c48-110">모듈 언로드 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="c8c48-110">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="c8c48-111">첫째 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="c8c48-111">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="c8c48-112">첫째 사용자 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="c8c48-112">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="c8c48-113">`catch` 처리기가 있는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="c8c48-113">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="c8c48-114">처리되지 않은 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="c8c48-114">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8c48-115">설명</span><span class="sxs-lookup"><span data-stu-id="c8c48-115">Remarks</span></span>  

 <span data-ttu-id="c8c48-116">`CorDebugDebugEventKind` [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) 메서드를 호출 하 여 열거형의 멤버를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8c48-116">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c8c48-117">이 열거형은 .NET 네이티브 디버깅 시나리오에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8c48-117">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8c48-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c8c48-118">Requirements</span></span>  

 <span data-ttu-id="c8c48-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8c48-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8c48-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8c48-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8c48-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8c48-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8c48-122">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8c48-122">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8c48-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8c48-123">See also</span></span>

- [<span data-ttu-id="c8c48-124">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="c8c48-124">Debugging Enumerations</span></span>](debugging-enumerations.md)
