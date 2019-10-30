---
title: StackOverflowInfo 구조체
ms.date: 03/30/2017
api_name:
- StackOverflowInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowInfo
helpviewer_keywords:
- StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type:
- apiref
ms.openlocfilehash: 1072026f92edbc646653c6dd74ec8e22d5b887e5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105915"
---
# <a name="stackoverflowinfo-structure"></a><span data-ttu-id="9ccf0-102">StackOverflowInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="9ccf0-102">StackOverflowInfo Structure</span></span>
<span data-ttu-id="9ccf0-103">발생 한 오버플로 형식과 오버플로로 인해 throw 된 예외에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccf0-103">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ccf0-104">구문</span><span class="sxs-lookup"><span data-stu-id="9ccf0-104">Syntax</span></span>  
  
```cpp  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="9ccf0-105">멤버</span><span class="sxs-lookup"><span data-stu-id="9ccf0-105">Members</span></span>  
  
|<span data-ttu-id="9ccf0-106">멤버</span><span class="sxs-lookup"><span data-stu-id="9ccf0-106">Member</span></span>|<span data-ttu-id="9ccf0-107">설명</span><span class="sxs-lookup"><span data-stu-id="9ccf0-107">Description</span></span>|  
|------------|-----------------|  
|`soType`|<span data-ttu-id="9ccf0-108">오버플로 유형을 지정 하는 [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9ccf0-108">A value of the [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) enumeration that specifies the type of overflow.</span></span>|  
|`pExceptionInfo`|<span data-ttu-id="9ccf0-109">예외에 대 한 컴퓨터 독립적 설명과 함께 예외 레코드를 포함 하는 Win32 `EXCEPTION_POINTERS` 개체에 대 한 포인터로, 예외 발생 시 프로세서 컨텍스트에 대 한 컴퓨터 종속 설명을 포함 하는 컨텍스트 레코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ccf0-109">A pointer to a Win32 `EXCEPTION_POINTERS` object, which contains an exception record with a machine-independent description of an exception and a context record with a machine-dependent description of the processor context at the time of the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ccf0-110">주의</span><span class="sxs-lookup"><span data-stu-id="9ccf0-110">Remarks</span></span>  
 <span data-ttu-id="9ccf0-111">`StackOverflowInfo` 개체는 `Event_StackOverflow` 이벤트에 대해 [IActionOnCLREvent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) 메서드에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ccf0-111">A `StackOverflowInfo` object is passed to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method for `Event_StackOverflow` events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ccf0-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9ccf0-112">Requirements</span></span>  
 <span data-ttu-id="9ccf0-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ccf0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ccf0-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9ccf0-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="9ccf0-115">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ccf0-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ccf0-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ccf0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ccf0-117">참조</span><span class="sxs-lookup"><span data-stu-id="9ccf0-117">See also</span></span>

- [<span data-ttu-id="9ccf0-118">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="9ccf0-118">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
