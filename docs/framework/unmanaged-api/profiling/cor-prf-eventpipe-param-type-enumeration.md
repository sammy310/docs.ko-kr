---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_EVENTPIPE_PARAM_TYPE'
title: COR_PRF_EVENTPIPE_PARAM_TYPE 열거형
ms.date: 03/19/2021
api_name:
- COR_PRF_EVENTPIPE_PARAM_TYPE
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 29aed86e4a991598d038a60ae086e77e25df24bb
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805781"
---
# <a name="cor_prf_eventpipe_param_type-enumeration"></a><span data-ttu-id="56705-103">COR_PRF_EVENTPIPE_PARAM_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="56705-103">COR_PRF_EVENTPIPE_PARAM_TYPE Enumeration</span></span>

<span data-ttu-id="56705-104">EventPipe 이벤트의 매개 변수 형식을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="56705-104">Describes the type of a parameter for an EventPipe event.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="56705-105">구문</span><span class="sxs-lookup"><span data-stu-id="56705-105">Syntax</span></span>  
  
```cpp  
typedef enum
{
    COR_PRF_EVENTPIPE_OBJECT = 1,
    COR_PRF_EVENTPIPE_BOOLEAN = 3,
    COR_PRF_EVENTPIPE_CHAR = 4,
    COR_PRF_EVENTPIPE_SBYTE = 5,
    COR_PRF_EVENTPIPE_BYTE = 6,
    COR_PRF_EVENTPIPE_INT16 = 7,
    COR_PRF_EVENTPIPE_UINT16 = 8,
    COR_PRF_EVENTPIPE_INT32 = 9,
    COR_PRF_EVENTPIPE_UINT32 = 10,
    COR_PRF_EVENTPIPE_INT64 = 11,
    COR_PRF_EVENTPIPE_UINT64 = 12,
    COR_PRF_EVENTPIPE_SINGLE = 13,
    COR_PRF_EVENTPIPE_DOUBLE = 14,
    COR_PRF_EVENTPIPE_DECIMAL = 15,
    COR_PRF_EVENTPIPE_DATETIME = 16,
    COR_PRF_EVENTPIPE_GUID = 17,
    COR_PRF_EVENTPIPE_STRING = 18,
    COR_PRF_EVENTPIPE_ARRAY = 19,
} COR_PRF_EVENTPIPE_PARAM_TYPE;
```  
  
## <a name="members"></a><span data-ttu-id="56705-106">멤버</span><span class="sxs-lookup"><span data-stu-id="56705-106">Members</span></span>  
  
