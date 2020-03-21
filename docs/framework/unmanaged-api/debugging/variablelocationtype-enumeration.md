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
ms.openlocfilehash: e2fa5d5a998f51e0e90cfde22b40ec12f278307b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178359"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="6ceba-102">VariableLocationType 열거형</span><span class="sxs-lookup"><span data-stu-id="6ceba-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="6ceba-103">변수의 기본 위치 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6ceba-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ceba-104">구문</span><span class="sxs-lookup"><span data-stu-id="6ceba-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="6ceba-105">구성원</span><span class="sxs-lookup"><span data-stu-id="6ceba-105">Members</span></span>  
  
|<span data-ttu-id="6ceba-106">멤버</span><span class="sxs-lookup"><span data-stu-id="6ceba-106">Member</span></span>|<span data-ttu-id="6ceba-107">Description</span><span class="sxs-lookup"><span data-stu-id="6ceba-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="6ceba-108">변수가 레지스터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ceba-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="6ceba-109">변수는 레지스터 상대 메모리 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ceba-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="6ceba-110">변수는 레지스터 또는 레지스터 상대 메모리 위치에 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ceba-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ceba-111">설명</span><span class="sxs-lookup"><span data-stu-id="6ceba-111">Remarks</span></span>  
 <span data-ttu-id="6ceba-112">열거형의 `VariableLocationType` 멤버는 [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) 메서드에 의해 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ceba-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ceba-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ceba-113">Requirements</span></span>  
 <span data-ttu-id="6ceba-114">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ceba-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ceba-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ceba-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ceba-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ceba-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ceba-117">**.NET Framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ceba-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ceba-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ceba-118">See also</span></span>

- [<span data-ttu-id="6ceba-119">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="6ceba-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
