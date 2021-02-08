---
description: '자세히 알아보기: CorDebugRecordFormat 열거형'
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
ms.openlocfilehash: 856522497a8f858abdb39ac232fb3034d4d91dfc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801568"
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="9590e-103">CorDebugRecordFormat 열거형</span><span class="sxs-lookup"><span data-stu-id="9590e-103">CorDebugRecordFormat Enumeration</span></span>

<span data-ttu-id="9590e-104">네이티브 예외 디버그 이벤트에 대한 정보가 포함된 바이트 배열의 데이터 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9590e-104">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9590e-105">구문</span><span class="sxs-lookup"><span data-stu-id="9590e-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="9590e-106">구성원</span><span class="sxs-lookup"><span data-stu-id="9590e-106">Members</span></span>  
  
|<span data-ttu-id="9590e-107">멤버</span><span class="sxs-lookup"><span data-stu-id="9590e-107">Member</span></span>|<span data-ttu-id="9590e-108">설명</span><span class="sxs-lookup"><span data-stu-id="9590e-108">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="9590e-109">데이터가 32비트 Windows 예외 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="9590e-109">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="9590e-110">데이터가 64비트 Windows 예외 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="9590e-110">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9590e-111">설명</span><span class="sxs-lookup"><span data-stu-id="9590e-111">Remarks</span></span>  

 <span data-ttu-id="9590e-112">열거형의 멤버는 `CorDebugRecordFormat` 인수에서 바이트 배열의 형식을 나타내기 위해 [DecodeEvent](icordebugprocess6-decodeevent-method.md) 메서드에 전달 됩니다 `pRecord` .</span><span class="sxs-lookup"><span data-stu-id="9590e-112">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9590e-113">이 열거형은 .NET 네이티브 디버깅 시나리오에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9590e-113">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9590e-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9590e-114">Requirements</span></span>  

 <span data-ttu-id="9590e-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9590e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9590e-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9590e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9590e-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9590e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9590e-118">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9590e-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9590e-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9590e-119">See also</span></span>

- [<span data-ttu-id="9590e-120">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="9590e-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
