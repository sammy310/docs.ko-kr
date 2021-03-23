---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_EVENTPIPE_PROVIDER_CONFIG'
title: COR_PRF_EVENTPIPE_PROVIDER_CONFIG 열거형
ms.date: 03/19/2021
api_name:
- COR_PRF_EVENTPIPE_PROVIDER_CONFIG
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 2a7a5e720e9468b44e6504d24a3b9ad836e13693
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805846"
---
# <a name="cor_prf_eventpipe_provider_config-enumeration"></a><span data-ttu-id="6a0c0-103">COR_PRF_EVENTPIPE_PROVIDER_CONFIG 열거형</span><span class="sxs-lookup"><span data-stu-id="6a0c0-103">COR_PRF_EVENTPIPE_PROVIDER_CONFIG Enumeration</span></span>

<span data-ttu-id="6a0c0-104">EventPipe 공급자를 구성 하는 데 필요한 필드에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0c0-104">Describes the fields necessary to configure an EventPipe provider.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="6a0c0-105">구문</span><span class="sxs-lookup"><span data-stu-id="6a0c0-105">Syntax</span></span>  
  
```cpp  
typedef struct
{
    const WCHAR* providerName;
    UINT64       keywords;
    UINT32       loggingLevel;
    const WCHAR* filterData;
} COR_PRF_EVENTPIPE_PROVIDER_CONFIG;
```  
  
## <a name="members"></a><span data-ttu-id="6a0c0-106">멤버</span><span class="sxs-lookup"><span data-stu-id="6a0c0-106">Members</span></span>  
  
|<span data-ttu-id="6a0c0-107">멤버</span><span class="sxs-lookup"><span data-stu-id="6a0c0-107">Member</span></span>|<span data-ttu-id="6a0c0-108">설명</span><span class="sxs-lookup"><span data-stu-id="6a0c0-108">Description</span></span>|  
|------------|-----------------|  
|`providerName`|<span data-ttu-id="6a0c0-109">사용할 공급자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6a0c0-109">The name of the provider to enable.</span></span>|  
|`keywords`|<span data-ttu-id="6a0c0-110">공급자에서 사용할 수 있는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="6a0c0-110">The keywords to enable on the provider.</span></span>|  
|`loggingLevel`|<span data-ttu-id="6a0c0-111">공급자에서 사용할 수 있는 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="6a0c0-111">The level to enable on the provider.</span></span>|  
|`filterData`|<span data-ttu-id="6a0c0-112">공급자를 사용 하도록 설정할 때 사용할 filterdata를 포함 하는 와이드 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6a0c0-112">A wide character string containing the filterdata to use when enabling the provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a0c0-113">설명</span><span class="sxs-lookup"><span data-stu-id="6a0c0-113">Remarks</span></span>  

 <span data-ttu-id="6a0c0-114">`COR_PRF_EVENTPIPE_PROVIDER_CONFIG`이 구조는 [ICorProfilerInfo12:: EventPipeAddProviderToSession](icorprofilerinfo12-eventpipeaddprovidertosession-method.md) 메서드에서 세션에 추가 되는 공급자에 대 한 구성을 나타내는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a0c0-114">The `COR_PRF_EVENTPIPE_PROVIDER_CONFIG` structure is used by the [ICorProfilerInfo12::EventPipeAddProviderToSession](icorprofilerinfo12-eventpipeaddprovidertosession-method.md) method to indicate the configuration for the provider being added to the session.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="6a0c0-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a0c0-115">Requirements</span></span>  

<span data-ttu-id="6a0c0-116">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a0c0-116">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>
<span data-ttu-id="6a0c0-117">**헤더:** Corprof.idl, Corprof.idl **.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a0c0-117">**Header:** CorProf.idl, CorProf.h **.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6a0c0-118">참조</span><span class="sxs-lookup"><span data-stu-id="6a0c0-118">See also</span></span>

- [<span data-ttu-id="6a0c0-119">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="6a0c0-119">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="6a0c0-120">ICorProfilerInfo12::EventPipeAddProviderToSession</span><span class="sxs-lookup"><span data-stu-id="6a0c0-120">ICorProfilerInfo12::EventPipeAddProviderToSession</span></span>](icorprofilerinfo12-eventpipeaddprovidertosession-method.md)
