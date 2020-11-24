---
title: ICorProfilerInfo::GetAppDomainInfo 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetAppDomainInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetAppDomainInfo
helpviewer_keywords:
- ICorProfilerInfo::GetAppDomainInfo method [.NET Framework profiling]
- GetAppDomainInfo method [.NET Framework profiling]
ms.assetid: a6bf5a04-e03e-44f0-917a-96f6a6d3cc96
topic_type:
- apiref
ms.openlocfilehash: 62055a98197f5f8bd4cfc02e99891b83ef6341e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680302"
---
# <a name="icorprofilerinfogetappdomaininfo-method"></a><span data-ttu-id="8ea77-102">ICorProfilerInfo::GetAppDomainInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="8ea77-102">ICorProfilerInfo::GetAppDomainInfo Method</span></span>

<span data-ttu-id="8ea77-103">애플리케이션 도메인 ID를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea77-103">Accepts an application domain ID.</span></span> <span data-ttu-id="8ea77-104">애플리케이션 도메인 이름 및 해당 이름을 포함하는 프로세스 ID를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea77-104">Returns an application domain name and the ID of the process that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ea77-105">구문</span><span class="sxs-lookup"><span data-stu-id="8ea77-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomainInfo(  
    [in]  AppDomainID appDomainId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] ProcessID   *pProcessId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ea77-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8ea77-106">Parameters</span></span>  

 `appDomainId`  
 <span data-ttu-id="8ea77-107">[in] 애플리케이션 도메인의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea77-107">[in] The ID of the application domain.</span></span>  
  
 `cchName`  
 <span data-ttu-id="8ea77-108">[in] `szName` 반환 버퍼의 길이(문자)입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea77-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="8ea77-109">[out] 애플리케이션 도메인 이름의 총 문자 길이에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea77-109">[out] A pointer to the total character length of the application domain name.</span></span>  
  
 `szName`  
 <span data-ttu-id="8ea77-110">[out] 호출자가 제공한 와이드 문자 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea77-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="8ea77-111">메서드가 반환되면 `szName`에 전체 또는 일부 애플리케이션 도메인 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ea77-111">When the method returns, `szName` will contain the full or partial application domain name.</span></span>  
  
 `pProcessId`  
 <span data-ttu-id="8ea77-112">[out] 애플리케이션 도메인을 포함하는 프로세스 ID에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea77-112">[out] A pointer to the ID of the process that contains the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ea77-113">설명</span><span class="sxs-lookup"><span data-stu-id="8ea77-113">Remarks</span></span>  

 <span data-ttu-id="8ea77-114">이 메서드가 반환된 후 `szName` 버퍼가 모듈의 애플리케이션 도메인의 전체 이름을 포함하기에 충분히 큰지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea77-114">After this method returns, you must verify that the `szName` buffer was large enough to contain the full name of the application domain.</span></span> <span data-ttu-id="8ea77-115">이렇게 하려면 `pcchName`가 가리키는 값을 `cchName` 매개 변수의 값과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea77-115">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="8ea77-116">`pcchName`이 `cchName`보다 큰 값을 가리키는 경우 더 큰 `szName` 버퍼를 할당하고 `cchName`을 더 큰 새 크기로 업데이트한 후 `GetAppDomainInfo`를 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea77-116">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetAppDomainInfo` again.</span></span>  
  
 <span data-ttu-id="8ea77-117">또는 길이가 0인 `szName` 버퍼로 `GetAppDomainInfo`를 먼저 호출하여 올바른 버퍼 크기를 구합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea77-117">Alternatively, you can first call `GetAppDomainInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="8ea77-118">그런 다음 버퍼 크기를 `pcchName`에 반환된 값으로 설정하고 `GetAppDomainInfo`을 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea77-118">You can then set the buffer size to the value returned in `pcchName` and call `GetAppDomainInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ea77-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8ea77-119">Requirements</span></span>  

 <span data-ttu-id="8ea77-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ea77-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ea77-121">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8ea77-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8ea77-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ea77-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ea77-123">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ea77-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ea77-124">참조</span><span class="sxs-lookup"><span data-stu-id="8ea77-124">See also</span></span>

- [<span data-ttu-id="8ea77-125">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ea77-125">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="8ea77-126">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ea77-126">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="8ea77-127">프로파일링</span><span class="sxs-lookup"><span data-stu-id="8ea77-127">Profiling</span></span>](index.md)
