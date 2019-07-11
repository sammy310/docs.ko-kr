---
title: CorDebugIlToNativeMappingTypes 열거형
ms.date: 03/30/2017
api_name:
- CorDebugIlToNativeMappingTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIlToNativeMappingTypes
helpviewer_keywords:
- CorDebugIIToNativeMappingTypes enumeration [.NET Framework debugging]
ms.assetid: c35e2919-42c3-4ba0-ae28-443c35f66f93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c7d9f5373f2b4ea216ca517813b1334b9f5c38a6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739961"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="150b0-102">CorDebugIlToNativeMappingTypes 열거형</span><span class="sxs-lookup"><span data-stu-id="150b0-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="150b0-103">COR_DEBUG_IL_TO_NATIVE_MAP 구조체의 인스턴스로 표시 되는 기본 명령의 특정 범위가 특수 코드 영역에 해당 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="150b0-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="150b0-104">구문</span><span class="sxs-lookup"><span data-stu-id="150b0-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="150b0-105">멤버</span><span class="sxs-lookup"><span data-stu-id="150b0-105">Members</span></span>  
  
|<span data-ttu-id="150b0-106">멤버</span><span class="sxs-lookup"><span data-stu-id="150b0-106">Member</span></span>|<span data-ttu-id="150b0-107">Description</span><span class="sxs-lookup"><span data-stu-id="150b0-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="150b0-108">기본 명령의 범위가 특수 코드 영역에 일치 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="150b0-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="150b0-109">네이티브 지침의 범위는 프롤로그에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="150b0-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="150b0-110">네이티브 지침의 범위는 에필로그에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="150b0-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="150b0-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="150b0-111">Requirements</span></span>  
 <span data-ttu-id="150b0-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="150b0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="150b0-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="150b0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="150b0-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="150b0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="150b0-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="150b0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="150b0-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="150b0-116">See also</span></span>

- [<span data-ttu-id="150b0-117">GetILToNativeMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="150b0-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="150b0-118">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="150b0-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
