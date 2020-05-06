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
ms.openlocfilehash: a90ddd27834e7614c1827d606a9955b4d6c53127
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795978"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="e1bd4-102">CorDebugDecodeEventFlagsWindows 열거형</span><span class="sxs-lookup"><span data-stu-id="e1bd4-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>
<span data-ttu-id="e1bd4-103">Windows 플랫폼에서 디버그 이벤트에 대한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1bd4-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1bd4-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="e1bd4-105">구성원</span><span class="sxs-lookup"><span data-stu-id="e1bd4-105">Members</span></span>  
  
|<span data-ttu-id="e1bd4-106">멤버</span><span class="sxs-lookup"><span data-stu-id="e1bd4-106">Member</span></span>|<span data-ttu-id="e1bd4-107">설명</span><span class="sxs-lookup"><span data-stu-id="e1bd4-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="e1bd4-108">디버그 이벤트가 첫째 예외임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1bd4-109">설명</span><span class="sxs-lookup"><span data-stu-id="e1bd4-109">Remarks</span></span>  
 <span data-ttu-id="e1bd4-110">[ICorDebugProcess6::D ecodeevent](icordebugprocess6-decodeevent-method.md) 메서드에는 디버그 이벤트 `dwFlags` 에 대 한 추가 정보를 제공 하 고 값이 대상 아키텍처에 따라 달라 지는 매개 변수가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-110">The [ICorDebugProcess6::DecodeEvent](icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="e1bd4-111">`CorDebugDecodeEventFlagsWindows` 열거형을 Windows 플랫폼의 디버그 이벤트와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1bd4-112">이 열거형은 .NET 네이티브 디버깅 시나리오에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1bd4-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1bd4-113">Requirements</span></span>  
 <span data-ttu-id="e1bd4-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1bd4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1bd4-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1bd4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1bd4-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1bd4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1bd4-117">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1bd4-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1bd4-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1bd4-118">See also</span></span>

- [<span data-ttu-id="e1bd4-119">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="e1bd4-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
