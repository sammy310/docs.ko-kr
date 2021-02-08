---
description: '자세히 알아보기: ICLRDataEnumMemoryRegionsCallback:: EnumMemoryRegion 메서드'
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
ms.openlocfilehash: 733911f71898ea7019a0b8d854fb1c1bf61a2474
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801399"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="a4593-103">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion 메서드</span><span class="sxs-lookup"><span data-stu-id="a4593-103">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>

<span data-ttu-id="a4593-104">지정 된 메모리 영역을 열거 하려는 시도의 결과로 디버거에 보고 하기 위해 [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) 에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4593-104">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4593-105">구문</span><span class="sxs-lookup"><span data-stu-id="a4593-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4593-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4593-106">Parameters</span></span>  

 `address`  
 <span data-ttu-id="a4593-107">진행 열거할 메모리 영역의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="a4593-107">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="a4593-108">진행 메모리 영역의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="a4593-108">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4593-109">설명</span><span class="sxs-lookup"><span data-stu-id="a4593-109">Remarks</span></span>  

 <span data-ttu-id="a4593-110">`ICLRDataEnumMemoryRegions::EnumMemoryRegions`메서드는 각 메모리 영역을 열거 하려고 시도한 후이 콜백 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4593-110">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="a4593-111">열거형은이 메서드가 실패를 나타내는 HRESULT를 반환 하는 경우에도 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4593-111">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="a4593-112">이 콜백에서 보고 한 지역은 중복 되거나 중복 된 지역이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4593-112">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4593-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4593-113">Requirements</span></span>  

 <span data-ttu-id="a4593-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4593-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4593-115">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="a4593-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="a4593-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4593-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4593-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4593-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4593-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4593-118">See also</span></span>

- [<span data-ttu-id="a4593-119">ICLRDataEnumMemoryRegionsCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4593-119">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](iclrdataenummemoryregionscallback-interface.md)
