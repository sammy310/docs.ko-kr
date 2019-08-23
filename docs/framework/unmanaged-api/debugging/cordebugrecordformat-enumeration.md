---
title: CorDebugRecordFormat 열거형
ms.date: 03/30/2017
api_name:
- CorDebugRecordFormat
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6ed7d25593f9dd5d5d01f8c06024dcf8acfcfea
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916482"
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="c5e90-102">CorDebugRecordFormat 열거형</span><span class="sxs-lookup"><span data-stu-id="c5e90-102">CorDebugRecordFormat Enumeration</span></span>
<span data-ttu-id="c5e90-103">네이티브 예외 디버그 이벤트에 대한 정보가 포함된 바이트 배열의 데이터 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c5e90-103">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5e90-104">구문</span><span class="sxs-lookup"><span data-stu-id="c5e90-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="c5e90-105">멤버</span><span class="sxs-lookup"><span data-stu-id="c5e90-105">Members</span></span>  
  
|<span data-ttu-id="c5e90-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c5e90-106">Member</span></span>|<span data-ttu-id="c5e90-107">Description</span><span class="sxs-lookup"><span data-stu-id="c5e90-107">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="c5e90-108">데이터가 32비트 Windows 예외 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c5e90-108">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="c5e90-109">데이터가 64비트 Windows 예외 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c5e90-109">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5e90-110">설명</span><span class="sxs-lookup"><span data-stu-id="c5e90-110">Remarks</span></span>  
 <span data-ttu-id="c5e90-111">`CorDebugRecordFormat` 열거형의 멤버는 `pRecord` 인수에서 바이트 배열의 형식을 나타내기 위해 [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) 메서드에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5e90-111">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c5e90-112">이 열거형은 .NET 네이티브 디버깅 시나리오에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5e90-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5e90-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c5e90-113">Requirements</span></span>  
 <span data-ttu-id="c5e90-114">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c5e90-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5e90-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5e90-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5e90-116">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5e90-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5e90-117">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5e90-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5e90-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="c5e90-118">See also</span></span>

- [<span data-ttu-id="c5e90-119">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="c5e90-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
