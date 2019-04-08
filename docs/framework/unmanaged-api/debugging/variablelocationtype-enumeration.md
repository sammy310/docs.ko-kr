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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099952"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="d59dd-102">VariableLocationType 열거형</span><span class="sxs-lookup"><span data-stu-id="d59dd-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="d59dd-103">변수의 네이티브 위치 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d59dd-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d59dd-104">구문</span><span class="sxs-lookup"><span data-stu-id="d59dd-104">Syntax</span></span>  
  
```  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="d59dd-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d59dd-105">Members</span></span>  
  
|<span data-ttu-id="d59dd-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d59dd-106">Member</span></span>|<span data-ttu-id="d59dd-107">설명</span><span class="sxs-lookup"><span data-stu-id="d59dd-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="d59dd-108">변수가 레지스터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d59dd-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="d59dd-109">변수가 레지스터 상대 메모리 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d59dd-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="d59dd-110">변수는 등록 또는 등록 관련 메모리 위치에 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d59dd-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d59dd-111">설명</span><span class="sxs-lookup"><span data-stu-id="d59dd-111">Remarks</span></span>  
 <span data-ttu-id="d59dd-112">멤버는 `VariableLocationType` 열거형에서 반환 되는 [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="d59dd-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d59dd-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d59dd-113">Requirements</span></span>  
 <span data-ttu-id="d59dd-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d59dd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d59dd-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d59dd-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d59dd-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d59dd-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d59dd-117">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="d59dd-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d59dd-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="d59dd-118">See also</span></span>

- [<span data-ttu-id="d59dd-119">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="d59dd-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
