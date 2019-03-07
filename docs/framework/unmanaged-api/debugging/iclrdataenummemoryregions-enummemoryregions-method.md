---
title: ICLRDataEnumMemoryRegions::EnumMemoryRegions 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c9e3aa909c4eb674b166bfd14feb59e35df4cfd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488528"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="9dfd7-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions 메서드</span><span class="sxs-lookup"><span data-stu-id="9dfd7-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="9dfd7-103">메모리의 지정 된 영역을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="9dfd7-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dfd7-104">구문</span><span class="sxs-lookup"><span data-stu-id="9dfd7-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9dfd7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9dfd7-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="9dfd7-106">[in] 에 대 한 포인터를 [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) 결과의 디버거에 알리기 위해 열거 되 고 있는 각 메모리 영역에 대 한이 메서드에 의해 호출 되는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="9dfd7-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="9dfd7-107">메모리 영역의 열거형에는 콜백에 실패 했음을 의미 하는 경우에 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dfd7-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="9dfd7-108">[in] 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9dfd7-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="9dfd7-109">[in] 값을 [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) 열거할 메모리의 영역을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="9dfd7-109">[in] A value of the [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9dfd7-110">설명</span><span class="sxs-lookup"><span data-stu-id="9dfd7-110">Remarks</span></span>  
 <span data-ttu-id="9dfd7-111">이 메서드를 사용 하 여 지정 된 [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) 결과의 호출자에 게 알리지 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="9dfd7-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dfd7-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9dfd7-112">Requirements</span></span>  
 <span data-ttu-id="9dfd7-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9dfd7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dfd7-114">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="9dfd7-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="9dfd7-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9dfd7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9dfd7-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dfd7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dfd7-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="9dfd7-117">See also</span></span>
- [<span data-ttu-id="9dfd7-118">ICLRDataEnumMemoryRegions 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9dfd7-118">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)
