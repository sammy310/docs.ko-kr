---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_EVENTPIPE_PARAM_DESC'
title: COR_PRF_EVENTPIPE_PARAM_DESC 열거형
ms.date: 03/19/2021
api_name:
- COR_PRF_EVENTPIPE_PARAM_DESC
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: b23897580092cc9f3f887a21e86f7111fecd9f19
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805794"
---
# <a name="cor_prf_eventpipe_param_desc-enumeration"></a><span data-ttu-id="474af-103">COR_PRF_EVENTPIPE_PARAM_DESC 열거형</span><span class="sxs-lookup"><span data-stu-id="474af-103">COR_PRF_EVENTPIPE_PARAM_DESC Enumeration</span></span>

<span data-ttu-id="474af-104">EventPipe 이벤트의 매개 변수 이름 및 유형을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="474af-104">Describes the parameter name and type for an EventPipe event.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="474af-105">구문</span><span class="sxs-lookup"><span data-stu-id="474af-105">Syntax</span></span>  
  
```cpp  
typedef struct
{
    UINT32       type;
    UINT32       elementType;
    const WCHAR *name;
} COR_PRF_EVENTPIPE_PARAM_DESC;
```  
  
## <a name="members"></a><span data-ttu-id="474af-106">멤버</span><span class="sxs-lookup"><span data-stu-id="474af-106">Members</span></span>  
  
|<span data-ttu-id="474af-107">멤버</span><span class="sxs-lookup"><span data-stu-id="474af-107">Member</span></span>|<span data-ttu-id="474af-108">설명</span><span class="sxs-lookup"><span data-stu-id="474af-108">Description</span></span>|  
|------------|-----------------|  
|`type`|<span data-ttu-id="474af-109">매개 변수의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="474af-109">The type of the parameter.</span></span>|  
|`elementType`|<span data-ttu-id="474af-110">이 매개 변수가 배열 형식인 경우 요소 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="474af-110">The element type if this parameter is an array type.</span></span>|  
|`name`|<span data-ttu-id="474af-111">매개 변수의 이름을 포함 하는 와이드 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="474af-111">A wide character string containing the name of the parameter.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="474af-112">설명</span><span class="sxs-lookup"><span data-stu-id="474af-112">Remarks</span></span>  

 <span data-ttu-id="474af-113">`COR_PRF_EVENTPIPE_PARAM_DESC`구조체는 [ICorProfilerInfo12:: EventPipeDefineEvent](icorprofilerinfo12-eventpipedefineevent-method.md) 메서드에서 정의 되는 이벤트의 매개 변수 형식을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="474af-113">The `COR_PRF_EVENTPIPE_PARAM_DESC` structure is used by the [ICorProfilerInfo12::EventPipeDefineEvent](icorprofilerinfo12-eventpipedefineevent-method.md) method to define the parameter types of the event being defined.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="474af-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="474af-114">Requirements</span></span>  

<span data-ttu-id="474af-115">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="474af-115">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>
<span data-ttu-id="474af-116">**헤더:** Corprof.idl, Corprof.idl **.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="474af-116">**Header:** CorProf.idl, CorProf.h **.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="474af-117">참조</span><span class="sxs-lookup"><span data-stu-id="474af-117">See also</span></span>

- [<span data-ttu-id="474af-118">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="474af-118">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="474af-119">ICorProfilerInfo12::EventPipeDefineEvent</span><span class="sxs-lookup"><span data-stu-id="474af-119">ICorProfilerInfo12::EventPipeDefineEvent</span></span>](icorprofilerinfo12-eventpipedefineevent-method.md)
