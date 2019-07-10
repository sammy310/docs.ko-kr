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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92eff65078f05557f542c64c1be7d4f6eca43eb5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738474"
---
# <a name="iclrdatatarget2allocvirtual-method"></a><span data-ttu-id="1e1c7-102">ICLRDataTarget2::AllocVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="1e1c7-102">ICLRDataTarget2::AllocVirtual Method</span></span>
<span data-ttu-id="1e1c7-103">이 대상 프로세스의 주소 공간에 메모리를 할당 하는 공용 언어 런타임 (CLR) 데이터 액세스 서비스에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e1c7-103">Called by the common language runtime (CLR) data access services to allocate memory in the address space of this target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e1c7-104">구문</span><span class="sxs-lookup"><span data-stu-id="1e1c7-104">Syntax</span></span>  
  
```cpp  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e1c7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1e1c7-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="1e1c7-106">[in] `CLRDATA_ADDRESS` 할당할 메모리의 요청된 된 시작 주소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1e1c7-106">[in] A `CLRDATA_ADDRESS` value that specifies the requested starting address of the memory to be allocated.</span></span>  
  
 `size`  
 <span data-ttu-id="1e1c7-107">[in] 할당할 메모리의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="1e1c7-107">[in] The size, in bytes, of the memory to be allocated.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="1e1c7-108">[in] 메모리의 할당을 제어 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="1e1c7-108">[in] Flags that control the allocation of memory.</span></span> <span data-ttu-id="1e1c7-109">Win32 참조 `VirtualAlloc` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="1e1c7-109">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `protectFlags`  
 <span data-ttu-id="1e1c7-110">[in] 할당된 된 메모리에 대 한 보호 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1e1c7-110">[in] The protection attributes for the allocated memory.</span></span> <span data-ttu-id="1e1c7-111">Win32 참조 `VirtualAlloc` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="1e1c7-111">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `virt`  
 <span data-ttu-id="1e1c7-112">[out] 에 대 한 포인터를 `CLRDATA_ADDRESS` 할당된 된 메모리의 실제 시작 주소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1e1c7-112">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the actual starting address of the allocated memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e1c7-113">설명</span><span class="sxs-lookup"><span data-stu-id="1e1c7-113">Remarks</span></span>  
 <span data-ttu-id="1e1c7-114">합니다 `AllocVirtual` 메서드는 win32 논리 래퍼 역할도 `VirtualAlloc` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="1e1c7-114">The `AllocVirtual` method serves as a logical wrapper for the Win32 `VirtualAlloc` function.</span></span>  
  
 <span data-ttu-id="1e1c7-115">이 메서드는 디버깅 응용 프로그램의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="1e1c7-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e1c7-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1e1c7-116">Requirements</span></span>  
 <span data-ttu-id="1e1c7-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1e1c7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e1c7-118">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="1e1c7-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="1e1c7-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e1c7-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e1c7-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e1c7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e1c7-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="1e1c7-121">See also</span></span>

- [<span data-ttu-id="1e1c7-122">ICLRDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1e1c7-122">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="1e1c7-123">FreeVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="1e1c7-123">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)
