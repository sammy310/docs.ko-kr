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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac0f5d522a24394369583692f8c564254529bf13
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137352"
---
# <a name="stackoverflowinfo-structure"></a><span data-ttu-id="f2d71-102">StackOverflowInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="f2d71-102">StackOverflowInfo Structure</span></span>
<span data-ttu-id="f2d71-103">오버플로 인해 throw 된 예외 유형 발생 한 오버플로 및 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2d71-103">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2d71-104">구문</span><span class="sxs-lookup"><span data-stu-id="f2d71-104">Syntax</span></span>  
  
```  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="f2d71-105">멤버</span><span class="sxs-lookup"><span data-stu-id="f2d71-105">Members</span></span>  
  
|<span data-ttu-id="f2d71-106">멤버</span><span class="sxs-lookup"><span data-stu-id="f2d71-106">Member</span></span>|<span data-ttu-id="f2d71-107">설명</span><span class="sxs-lookup"><span data-stu-id="f2d71-107">Description</span></span>|  
|------------|-----------------|  
|`soType`|<span data-ttu-id="f2d71-108">값을 [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) 오버플로의 형식을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="f2d71-108">A value of the [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) enumeration that specifies the type of overflow.</span></span>|  
|`pExceptionInfo`|<span data-ttu-id="f2d71-109">Win32에 대 한 포인터 `EXCEPTION_POINTERS` 예외가 컴퓨터 독립적 설명과 함께 예외 레코드 및 예외 시 컴퓨터 종속 설명은 프로세서 컨텍스트를 사용 하 여 컨텍스트 레코드를 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f2d71-109">A pointer to a Win32 `EXCEPTION_POINTERS` object, which contains an exception record with a machine-independent description of an exception and a context record with a machine-dependent description of the processor context at the time of the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2d71-110">설명</span><span class="sxs-lookup"><span data-stu-id="f2d71-110">Remarks</span></span>  
 <span data-ttu-id="f2d71-111">A `StackOverflowInfo` 개체를 전달 하는 [iactiononclrevent:: Onevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) 에 대 한 메서드 `Event_StackOverflow` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="f2d71-111">A `StackOverflowInfo` object is passed to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method for `Event_StackOverflow` events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2d71-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f2d71-112">Requirements</span></span>  
 <span data-ttu-id="f2d71-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f2d71-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2d71-114">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="f2d71-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="f2d71-115">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f2d71-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f2d71-116">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="f2d71-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f2d71-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="f2d71-117">See also</span></span>

- [<span data-ttu-id="f2d71-118">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="f2d71-118">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
