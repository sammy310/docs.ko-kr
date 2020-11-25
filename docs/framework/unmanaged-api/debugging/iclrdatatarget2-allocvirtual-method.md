---
title: ICLRDataTarget2::AllocVirtual 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.AllocVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::AllocVirtual
helpviewer_keywords:
- ICLRDataTarget2::AllocVirtual method [.NET Framework debugging]
- AllocVirtual method [.NET Framework debugging]
ms.assetid: e3226230-964b-47fb-9f53-d6fdbeda1e9e
topic_type:
- apiref
ms.openlocfilehash: 6d3985919ea7e766db7d07e4ed81484851156ca5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723670"
---
# <a name="iclrdatatarget2allocvirtual-method"></a><span data-ttu-id="a391d-102">ICLRDataTarget2::AllocVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="a391d-102">ICLRDataTarget2::AllocVirtual Method</span></span>

<span data-ttu-id="a391d-103">이 대상 프로세스의 주소 공간에서 메모리를 할당 하기 위해 CLR (공용 언어 런타임) 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a391d-103">Called by the common language runtime (CLR) data access services to allocate memory in the address space of this target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a391d-104">구문</span><span class="sxs-lookup"><span data-stu-id="a391d-104">Syntax</span></span>  
  
```cpp  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a391d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a391d-105">Parameters</span></span>  

 `addr`  
 <span data-ttu-id="a391d-106">진행 `CLRDATA_ADDRESS` 할당할 메모리의 요청 된 시작 주소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a391d-106">[in] A `CLRDATA_ADDRESS` value that specifies the requested starting address of the memory to be allocated.</span></span>  
  
 `size`  
 <span data-ttu-id="a391d-107">진행 할당할 메모리의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="a391d-107">[in] The size, in bytes, of the memory to be allocated.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="a391d-108">진행 메모리 할당을 제어 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="a391d-108">[in] Flags that control the allocation of memory.</span></span> <span data-ttu-id="a391d-109">Win32 함수를 참조 하세요 `VirtualAlloc` .</span><span class="sxs-lookup"><span data-stu-id="a391d-109">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `protectFlags`  
 <span data-ttu-id="a391d-110">진행 할당 된 메모리에 대 한 보호 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a391d-110">[in] The protection attributes for the allocated memory.</span></span> <span data-ttu-id="a391d-111">Win32 함수를 참조 하세요 `VirtualAlloc` .</span><span class="sxs-lookup"><span data-stu-id="a391d-111">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `virt`  
 <span data-ttu-id="a391d-112">제한이 `CLRDATA_ADDRESS` 할당 된 메모리의 실제 시작 주소를 지정 하는 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a391d-112">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the actual starting address of the allocated memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a391d-113">설명</span><span class="sxs-lookup"><span data-stu-id="a391d-113">Remarks</span></span>  

 <span data-ttu-id="a391d-114">`AllocVirtual`메서드는 Win32 함수에 대 한 논리 래퍼로 사용 `VirtualAlloc` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a391d-114">The `AllocVirtual` method serves as a logical wrapper for the Win32 `VirtualAlloc` function.</span></span>  
  
 <span data-ttu-id="a391d-115">이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a391d-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a391d-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a391d-116">Requirements</span></span>  

 <span data-ttu-id="a391d-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a391d-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a391d-118">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="a391d-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="a391d-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a391d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a391d-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a391d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a391d-121">참조</span><span class="sxs-lookup"><span data-stu-id="a391d-121">See also</span></span>

- [<span data-ttu-id="a391d-122">ICLRDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a391d-122">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="a391d-123">FreeVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="a391d-123">FreeVirtual Method</span></span>](iclrdatatarget2-freevirtual-method.md)
