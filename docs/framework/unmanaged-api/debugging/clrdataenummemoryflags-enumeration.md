---
description: '자세한 정보: CLRDataEnumMemoryFlags 열거형'
title: CLRDataEnumMemoryFlags 열거형
ms.date: 03/30/2017
api_name:
- CLRDataEnumMemoryFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLRDataEnumMemoryFlags
helpviewer_keywords:
- CLRDataEnumMemoryFlags enumeration [.NET Framework debugging]
ms.assetid: e249f9fc-e24a-4506-903c-92781f6eab7c
topic_type:
- apiref
ms.openlocfilehash: 3522649c59177de8295416ce260c374df605efb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662249"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="00090-103">CLRDataEnumMemoryFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="00090-103">CLRDataEnumMemoryFlags Enumeration</span></span>

<span data-ttu-id="00090-104">[ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) 메서드에 대 한 호출에 포함 되어야 하는 메모리 영역을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="00090-104">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00090-105">구문</span><span class="sxs-lookup"><span data-stu-id="00090-105">Syntax</span></span>  
  
```cpp  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="00090-106">구성원</span><span class="sxs-lookup"><span data-stu-id="00090-106">Members</span></span>  
  
|<span data-ttu-id="00090-107">멤버</span><span class="sxs-lookup"><span data-stu-id="00090-107">Member</span></span>|<span data-ttu-id="00090-108">설명</span><span class="sxs-lookup"><span data-stu-id="00090-108">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="00090-109">미니 덤프, 즉 스파스 메모리 덤프입니다.</span><span class="sxs-lookup"><span data-stu-id="00090-109">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="00090-110">전체 힙 덤프입니다.</span><span class="sxs-lookup"><span data-stu-id="00090-110">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="00090-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="00090-111">Requirements</span></span>  

 <span data-ttu-id="00090-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00090-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00090-113">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="00090-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="00090-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00090-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00090-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00090-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00090-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00090-116">See also</span></span>

- [<span data-ttu-id="00090-117">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="00090-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
