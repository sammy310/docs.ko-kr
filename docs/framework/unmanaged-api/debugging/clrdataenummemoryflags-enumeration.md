---
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
ms.openlocfilehash: 769e63ac6e23ae0264b79a1cd8d6e3cc1ac5a744
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132408"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="18e92-102">CLRDataEnumMemoryFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="18e92-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="18e92-103">[ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) 메서드에 대 한 호출에 포함 되어야 하는 메모리 영역을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="18e92-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18e92-104">구문</span><span class="sxs-lookup"><span data-stu-id="18e92-104">Syntax</span></span>  
  
```cpp  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="18e92-105">멤버</span><span class="sxs-lookup"><span data-stu-id="18e92-105">Members</span></span>  
  
|<span data-ttu-id="18e92-106">멤버</span><span class="sxs-lookup"><span data-stu-id="18e92-106">Member</span></span>|<span data-ttu-id="18e92-107">설명</span><span class="sxs-lookup"><span data-stu-id="18e92-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="18e92-108">미니 덤프, 즉 스파스 메모리 덤프입니다.</span><span class="sxs-lookup"><span data-stu-id="18e92-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="18e92-109">전체 힙 덤프입니다.</span><span class="sxs-lookup"><span data-stu-id="18e92-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="18e92-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18e92-110">Requirements</span></span>  
 <span data-ttu-id="18e92-111">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18e92-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18e92-112">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="18e92-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="18e92-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18e92-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18e92-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18e92-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18e92-115">참조</span><span class="sxs-lookup"><span data-stu-id="18e92-115">See also</span></span>

- [<span data-ttu-id="18e92-116">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="18e92-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
