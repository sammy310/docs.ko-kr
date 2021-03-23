---
description: '자세히 알아보기: ICorProfilerInfo11:: GetEnvironmentVariable 메서드'
title: 'ICorProfilerInfo11:: GetEnvironmentVariable 메서드'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo11.GetEnvironmentVariable
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 635c5fb67b880c39f15fbc194a51a706d9ef7fe4
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805833"
---
# <a name="icorprofilerinfo11getenvironmentvariable-method"></a><span data-ttu-id="95497-103">ICorProfilerInfo11:: GetEnvironmentVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="95497-103">ICorProfilerInfo11::GetEnvironmentVariable Method</span></span>

<span data-ttu-id="95497-104">프로세스에서 환경 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="95497-104">Gets an environment variable from the process.</span></span> <span data-ttu-id="95497-105">Windows가 아닌 플랫폼에서 런타임은 환경 변수의 내부 캐시를 유지 하 여 스레드 안전을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="95497-105">On non-Windows platforms the runtime keeps an internal cache of environment variables to ensure thread safety.</span></span> <span data-ttu-id="95497-106">즉,을 호출 `getenv` 하면 시작 후 프로세스에서 실행 되는 관리 코드에 의해 설정 된 새 환경 변수 또는 업데이트 된 환경 변수는 읽지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95497-106">This means that calling `getenv` will not read any new or updated environment variables set by managed code running in the process after startup.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="95497-107">구문</span><span class="sxs-lookup"><span data-stu-id="95497-107">Syntax</span></span>  
  
```cpp  
    HRESULT GetEnvironmentVariable(
                [in, string] const WCHAR *szName,
                [in]         ULONG cchValue,
                [out]        ULONG *pcchValue,
                [out, annotation("_Out_writes_to_(cchValue, *pcchValue)")]
                             WCHAR szValue[]);
```  
  
## <a name="parameters"></a><span data-ttu-id="95497-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="95497-108">Parameters</span></span>

<span data-ttu-id="95497-109">`szName` 진행 가져올 환경 변수의 이름을 포함 하는 null로 끝나는 와이드 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="95497-109">`szName` [in] A pointer to a null terminated wide character string containing the name of the environment variable to get.</span></span>

<span data-ttu-id="95497-110">`cchValue` 진행 의 길이 (문자) `szValue` 입니다.</span><span class="sxs-lookup"><span data-stu-id="95497-110">`cchValue` [in] The length, in characters, of `szValue`.</span></span>

<span data-ttu-id="95497-111">`pcchValue` 제한이 의 총 문자 길이에 대 한 포인터 `szValue` 입니다.</span><span class="sxs-lookup"><span data-stu-id="95497-111">`pcchValue` [out] A pointer to the total character length of `szValue`.</span></span>

<span data-ttu-id="95497-112">`szValue` 제한이 호출자가 와이드 문자 버퍼를 제공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="95497-112">`szValue` [out] A caller provided wide character buffer.</span></span> <span data-ttu-id="95497-113">함수가 반환 될 때 버퍼에는 환경 변수 값이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95497-113">When the function returns the buffer will contain the value of the environment variable.</span></span>

## <a name="requirements"></a><span data-ttu-id="95497-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="95497-114">Requirements</span></span>  

<span data-ttu-id="95497-115">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="95497-115">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="95497-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="95497-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="95497-117">**.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-31-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95497-117">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-31-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95497-118">참조</span><span class="sxs-lookup"><span data-stu-id="95497-118">See also</span></span>

- [<span data-ttu-id="95497-119">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="95497-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="95497-120">ICorProfilerInfo11 인터페이스</span><span class="sxs-lookup"><span data-stu-id="95497-120">ICorProfilerInfo11 Interface</span></span>](icorprofilerinfo11-interface.md)
