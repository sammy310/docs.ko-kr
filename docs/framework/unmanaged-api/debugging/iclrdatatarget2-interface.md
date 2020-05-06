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
ms.openlocfilehash: 6b2700b2f12e312f06640a06e5ec82fbc58f2ca9
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860470"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="00710-102">ICLRDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00710-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="00710-103">데이터 액세스 서비스 계층에서 대상 프로세스의 가상 메모리 영역을 조작 하는 데 사용 하는 [ICLRDataTarget](iclrdatatarget-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="00710-103">A subclass of [ICLRDataTarget](iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="00710-104">메서드</span><span class="sxs-lookup"><span data-stu-id="00710-104">Methods</span></span>  
  
|<span data-ttu-id="00710-105">메서드</span><span class="sxs-lookup"><span data-stu-id="00710-105">Method</span></span>|<span data-ttu-id="00710-106">Description</span><span class="sxs-lookup"><span data-stu-id="00710-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="00710-107">AllocVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="00710-107">AllocVirtual Method</span></span>](iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="00710-108">대상 프로세스의 주소 공간에 메모리를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="00710-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="00710-109">FreeVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="00710-109">FreeVirtual Method</span></span>](iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="00710-110">대상 프로세스의 주소 공간에 이전에 할당 된 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="00710-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00710-111">설명</span><span class="sxs-lookup"><span data-stu-id="00710-111">Remarks</span></span>  
 <span data-ttu-id="00710-112">API 클라이언트(즉, 디버거)에서는 이 인터페이스를 특정 대상 프로세스에 적절하게 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00710-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="00710-113">예를 들어 활성 프로세스의 구현은 메모리 덤프의 구현과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="00710-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="00710-114">대상에서 메모리 영역의 수정을 지원하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00710-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00710-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="00710-115">Requirements</span></span>  
 <span data-ttu-id="00710-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00710-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00710-117">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="00710-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="00710-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00710-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00710-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00710-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00710-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00710-120">See also</span></span>

- [<span data-ttu-id="00710-121">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00710-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
- [<span data-ttu-id="00710-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00710-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
