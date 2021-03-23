---
description: '자세히 알아보기: ICorProfilerInfo11:: SetEnvironmentVariable 메서드'
title: 'ICorProfilerInfo11:: SetEnvironmentVariable 메서드'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo11.SetEnvironmentVariable
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 77dc3fc992dec037881573323822dc11481a56be
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805608"
---
# <a name="icorprofilerinfo11setenvironmentvariable-method"></a><span data-ttu-id="ff01a-103">ICorProfilerInfo11:: SetEnvironmentVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="ff01a-103">ICorProfilerInfo11::SetEnvironmentVariable Method</span></span>

<span data-ttu-id="ff01a-104">프로세스의 환경 변수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff01a-104">Sets an environment variable in the process.</span></span> <span data-ttu-id="ff01a-105">Windows가 아닌 플랫폼에서 런타임은 환경 변수의 내부 캐시를 유지 하 여 스레드 안전을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff01a-105">On non-Windows platforms the runtime keeps an internal cache of environment variables to ensure thread safety.</span></span> <span data-ttu-id="ff01a-106">즉, 프로파일러가 새 환경 변수를 호출 하는 경우 `setenv` 프로세스에서 실행 되는 관리 코드에 의해 선택 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff01a-106">This means that if the profiler calls `setenv` the new environment variable will not be picked up by managed code running in the process.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="ff01a-107">구문</span><span class="sxs-lookup"><span data-stu-id="ff01a-107">Syntax</span></span>  
  
```cpp  
    HRESULT SetEnvironmentVariable(
                [in, string] const WCHAR *szName,
                [in, string] const WCHAR *szValue);
```  
  
## <a name="parameters"></a><span data-ttu-id="ff01a-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ff01a-108">Parameters</span></span>

<span data-ttu-id="ff01a-109">`szName` 진행 설정할 환경 변수의 이름을 포함 하는 null로 끝나는 와이드 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ff01a-109">`szName` [in] A pointer to a null terminated wide character string containing the name of the environment variable to set.</span></span>

<span data-ttu-id="ff01a-110">`szValue` 진행 설정할 환경 변수의 값을 포함 하는 null로 끝나는 와이드 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ff01a-110">`szValue` [in] A pointer to a null terminated wide character string containing the value of the environment variable to set.</span></span>

## <a name="requirements"></a><span data-ttu-id="ff01a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff01a-111">Requirements</span></span>  

<span data-ttu-id="ff01a-112">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ff01a-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="ff01a-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff01a-113">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="ff01a-114">**.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-31-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff01a-114">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-31-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff01a-115">참조</span><span class="sxs-lookup"><span data-stu-id="ff01a-115">See also</span></span>

- [<span data-ttu-id="ff01a-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff01a-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="ff01a-117">ICorProfilerInfo11 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff01a-117">ICorProfilerInfo11 Interface</span></span>](icorprofilerinfo11-interface.md)
