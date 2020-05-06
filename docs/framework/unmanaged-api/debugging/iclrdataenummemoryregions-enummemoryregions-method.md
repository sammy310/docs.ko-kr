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
ms.openlocfilehash: e6cdc924df126e56d2e7c8c9cb8762ee88712fcc
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860695"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="5ba70-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions 메서드</span><span class="sxs-lookup"><span data-stu-id="5ba70-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="5ba70-103">지정 된 메모리 영역을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ba70-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ba70-104">구문</span><span class="sxs-lookup"><span data-stu-id="5ba70-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ba70-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5ba70-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="5ba70-106">진행 결과를 디버거에 알리기 위해 열거 되는 각 메모리 영역에 대해이 메서드에서 호출 하는 [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5ba70-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="5ba70-107">콜백이 실패를 나타내는 경우에도 메모리 영역의 열거를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ba70-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="5ba70-108">진행 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ba70-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="5ba70-109">진행 열거할 메모리 영역을 지정 하는 [Clrdataenummemoryflags](clrdataenummemoryflags-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5ba70-109">[in] A value of the [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ba70-110">설명</span><span class="sxs-lookup"><span data-stu-id="5ba70-110">Remarks</span></span>  
 <span data-ttu-id="5ba70-111">이 메서드는 지정 된 [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) 인스턴스를 사용 하 여 호출자에 게 결과를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5ba70-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ba70-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ba70-112">Requirements</span></span>  
 <span data-ttu-id="5ba70-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ba70-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ba70-114">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="5ba70-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5ba70-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ba70-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ba70-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ba70-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ba70-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ba70-117">See also</span></span>

- [<span data-ttu-id="5ba70-118">ICLRDataEnumMemoryRegions 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ba70-118">ICLRDataEnumMemoryRegions Interface</span></span>](iclrdataenummemoryregions-interface.md)
