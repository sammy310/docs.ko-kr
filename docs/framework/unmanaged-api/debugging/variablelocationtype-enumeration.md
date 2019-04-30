---
title: VariableLocationType 열거형
ms.date: 03/30/2017
api_name:
- VariableLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- VariableLocationType
helpviewer_keywords:
- VariableLocationType enumeration [.NET Framework debugging]
ms.assetid: 8635ee3a-c84b-4626-876c-416bee54f787
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 392254efcd099aca60e58b3cc0bc61ca85aa2c66
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986520"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="1a349-102">VariableLocationType 열거형</span><span class="sxs-lookup"><span data-stu-id="1a349-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="1a349-103">변수의 네이티브 위치 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1a349-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a349-104">구문</span><span class="sxs-lookup"><span data-stu-id="1a349-104">Syntax</span></span>  
  
```  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="1a349-105">멤버</span><span class="sxs-lookup"><span data-stu-id="1a349-105">Members</span></span>  
  
|<span data-ttu-id="1a349-106">멤버</span><span class="sxs-lookup"><span data-stu-id="1a349-106">Member</span></span>|<span data-ttu-id="1a349-107">설명</span><span class="sxs-lookup"><span data-stu-id="1a349-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="1a349-108">변수가 레지스터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a349-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="1a349-109">변수가 레지스터 상대 메모리 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a349-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="1a349-110">변수는 등록 또는 등록 관련 메모리 위치에 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a349-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a349-111">설명</span><span class="sxs-lookup"><span data-stu-id="1a349-111">Remarks</span></span>  
 <span data-ttu-id="1a349-112">멤버는 `VariableLocationType` 열거형에서 반환 되는 [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="1a349-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a349-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1a349-113">Requirements</span></span>  
 <span data-ttu-id="1a349-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1a349-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a349-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a349-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a349-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a349-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a349-117">**.NET Framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a349-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a349-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="1a349-118">See also</span></span>

- [<span data-ttu-id="1a349-119">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="1a349-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
