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
ms.openlocfilehash: 808fc70a308eff1b05aa49ea2bb89fe53377c973
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795848"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="a9cea-102">CorDebugIlToNativeMappingTypes 열거형</span><span class="sxs-lookup"><span data-stu-id="a9cea-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="a9cea-103">COR_DEBUG_IL_TO_NATIVE_MAP 구조의 인스턴스로 표시 되는 특정 범위의 기본 명령이 특수 코드 영역에 해당 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a9cea-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9cea-104">구문</span><span class="sxs-lookup"><span data-stu-id="a9cea-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="a9cea-105">구성원</span><span class="sxs-lookup"><span data-stu-id="a9cea-105">Members</span></span>  
  
|<span data-ttu-id="a9cea-106">멤버</span><span class="sxs-lookup"><span data-stu-id="a9cea-106">Member</span></span>|<span data-ttu-id="a9cea-107">설명</span><span class="sxs-lookup"><span data-stu-id="a9cea-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="a9cea-108">네이티브 명령의 범위가 특별 한 코드 영역과 일치 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9cea-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="a9cea-109">네이티브 명령의 범위는 프롤로그에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9cea-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="a9cea-110">네이티브 명령의 범위는 에필로그에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9cea-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a9cea-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a9cea-111">Requirements</span></span>  
 <span data-ttu-id="a9cea-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a9cea-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9cea-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9cea-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9cea-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9cea-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9cea-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9cea-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9cea-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9cea-116">See also</span></span>

- [<span data-ttu-id="a9cea-117">GetILToNativeMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="a9cea-117">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="a9cea-118">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="a9cea-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
