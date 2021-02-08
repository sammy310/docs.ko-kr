---
description: '자세히 알아보기: ICLRDataEnumMemoryRegionsCallback 인터페이스'
title: ICLRDataEnumMemoryRegionsCallback 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords:
- ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type:
- apiref
ms.openlocfilehash: 863192844c4d4d8a35d1e73d38adea3a513bc944
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801373"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="b1119-103">ICLRDataEnumMemoryRegionsCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1119-103">ICLRDataEnumMemoryRegionsCallback Interface</span></span>

<span data-ttu-id="b1119-104">지정 된 메모리 영역을 열거 하려는 시도의 결과로 디버거에 보고 하는 [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) 에 대 한 콜백 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1119-104">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b1119-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b1119-105">Methods</span></span>  
  
|<span data-ttu-id="b1119-106">메서드</span><span class="sxs-lookup"><span data-stu-id="b1119-106">Method</span></span>|<span data-ttu-id="b1119-107">설명</span><span class="sxs-lookup"><span data-stu-id="b1119-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b1119-108">EnumMemoryRegion 메서드</span><span class="sxs-lookup"><span data-stu-id="b1119-108">EnumMemoryRegion Method</span></span>](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="b1119-109">`ICLRDataEnumMemoryRegions::EnumMemoryRegions`지정 된 메모리 영역을 열거 하려는 시도의 결과로 디버거에 보고 하기 위해에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1119-109">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b1119-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b1119-110">Requirements</span></span>  

 <span data-ttu-id="b1119-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b1119-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1119-112">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="b1119-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b1119-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1119-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1119-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1119-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1119-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1119-115">See also</span></span>

- [<span data-ttu-id="b1119-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1119-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
