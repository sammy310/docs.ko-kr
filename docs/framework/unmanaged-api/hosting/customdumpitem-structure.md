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
ms.openlocfilehash: 154beef9398029f31dcb4d081019b9f292238af4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176476"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="7940a-102">CustomDumpItem 구조체</span><span class="sxs-lookup"><span data-stu-id="7940a-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="7940a-103">오류 보고에서 사용자 지정 덤프에 추가할 항목을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7940a-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7940a-104">구문</span><span class="sxs-lookup"><span data-stu-id="7940a-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="7940a-105">구성원</span><span class="sxs-lookup"><span data-stu-id="7940a-105">Members</span></span>  
  
|<span data-ttu-id="7940a-106">멤버</span><span class="sxs-lookup"><span data-stu-id="7940a-106">Member</span></span>|<span data-ttu-id="7940a-107">Description</span><span class="sxs-lookup"><span data-stu-id="7940a-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="7940a-108">추가할 항목의 종류를 나타내는 [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7940a-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="7940a-109">현재 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7940a-109">Not currently used.</span></span> <span data-ttu-id="7940a-110">공용 구조에 추가된 항목은 포인터 크기보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7940a-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="7940a-111">a가 `struct` 필요한 경우 별도로 할당하고 가리가야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7940a-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7940a-112">설명</span><span class="sxs-lookup"><span data-stu-id="7940a-112">Remarks</span></span>  
 <span data-ttu-id="7940a-113">[ICLR오류 보고 관리자::시작 사용자 지정](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) `CustomDumpItem`덤프 형식의 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7940a-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7940a-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7940a-114">Requirements</span></span>  
 <span data-ttu-id="7940a-115">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7940a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7940a-116">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="7940a-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="7940a-117">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7940a-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7940a-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7940a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7940a-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7940a-119">See also</span></span>

- [<span data-ttu-id="7940a-120">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="7940a-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
