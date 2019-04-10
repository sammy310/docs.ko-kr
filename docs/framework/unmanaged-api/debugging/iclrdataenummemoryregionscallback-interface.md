---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dad66c8a55982762ede754a4b3cd747b7a91b87d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225432"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="88fbc-102">ICLRDataEnumMemoryRegionsCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88fbc-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="88fbc-103">에 대 한 콜백 메서드를 제공 [iclrdataenummemoryregions:: Enummemoryregions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) 메모리의 지정된 된 영역을 열거 하려고 하면 디버거를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="88fbc-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="88fbc-104">메서드</span><span class="sxs-lookup"><span data-stu-id="88fbc-104">Methods</span></span>  
  
|<span data-ttu-id="88fbc-105">메서드</span><span class="sxs-lookup"><span data-stu-id="88fbc-105">Method</span></span>|<span data-ttu-id="88fbc-106">설명</span><span class="sxs-lookup"><span data-stu-id="88fbc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="88fbc-107">EnumMemoryRegion 메서드</span><span class="sxs-lookup"><span data-stu-id="88fbc-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="88fbc-108">호출한 `ICLRDataEnumMemoryRegions::EnumMemoryRegions` 메모리의 지정된 된 영역을 열거 하려고 하면 디버거를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="88fbc-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="88fbc-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="88fbc-109">Requirements</span></span>  
 <span data-ttu-id="88fbc-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="88fbc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88fbc-111">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="88fbc-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="88fbc-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88fbc-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="88fbc-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="88fbc-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="88fbc-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="88fbc-114">See also</span></span>

- [<span data-ttu-id="88fbc-115">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88fbc-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
