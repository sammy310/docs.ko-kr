---
title: CorDebugUnmappedStop 열거형
ms.date: 03/30/2017
api_name:
- CorDebugUnmappedStop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUnmappedStop
helpviewer_keywords:
- CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type:
- apiref
ms.openlocfilehash: 23e168b0f322a580917c3fcfcb767a7d4d4628f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793881"
---
# <a name="cordebugunmappedstop-enumeration"></a><span data-ttu-id="c4de6-102">CorDebugUnmappedStop 열거형</span><span class="sxs-lookup"><span data-stu-id="c4de6-102">CorDebugUnmappedStop Enumeration</span></span>
<span data-ttu-id="c4de6-103">스텝퍼에 의해 코드 실행에서 중지를 트리거할 수 있는 매핑되지 않은 코드 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c4de6-103">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4de6-104">구문</span><span class="sxs-lookup"><span data-stu-id="c4de6-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugUnmappedStop {  
    STOP_NONE               = 0x0,  
    STOP_PROLOG             = 0x01,  
    STOP_EPILOG             = 0x02,  
    STOP_NO_MAPPING_INFO    = 0x04,  
    STOP_OTHER_UNMAPPED     = 0x08,  
    STOP_UNMANAGED          = 0x10,  
    STOP_ALL                = 0xffff,  
} CorDebugUnmappedStop;  
```  
  
## <a name="members"></a><span data-ttu-id="c4de6-105">Members</span><span class="sxs-lookup"><span data-stu-id="c4de6-105">Members</span></span>  
  
|<span data-ttu-id="c4de6-106">Member</span><span class="sxs-lookup"><span data-stu-id="c4de6-106">Member</span></span>|<span data-ttu-id="c4de6-107">설명</span><span class="sxs-lookup"><span data-stu-id="c4de6-107">Description</span></span>|  
|------------|-----------------|  
|`STOP_NONE`|<span data-ttu-id="c4de6-108">모든 형식의 매핑되지 않은 코드에서 중지 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="c4de6-108">Do not stop in any type of unmapped code.</span></span>|  
|`STOP_PROLOG`|<span data-ttu-id="c4de6-109">프롤로그 코드에서를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4de6-109">Stop in prolog code.</span></span>|  
|`STOP_EPILOG`|<span data-ttu-id="c4de6-110">에필로그 코드에서 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4de6-110">Stop in epilog code.</span></span>|  
|`STOP_NO_MAPPING_INFO`|<span data-ttu-id="c4de6-111">매핑 정보가 없는 코드에서를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4de6-111">Stop in code that has no mapping information.</span></span>|  
|`STOP_OTHER_UNMAPPED`|<span data-ttu-id="c4de6-112">프롤로그, 에필로그, 매핑되지 않음 정보 또는 관리 되지 않는 범주에 맞지 않는 매핑되지 않은 코드에서 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4de6-112">Stop in unmapped code that does not fit into the prolog, epilog, no-mapping-information, or unmanaged category.</span></span>|  
|`STOP_UNMANAGED`|<span data-ttu-id="c4de6-113">비관리 코드에서 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4de6-113">Stop in unmanaged code.</span></span> <span data-ttu-id="c4de6-114">이 값은 interop 디버깅에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4de6-114">This value is valid only with interop debugging.</span></span>|  
|`STOP_ALL`|<span data-ttu-id="c4de6-115">매핑되지 않은 모든 형식의 코드에서 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4de6-115">Stop in all types of unmapped code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4de6-116">주의</span><span class="sxs-lookup"><span data-stu-id="c4de6-116">Remarks</span></span>  
 <span data-ttu-id="c4de6-117">[ICorDebugStepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) 메서드를 사용 하 여 스텝 퍼가 중지 될 매핑되지 않은 코드를 지정 하는 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4de6-117">Use the [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) method to set the flags that specify the unmapped code in which the stepper will stop.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4de6-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c4de6-118">Requirements</span></span>  
 <span data-ttu-id="c4de6-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c4de6-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4de6-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4de6-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4de6-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4de6-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4de6-122">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4de6-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4de6-123">참조</span><span class="sxs-lookup"><span data-stu-id="c4de6-123">See also</span></span>

- [<span data-ttu-id="c4de6-124">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="c4de6-124">Debugging Enumerations</span></span>](debugging-enumerations.md)
