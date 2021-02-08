---
description: '자세히 알아보기: ICLRDataTarget2 인터페이스'
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
ms.openlocfilehash: 9ba6d11ea043d3b6ba85544b47e063f585854af8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794847"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="b0335-103">ICLRDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0335-103">ICLRDataTarget2 Interface</span></span>

<span data-ttu-id="b0335-104">데이터 액세스 서비스 계층에서 대상 프로세스의 가상 메모리 영역을 조작 하는 데 사용 하는 [ICLRDataTarget](iclrdatatarget-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b0335-104">A subclass of [ICLRDataTarget](iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b0335-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b0335-105">Methods</span></span>  
  
|<span data-ttu-id="b0335-106">메서드</span><span class="sxs-lookup"><span data-stu-id="b0335-106">Method</span></span>|<span data-ttu-id="b0335-107">설명</span><span class="sxs-lookup"><span data-stu-id="b0335-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b0335-108">AllocVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="b0335-108">AllocVirtual Method</span></span>](iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="b0335-109">대상 프로세스의 주소 공간에 메모리를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0335-109">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="b0335-110">FreeVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="b0335-110">FreeVirtual Method</span></span>](iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="b0335-111">대상 프로세스의 주소 공간에 이전에 할당 된 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0335-111">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0335-112">설명</span><span class="sxs-lookup"><span data-stu-id="b0335-112">Remarks</span></span>  

 <span data-ttu-id="b0335-113">API 클라이언트(즉, 디버거)에서는 이 인터페이스를 특정 대상 프로세스에 적절하게 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0335-113">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="b0335-114">예를 들어 활성 프로세스의 구현은 메모리 덤프의 구현과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b0335-114">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="b0335-115">대상에서 메모리 영역의 수정을 지원하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0335-115">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0335-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b0335-116">Requirements</span></span>  

 <span data-ttu-id="b0335-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0335-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0335-118">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="b0335-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b0335-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0335-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0335-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0335-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0335-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0335-121">See also</span></span>

- [<span data-ttu-id="b0335-122">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0335-122">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
- [<span data-ttu-id="b0335-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0335-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
