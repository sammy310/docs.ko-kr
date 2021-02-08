---
description: '자세히 알아보기: VariableLocationType 열거형'
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
ms.openlocfilehash: 8561077b9f3f4d318eeb743d51538b2a9a22a217
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800528"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="bd652-103">VariableLocationType 열거형</span><span class="sxs-lookup"><span data-stu-id="bd652-103">VariableLocationType Enumeration</span></span>

<span data-ttu-id="bd652-104">변수의 기본 위치 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bd652-104">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd652-105">구문</span><span class="sxs-lookup"><span data-stu-id="bd652-105">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="bd652-106">구성원</span><span class="sxs-lookup"><span data-stu-id="bd652-106">Members</span></span>  
  
|<span data-ttu-id="bd652-107">멤버</span><span class="sxs-lookup"><span data-stu-id="bd652-107">Member</span></span>|<span data-ttu-id="bd652-108">설명</span><span class="sxs-lookup"><span data-stu-id="bd652-108">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="bd652-109">변수가 레지스터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd652-109">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="bd652-110">변수가 등록 관련 메모리 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd652-110">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="bd652-111">변수는 레지스터 또는 등록 관련 메모리 위치에 저장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd652-111">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd652-112">설명</span><span class="sxs-lookup"><span data-stu-id="bd652-112">Remarks</span></span>  

 <span data-ttu-id="bd652-113">열거형의 멤버는 `VariableLocationType` [ICorDebugVariableHome:: GetLocationType](icordebugvariablehome-getlocationtype-method.md) 메서드에서 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd652-113">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd652-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd652-114">Requirements</span></span>  

 <span data-ttu-id="bd652-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bd652-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd652-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd652-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd652-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd652-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd652-118">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd652-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd652-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd652-119">See also</span></span>

- [<span data-ttu-id="bd652-120">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="bd652-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
