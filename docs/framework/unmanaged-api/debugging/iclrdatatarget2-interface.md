---
title: ICLRDataTarget2 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2
helpviewer_keywords:
- ICLRDataTarget2 interface [.NET Framework debugging]
ms.assetid: 94249397-861b-4294-a538-cf01466a66d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d21bced214242866c47f40f392593f3f51cda02f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104717"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="70913-102">ICLRDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="70913-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="70913-103">서브 클래스 [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) 대상 프로세스의 가상 메모리 영역을 조작 하는 데 데이터 액세스 서비스 계층에서 사용 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="70913-103">A subclass of [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70913-104">메서드</span><span class="sxs-lookup"><span data-stu-id="70913-104">Methods</span></span>  
  
|<span data-ttu-id="70913-105">메서드</span><span class="sxs-lookup"><span data-stu-id="70913-105">Method</span></span>|<span data-ttu-id="70913-106">설명</span><span class="sxs-lookup"><span data-stu-id="70913-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="70913-107">AllocVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="70913-107">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="70913-108">대상 프로세스의 주소 공간에 메모리를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="70913-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="70913-109">FreeVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="70913-109">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="70913-110">대상 프로세스의 주소 공간에 이전에 할당 된 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="70913-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70913-111">설명</span><span class="sxs-lookup"><span data-stu-id="70913-111">Remarks</span></span>  
 <span data-ttu-id="70913-112">API 클라이언트(즉, 디버거)에서는 이 인터페이스를 특정 대상 프로세스에 적절하게 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70913-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="70913-113">예를 들어 활성 프로세스의 구현은 메모리 덤프의 구현과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="70913-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="70913-114">대상에서 메모리 영역의 수정을 지원하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70913-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70913-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="70913-115">Requirements</span></span>  
 <span data-ttu-id="70913-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="70913-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70913-117">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="70913-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="70913-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70913-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="70913-119">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="70913-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="70913-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="70913-120">See also</span></span>

- [<span data-ttu-id="70913-121">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="70913-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
- [<span data-ttu-id="70913-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="70913-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
