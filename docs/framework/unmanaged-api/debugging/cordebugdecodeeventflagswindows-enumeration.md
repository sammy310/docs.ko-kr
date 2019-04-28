---
title: CorDebugDecodeEventFlagsWindows 열거형
ms.date: 03/30/2017
api_name:
- CorDebugDecodeEventFlagsWindows
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aa6cf962-30ae-4cfd-8895-826deeb46a54
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d4e006a03db5b16de93dfd07ec7b964db4bfc1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609219"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="d1a5b-102">CorDebugDecodeEventFlagsWindows 열거형</span><span class="sxs-lookup"><span data-stu-id="d1a5b-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>
<span data-ttu-id="d1a5b-103">Windows 플랫폼에서 디버그 이벤트에 대한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a5b-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1a5b-104">구문</span><span class="sxs-lookup"><span data-stu-id="d1a5b-104">Syntax</span></span>  
  
```  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="d1a5b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d1a5b-105">Members</span></span>  
  
|<span data-ttu-id="d1a5b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d1a5b-106">Member</span></span>|<span data-ttu-id="d1a5b-107">설명</span><span class="sxs-lookup"><span data-stu-id="d1a5b-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="d1a5b-108">디버그 이벤트가 첫째 예외임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d1a5b-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1a5b-109">설명</span><span class="sxs-lookup"><span data-stu-id="d1a5b-109">Remarks</span></span>  
 <span data-ttu-id="d1a5b-110">합니다 [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) 메서드를 포함 한 `dwFlags` 매개 변수는 디버그 이벤트에 대 한 추가 정보를 제공 하 고 값이 대상 아키텍처에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="d1a5b-110">The [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="d1a5b-111">`CorDebugDecodeEventFlagsWindows` 열거형을 Windows 플랫폼의 디버그 이벤트와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1a5b-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1a5b-112">이 열거형은 .NET 네이티브 디버깅 시나리오에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1a5b-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1a5b-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1a5b-113">Requirements</span></span>  
 <span data-ttu-id="d1a5b-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1a5b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1a5b-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1a5b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1a5b-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1a5b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1a5b-117">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1a5b-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1a5b-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="d1a5b-118">See also</span></span>

- [<span data-ttu-id="d1a5b-119">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="d1a5b-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