|<span data-ttu-id="56705-107">멤버</span><span class="sxs-lookup"><span data-stu-id="56705-107">Member</span></span>|<span data-ttu-id="56705-108">설명</span><span class="sxs-lookup"><span data-stu-id="56705-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_EVENTPIPE_OBJECT`|<span data-ttu-id="56705-109">매개 변수 형식은 자체 설명 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="56705-109">The parameter type is a self describing object.</span></span>|
|`COR_PRF_EVENTPIPE_BOOLEAN`|<span data-ttu-id="56705-110">매개 변수 형식은 부울입니다.</span><span class="sxs-lookup"><span data-stu-id="56705-110">The parameter type is a boolean.</span></span>|
|`COR_PRF_EVENTPIPE_CHAR`|<span data-ttu-id="56705-111">매개 변수 형식은 16 비트 와이드 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="56705-111">The parameter type is a 16 bit wide character.</span></span>|
|`COR_PRF_EVENTPIPE_SBYTE`|<span data-ttu-id="56705-112">매개 변수 형식은 부호 있는 8 비트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="56705-112">The parameter type is a signed 8 bit integer.</span></span>|
|`COR_PRF_EVENTPIPE_BYTE`|<span data-ttu-id="56705-113">매개 변수 형식이 부호 없는 8 비트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="56705-113">The parameter type is an unsigned 8 bit integer.</span></span>|
|`COR_PRF_EVENTPIPE_INT16`|<span data-ttu-id="56705-114">매개 변수 형식은 부호 있는 16 비트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="56705-114">The parameter type is a signed 16 bit integer.</span></span>|
|`COR_PRF_EVENTPIPE_UINT16`|<span data-ttu-id="56705-115">매개 변수 형식이 부호 없는 16 비트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="56705-115">The parameter type is an unsigned 16 bit integer.</span></span>|
|`COR_PRF_EVENTPIPE_INT32`|<span data-ttu-id="56705-116">매개 변수 형식은 부호 있는 32 비트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="56705-116">The parameter type is a signed 32 bit integer.</span></span>|
|`COR_PRF_EVENTPIPE_UINT32`|<span data-ttu-id="56705-117">매개 변수 형식이 부호 없는 32 비트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="56705-117">The parameter type is an unsigned 32 bit integer.</span></span>|
|`COR_PRF_EVENTPIPE_INT64`|<span data-ttu-id="56705-118">매개 변수 형식은 부호 있는 64 비트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="56705-118">The parameter type is a signed 64 bit integer.</span></span>|
|`COR_PRF_EVENTPIPE_UINT64`|<span data-ttu-id="56705-119">매개 변수 형식이 부호 없는 64 비트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="56705-119">The parameter type is an unsigned 64 bit integer.</span></span>|
|`COR_PRF_EVENTPIPE_SINGLE`|<span data-ttu-id="56705-120">매개 변수 형식은 32 비트 부동 소수점 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="56705-120">The parameter type is a 32 bit floating point number.</span></span>|
|`COR_PRF_EVENTPIPE_DOUBLE`|<span data-ttu-id="56705-121">매개 변수 형식은 64 비트 부동 소수점 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="56705-121">The parameter type is a 64 bit floating point number.</span></span>|
|`COR_PRF_EVENTPIPE_DECIMAL`|<span data-ttu-id="56705-122">매개 변수 형식은 128 비트 부동 소수점 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="56705-122">The parameter type is a 128 bit floating point number.</span></span>|
|`COR_PRF_EVENTPIPE_DATETIME`|<span data-ttu-id="56705-123">매개 변수 형식은 직렬화 된 DataTime 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="56705-123">The parameter type is a serialized DataTime structure.</span></span>|
|`COR_PRF_EVENTPIPE_GUID`|<span data-ttu-id="56705-124">매개 변수 유형은 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="56705-124">The parameter type is a GUID.</span></span>|
|`COR_PRF_EVENTPIPE_STRING`|<span data-ttu-id="56705-125">매개 변수 형식은 16 비트 null로 끝나는 와이드 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="56705-125">The parameter type is a 16 bit null terminated wide character string.</span></span>|
|`COR_PRF_EVENTPIPE_ARRAY`|<span data-ttu-id="56705-126">매개 변수 형식은 위의 형식 중 하나의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="56705-126">The parameter type is an array of one of the preceding types.</span></span>|
  
## <a name="remarks"></a><span data-ttu-id="56705-127">설명</span><span class="sxs-lookup"><span data-stu-id="56705-127">Remarks</span></span>  

 <span data-ttu-id="56705-128">`COR_PRF_EVENTPIPE_PARAM_TYPE`열거형은 [COR_PRF_EVENTPIPE_PARAM_DESC](cor-prf-eventpipe-param-desc-structure.md) 구조에서 매개 변수의 형식을 나타내는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56705-128">The `COR_PRF_EVENTPIPE_PARAM_TYPE` enumeration is used by the [COR_PRF_EVENTPIPE_PARAM_DESC](cor-prf-eventpipe-param-desc-structure.md) structure to indicate the type of the parameter.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="56705-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="56705-129">Requirements</span></span>  

<span data-ttu-id="56705-130">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="56705-130">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>
<span data-ttu-id="56705-131">**헤더:** Corprof.idl, Corprof.idl **.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56705-131">**Header:** CorProf.idl, CorProf.h **.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="56705-132">참조</span><span class="sxs-lookup"><span data-stu-id="56705-132">See also</span></span>

- [<span data-ttu-id="56705-133">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="56705-133">Profiling Enumerations</span></span>](profiling-enumerations.md)
