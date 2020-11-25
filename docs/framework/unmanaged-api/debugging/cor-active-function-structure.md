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
ms.openlocfilehash: c50ba530d78296ebb956329b2f34b4f1e5cae94c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727421"
---
# <a name="cor_active_function-structure"></a><span data-ttu-id="d9b16-102">COR_ACTIVE_FUNCTION 구조체</span><span class="sxs-lookup"><span data-stu-id="d9b16-102">COR_ACTIVE_FUNCTION Structure</span></span>

<span data-ttu-id="d9b16-103">스레드 프레임에서 현재 활성 상태인 함수에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d9b16-103">Contains information about the functions that are currently active in a thread's frames.</span></span> <span data-ttu-id="d9b16-104">이 구조는 [ICorDebugThread2:: GetActiveFunctions](icordebugthread2-getactivefunctions-method.md) 메서드에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9b16-104">This structure is used by the [ICorDebugThread2::GetActiveFunctions](icordebugthread2-getactivefunctions-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9b16-105">구문</span><span class="sxs-lookup"><span data-stu-id="d9b16-105">Syntax</span></span>  
  
```cpp  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="d9b16-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d9b16-106">Members</span></span>  
  
|<span data-ttu-id="d9b16-107">멤버</span><span class="sxs-lookup"><span data-stu-id="d9b16-107">Member</span></span>|<span data-ttu-id="d9b16-108">설명</span><span class="sxs-lookup"><span data-stu-id="d9b16-108">Description</span></span>|  
|------------|-----------------|  
|`pAppDomain`|<span data-ttu-id="d9b16-109">필드의 응용 프로그램 도메인 소유자에 대 한 포인터 `ilOffset` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d9b16-109">Pointer to the application domain owner of the `ilOffset` field.</span></span>|  
|`pModule`|<span data-ttu-id="d9b16-110">필드의 모듈 소유자에 대 한 포인터 `ilOffset` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d9b16-110">Pointer to the module owner of the `ilOffset` field.</span></span>|  
|`pFunction`|<span data-ttu-id="d9b16-111">필드의 함수 소유자에 대 한 포인터 `ilOffset` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d9b16-111">Pointer to the function owner of the `ilOffset` field.</span></span>|  
|`ilOffset`|<span data-ttu-id="d9b16-112">프레임의 MSIL (Microsoft 중간 언어) 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="d9b16-112">The Microsoft intermediate language (MSIL) offset of the frame.</span></span>|  
|`flags`|<span data-ttu-id="d9b16-113">향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d9b16-113">Reserved for future extensibility.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d9b16-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d9b16-114">Requirements</span></span>  

 <span data-ttu-id="d9b16-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9b16-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9b16-116">**헤더:** CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="d9b16-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="d9b16-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9b16-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9b16-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9b16-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9b16-119">참조</span><span class="sxs-lookup"><span data-stu-id="d9b16-119">See also</span></span>

- [<span data-ttu-id="d9b16-120">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="d9b16-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="d9b16-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="d9b16-121">Debugging</span></span>](index.md)
