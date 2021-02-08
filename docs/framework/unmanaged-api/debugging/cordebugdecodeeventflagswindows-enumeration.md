---
description: '자세히 알아보기: CorDebugDecodeEventFlagsWindows 열거형'
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
ms.openlocfilehash: 765ce4b967d00bd70becca666e2ed418614d6fe3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801698"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="d23fa-103">CorDebugDecodeEventFlagsWindows 열거형</span><span class="sxs-lookup"><span data-stu-id="d23fa-103">CorDebugDecodeEventFlagsWindows Enumeration</span></span>

<span data-ttu-id="d23fa-104">Windows 플랫폼에서 디버그 이벤트에 대한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d23fa-104">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d23fa-105">구문</span><span class="sxs-lookup"><span data-stu-id="d23fa-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="d23fa-106">구성원</span><span class="sxs-lookup"><span data-stu-id="d23fa-106">Members</span></span>  
  
|<span data-ttu-id="d23fa-107">멤버</span><span class="sxs-lookup"><span data-stu-id="d23fa-107">Member</span></span>|<span data-ttu-id="d23fa-108">설명</span><span class="sxs-lookup"><span data-stu-id="d23fa-108">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="d23fa-109">디버그 이벤트가 첫째 예외임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d23fa-109">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d23fa-110">설명</span><span class="sxs-lookup"><span data-stu-id="d23fa-110">Remarks</span></span>  

 <span data-ttu-id="d23fa-111">[ICorDebugProcess6::D ecodeevent](icordebugprocess6-decodeevent-method.md) 메서드에는 `dwFlags` 디버그 이벤트에 대 한 추가 정보를 제공 하 고 값이 대상 아키텍처에 따라 달라 지는 매개 변수가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d23fa-111">The [ICorDebugProcess6::DecodeEvent](icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="d23fa-112">`CorDebugDecodeEventFlagsWindows` 열거형을 Windows 플랫폼의 디버그 이벤트와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d23fa-112">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d23fa-113">이 열거형은 .NET 네이티브 디버깅 시나리오에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d23fa-113">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d23fa-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d23fa-114">Requirements</span></span>  

 <span data-ttu-id="d23fa-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d23fa-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d23fa-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d23fa-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d23fa-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d23fa-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d23fa-118">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d23fa-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d23fa-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d23fa-119">See also</span></span>

- [<span data-ttu-id="d23fa-120">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="d23fa-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
