---
title: CustomDumpItem 구조체
ms.date: 03/30/2017
api_name:
- CustomDumpItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CustomDumpItem
helpviewer_keywords:
- CustomDumpItem structure [.NET Framework hosting]
ms.assetid: fd9085ff-7beb-4c38-97f0-037cd8ba4f65
topic_type:
- apiref
ms.openlocfilehash: ae64edd8a3a628100d4c51d0b78be1bc8d49fc17
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138289"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="1a47b-102">CustomDumpItem 구조체</span><span class="sxs-lookup"><span data-stu-id="1a47b-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="1a47b-103">오류 보고에서 사용자 지정 덤프에 추가할 항목을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a47b-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a47b-104">구문</span><span class="sxs-lookup"><span data-stu-id="1a47b-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="1a47b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="1a47b-105">Members</span></span>  
  
|<span data-ttu-id="1a47b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="1a47b-106">Member</span></span>|<span data-ttu-id="1a47b-107">설명</span><span class="sxs-lookup"><span data-stu-id="1a47b-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="1a47b-108">추가할 항목의 종류를 나타내는 [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1a47b-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="1a47b-109">현재 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a47b-109">Not currently used.</span></span> <span data-ttu-id="1a47b-110">공용 구조체에 추가 된 항목은 포인터 크기 보다 크지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a47b-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="1a47b-111">`struct` 필요한 경우 별도로 할당 하 고이를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a47b-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a47b-112">주의</span><span class="sxs-lookup"><span data-stu-id="1a47b-112">Remarks</span></span>  
 <span data-ttu-id="1a47b-113">[ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) 는 `CustomDumpItem`형식의 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a47b-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a47b-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1a47b-114">Requirements</span></span>  
 <span data-ttu-id="1a47b-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a47b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a47b-116">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1a47b-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="1a47b-117">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a47b-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1a47b-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a47b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a47b-119">참조</span><span class="sxs-lookup"><span data-stu-id="1a47b-119">See also</span></span>

- [<span data-ttu-id="1a47b-120">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="1a47b-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
