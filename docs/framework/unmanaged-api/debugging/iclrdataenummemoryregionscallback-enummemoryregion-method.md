---
title: ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85b1c5455cb2008a352461d6b506e43fcef48d17
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130925"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="2be75-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion 메서드</span><span class="sxs-lookup"><span data-stu-id="2be75-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="2be75-103">호출한 [iclrdataenummemoryregions:: Enummemoryregions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) 메모리의 지정된 된 영역을 열거 하려고 하면 디버거를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2be75-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2be75-104">구문</span><span class="sxs-lookup"><span data-stu-id="2be75-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2be75-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2be75-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="2be75-106">[in] 시작 주소를 열거할 수 있는 메모리 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="2be75-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="2be75-107">[in] 메모리 영역의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2be75-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2be75-108">설명</span><span class="sxs-lookup"><span data-stu-id="2be75-108">Remarks</span></span>  
 <span data-ttu-id="2be75-109">`ICLRDataEnumMemoryRegions::EnumMemoryRegions` 메서드 열거는 메모리 영역을 만들려고 할 때마다이 콜백 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2be75-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="2be75-110">열거형에는이 메서드는 실패를 나타내는 HRESULT를 반환 하는 경우에 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2be75-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="2be75-111">이 콜백에 의해 보고 되는 지역 중복 되거나 겹치는 영역 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2be75-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2be75-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2be75-112">Requirements</span></span>  
 <span data-ttu-id="2be75-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2be75-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2be75-114">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="2be75-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="2be75-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2be75-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2be75-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2be75-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2be75-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="2be75-117">See also</span></span>

- [<span data-ttu-id="2be75-118">ICLRDataEnumMemoryRegionsCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2be75-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)
