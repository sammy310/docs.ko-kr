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
ms.openlocfilehash: c77e93686c7d121e9fe2a92f03970404ab823dc0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673243"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="d7430-102">CustomDumpItem 구조체</span><span class="sxs-lookup"><span data-stu-id="d7430-102">CustomDumpItem Structure</span></span>

<span data-ttu-id="d7430-103">오류 보고에서 사용자 지정 덤프에 추가할 항목을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7430-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7430-104">구문</span><span class="sxs-lookup"><span data-stu-id="d7430-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="d7430-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d7430-105">Members</span></span>  
  
|<span data-ttu-id="d7430-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d7430-106">Member</span></span>|<span data-ttu-id="d7430-107">설명</span><span class="sxs-lookup"><span data-stu-id="d7430-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="d7430-108">추가할 항목의 종류를 나타내는 [ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d7430-108">An [ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="d7430-109">현재 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7430-109">Not currently used.</span></span> <span data-ttu-id="d7430-110">공용 구조체에 추가 된 항목은 포인터 크기 보다 크지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7430-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="d7430-111">`struct`가 필요한 경우 별도로 할당 하 고이를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7430-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7430-112">설명</span><span class="sxs-lookup"><span data-stu-id="d7430-112">Remarks</span></span>  

 <span data-ttu-id="d7430-113">[ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) 는 형식의 매개 변수를 사용 `CustomDumpItem` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7430-113">[ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7430-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7430-114">Requirements</span></span>  

 <span data-ttu-id="d7430-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7430-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7430-116">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d7430-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="d7430-117">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7430-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d7430-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7430-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7430-119">참조</span><span class="sxs-lookup"><span data-stu-id="d7430-119">See also</span></span>

- [<span data-ttu-id="d7430-120">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="d7430-120">Hosting Structures</span></span>](hosting-structures.md)
