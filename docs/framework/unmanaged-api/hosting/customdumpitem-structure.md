---
description: '자세히 알아보기: Customfcitem 구조체'
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
ms.openlocfilehash: 9bd7b2bb59675bc01e24dc6e6d0ce524f3d35466
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716902"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="f06cd-103">CustomDumpItem 구조체</span><span class="sxs-lookup"><span data-stu-id="f06cd-103">CustomDumpItem Structure</span></span>

<span data-ttu-id="f06cd-104">오류 보고에서 사용자 지정 덤프에 추가할 항목을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06cd-104">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f06cd-105">구문</span><span class="sxs-lookup"><span data-stu-id="f06cd-105">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="f06cd-106">구성원</span><span class="sxs-lookup"><span data-stu-id="f06cd-106">Members</span></span>  
  
|<span data-ttu-id="f06cd-107">멤버</span><span class="sxs-lookup"><span data-stu-id="f06cd-107">Member</span></span>|<span data-ttu-id="f06cd-108">설명</span><span class="sxs-lookup"><span data-stu-id="f06cd-108">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="f06cd-109">추가할 항목의 종류를 나타내는 [ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f06cd-109">An [ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="f06cd-110">현재 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f06cd-110">Not currently used.</span></span> <span data-ttu-id="f06cd-111">공용 구조체에 추가 된 항목은 포인터 크기 보다 크지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06cd-111">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="f06cd-112">`struct`가 필요한 경우 별도로 할당 하 고이를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06cd-112">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f06cd-113">설명</span><span class="sxs-lookup"><span data-stu-id="f06cd-113">Remarks</span></span>  

 <span data-ttu-id="f06cd-114">[ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) 는 형식의 매개 변수를 사용 `CustomDumpItem` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06cd-114">[ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f06cd-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f06cd-115">Requirements</span></span>  

 <span data-ttu-id="f06cd-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f06cd-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f06cd-117">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f06cd-117">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="f06cd-118">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06cd-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f06cd-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f06cd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f06cd-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f06cd-120">See also</span></span>

- [<span data-ttu-id="f06cd-121">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="f06cd-121">Hosting Structures</span></span>](hosting-structures.md)
