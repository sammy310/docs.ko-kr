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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80ea3afef4aee51760e3a2ce6a2b895bca4a6ec5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224069"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="53214-102">CLRDataEnumMemoryFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="53214-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="53214-103">메모리 영역에 대 한 호출을 나타내는 합니다 [iclrdataenummemoryregions:: Enummemoryregions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) 메서드를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53214-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53214-104">구문</span><span class="sxs-lookup"><span data-stu-id="53214-104">Syntax</span></span>  
  
```  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="53214-105">멤버</span><span class="sxs-lookup"><span data-stu-id="53214-105">Members</span></span>  
  
|<span data-ttu-id="53214-106">멤버</span><span class="sxs-lookup"><span data-stu-id="53214-106">Member</span></span>|<span data-ttu-id="53214-107">설명</span><span class="sxs-lookup"><span data-stu-id="53214-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="53214-108">미니 덤프, 즉 스파스 메모리 덤프 합니다.</span><span class="sxs-lookup"><span data-stu-id="53214-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="53214-109">전체 힙 덤프 합니다.</span><span class="sxs-lookup"><span data-stu-id="53214-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="53214-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="53214-110">Requirements</span></span>  
 <span data-ttu-id="53214-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="53214-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53214-112">**헤더:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="53214-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="53214-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53214-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="53214-114">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="53214-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="53214-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="53214-115">See also</span></span>

- [<span data-ttu-id="53214-116">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="53214-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
