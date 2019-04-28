---
title: COR_ACTIVE_FUNCTION 구조체
ms.date: 03/30/2017
api_name:
- COR_ACTIVE_FUNCTION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ACTIVE_FUNCTION
helpviewer_keywords:
- COR_ACTIVE_FUNCTION structure [.NET Framework debugging]
ms.assetid: ed86185f-2152-459c-961f-10c06d62e83f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0400da0cd29d642a1be42be7e2b22213ae54b94
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609662"
---
# <a name="coractivefunction-structure"></a><span data-ttu-id="89849-102">COR_ACTIVE_FUNCTION 구조체</span><span class="sxs-lookup"><span data-stu-id="89849-102">COR_ACTIVE_FUNCTION Structure</span></span>
<span data-ttu-id="89849-103">스레드 프레임에서 현재 활성 상태인 함수에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="89849-103">Contains information about the functions that are currently active in a thread's frames.</span></span> <span data-ttu-id="89849-104">이 구조체를 사용 합니다 [ICorDebugThread2::GetActiveFunctions](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="89849-104">This structure is used by the [ICorDebugThread2::GetActiveFunctions](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89849-105">구문</span><span class="sxs-lookup"><span data-stu-id="89849-105">Syntax</span></span>  
  
```  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="89849-106">멤버</span><span class="sxs-lookup"><span data-stu-id="89849-106">Members</span></span>  
  
|<span data-ttu-id="89849-107">멤버</span><span class="sxs-lookup"><span data-stu-id="89849-107">Member</span></span>|<span data-ttu-id="89849-108">설명</span><span class="sxs-lookup"><span data-stu-id="89849-108">Description</span></span>|  
|------------|-----------------|  
|`pAppDomain`|<span data-ttu-id="89849-109">응용 프로그램 도메인 소유자에 대 한 포인터를 `ilOffset` 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="89849-109">Pointer to the application domain owner of the `ilOffset` field.</span></span>|  
|`pModule`|<span data-ttu-id="89849-110">모듈 소유자에 대 한 포인터를 `ilOffset` 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="89849-110">Pointer to the module owner of the `ilOffset` field.</span></span>|  
|`pFunction`|<span data-ttu-id="89849-111">함수 소유자에 대 한 포인터를 `ilOffset` 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="89849-111">Pointer to the function owner of the `ilOffset` field.</span></span>|  
|`ilOffset`|<span data-ttu-id="89849-112">프레임의 Microsoft MSIL (intermediate language) 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="89849-112">The Microsoft intermediate language (MSIL) offset of the frame.</span></span>|  
|`flags`|<span data-ttu-id="89849-113">향후 확장성을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89849-113">Reserved for future extensibility.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="89849-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="89849-114">Requirements</span></span>  
 <span data-ttu-id="89849-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="89849-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89849-116">**헤더:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="89849-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="89849-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89849-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89849-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89849-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89849-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="89849-119">See also</span></span>

- [<span data-ttu-id="89849-120">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="89849-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="89849-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="89849-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
