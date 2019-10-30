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
ms.openlocfilehash: 693ec07176f80711709cd9b85c6886bea8be74b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122961"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="c4cad-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions 메서드</span><span class="sxs-lookup"><span data-stu-id="c4cad-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="c4cad-103">지정 된 메모리 영역을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4cad-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4cad-104">구문</span><span class="sxs-lookup"><span data-stu-id="c4cad-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4cad-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c4cad-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="c4cad-106">진행 결과를 디버거에 알리기 위해 열거 되는 각 메모리 영역에 대해이 메서드에서 호출 하는 [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c4cad-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="c4cad-107">콜백이 실패를 나타내는 경우에도 메모리 영역의 열거를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4cad-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="c4cad-108">진행 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4cad-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="c4cad-109">진행 열거할 메모리 영역을 지정 하는 [Clrdataenummemoryflags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c4cad-109">[in] A value of the [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4cad-110">주의</span><span class="sxs-lookup"><span data-stu-id="c4cad-110">Remarks</span></span>  
 <span data-ttu-id="c4cad-111">이 메서드는 지정 된 [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) 인스턴스를 사용 하 여 호출자에 게 결과를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c4cad-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4cad-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c4cad-112">Requirements</span></span>  
 <span data-ttu-id="c4cad-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c4cad-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4cad-114">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="c4cad-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c4cad-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4cad-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4cad-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4cad-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4cad-117">참조</span><span class="sxs-lookup"><span data-stu-id="c4cad-117">See also</span></span>

- [<span data-ttu-id="c4cad-118">ICLRDataEnumMemoryRegions 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c4cad-118">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)
