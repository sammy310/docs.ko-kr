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
ms.openlocfilehash: 1aa59ee559abff8006f0ac63a812e4315aa48154
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790303"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="4830f-102">VariableLocationType 열거형</span><span class="sxs-lookup"><span data-stu-id="4830f-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="4830f-103">변수의 기본 위치 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4830f-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4830f-104">구문</span><span class="sxs-lookup"><span data-stu-id="4830f-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="4830f-105">Members</span><span class="sxs-lookup"><span data-stu-id="4830f-105">Members</span></span>  
  
|<span data-ttu-id="4830f-106">Member</span><span class="sxs-lookup"><span data-stu-id="4830f-106">Member</span></span>|<span data-ttu-id="4830f-107">설명</span><span class="sxs-lookup"><span data-stu-id="4830f-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="4830f-108">변수가 레지스터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4830f-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="4830f-109">변수가 등록 관련 메모리 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4830f-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="4830f-110">변수는 레지스터 또는 등록 관련 메모리 위치에 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4830f-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4830f-111">주의</span><span class="sxs-lookup"><span data-stu-id="4830f-111">Remarks</span></span>  
 <span data-ttu-id="4830f-112">`VariableLocationType` 열거형의 멤버는 [ICorDebugVariableHome:: GetLocationType](icordebugvariablehome-getlocationtype-method.md) 메서드에서 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4830f-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4830f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4830f-113">Requirements</span></span>  
 <span data-ttu-id="4830f-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4830f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4830f-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4830f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4830f-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4830f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4830f-117">**.NET Framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4830f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4830f-118">참조</span><span class="sxs-lookup"><span data-stu-id="4830f-118">See also</span></span>

- [<span data-ttu-id="4830f-119">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="4830f-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
