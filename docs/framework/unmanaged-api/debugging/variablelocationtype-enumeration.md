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
ms.openlocfilehash: 455fd06dbdbfd5d9753f3d7270647a742751d804
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420658"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="5ff9f-102">VariableLocationType 열거형</span><span class="sxs-lookup"><span data-stu-id="5ff9f-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="5ff9f-103">변수의 기본 위치 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5ff9f-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ff9f-104">구문</span><span class="sxs-lookup"><span data-stu-id="5ff9f-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="5ff9f-105">멤버</span><span class="sxs-lookup"><span data-stu-id="5ff9f-105">Members</span></span>  
  
|<span data-ttu-id="5ff9f-106">멤버</span><span class="sxs-lookup"><span data-stu-id="5ff9f-106">Member</span></span>|<span data-ttu-id="5ff9f-107">설명</span><span class="sxs-lookup"><span data-stu-id="5ff9f-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="5ff9f-108">변수가 레지스터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff9f-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="5ff9f-109">변수가 등록 관련 메모리 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff9f-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="5ff9f-110">변수는 레지스터 또는 등록 관련 메모리 위치에 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff9f-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ff9f-111">설명</span><span class="sxs-lookup"><span data-stu-id="5ff9f-111">Remarks</span></span>  
 <span data-ttu-id="5ff9f-112">열거형의 멤버는 `VariableLocationType` [ICorDebugVariableHome:: GetLocationType](icordebugvariablehome-getlocationtype-method.md) 메서드에서 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ff9f-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ff9f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ff9f-113">Requirements</span></span>  
 <span data-ttu-id="5ff9f-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ff9f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ff9f-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ff9f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ff9f-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ff9f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ff9f-117">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ff9f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff9f-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ff9f-118">See also</span></span>

- [<span data-ttu-id="5ff9f-119">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="5ff9f-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
