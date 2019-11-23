---
title: ICorProfilerInfo3::GetRuntimeInformation 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetRuntimeInformation Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type:
- apiref
ms.openlocfilehash: 20556d85655a0a1bbe069a94b99c19c774a13ce6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449688"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a><span data-ttu-id="5f600-102">ICorProfilerInfo3::GetRuntimeInformation 메서드</span><span class="sxs-lookup"><span data-stu-id="5f600-102">ICorProfilerInfo3::GetRuntimeInformation Method</span></span>
<span data-ttu-id="5f600-103">Provides version information about the common language runtime (CLR) that is being profiled.</span><span class="sxs-lookup"><span data-stu-id="5f600-103">Provides version information about the common language runtime (CLR) that is being profiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f600-104">구문</span><span class="sxs-lookup"><span data-stu-id="5f600-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeInformation(  
       [out] USHORT *pClrInstanceId,  
       [out] COR_PRF_RUNTIME_TYPE *pRuntimeType,  
       [out] USHORT *pMajorVersion,  
       [out] USHORT *pMinorVersion,  
       [out] USHORT *pBuildNumber,  
       [out] USHORT *pQFEVersion,  
       [in]  ULONG  cchVersionString,  
       [out] ULONG  *pcchVersionString,  
       [out, size_is(cchVersionString), length_is(*pcchVersionString)]  
                   WCHAR  szVersionString[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f600-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5f600-105">Parameters</span></span>  
 `pClrInstanceId`  
 <span data-ttu-id="5f600-106">[out] The representative ID of a running CLR instance in a process.</span><span class="sxs-lookup"><span data-stu-id="5f600-106">[out] The representative ID of a running CLR instance in a process.</span></span> <span data-ttu-id="5f600-107">This is the same as the `ClrInstanceID` that the event tracing for Windows (ETW) startup event reports.</span><span class="sxs-lookup"><span data-stu-id="5f600-107">This is the same as the `ClrInstanceID` that the event tracing for Windows (ETW) startup event reports.</span></span>  
  
 `pRuntimeType`  
 <span data-ttu-id="5f600-108">[out] The runtime type.</span><span class="sxs-lookup"><span data-stu-id="5f600-108">[out] The runtime type.</span></span> <span data-ttu-id="5f600-109">This parameter returns `COR_PRF_DESKTOP_CLR` for the desktop version of the CLR, or `COR_PRF_CORE_CLR` for the core version of the CLR used in Silverlight.</span><span class="sxs-lookup"><span data-stu-id="5f600-109">This parameter returns `COR_PRF_DESKTOP_CLR` for the desktop version of the CLR, or `COR_PRF_CORE_CLR` for the core version of the CLR used in Silverlight.</span></span>  
  
 `pMajorVersion`  
 <span data-ttu-id="5f600-110">[out] The major version number of the CLR.</span><span class="sxs-lookup"><span data-stu-id="5f600-110">[out] The major version number of the CLR.</span></span>  
  
 `pMinorVersion`  
 <span data-ttu-id="5f600-111">[out] The minor version number of the CLR.</span><span class="sxs-lookup"><span data-stu-id="5f600-111">[out] The minor version number of the CLR.</span></span>  
  
 `pBuildVersion`  
 <span data-ttu-id="5f600-112">[out] The build version number of the CLR.</span><span class="sxs-lookup"><span data-stu-id="5f600-112">[out] The build version number of the CLR.</span></span>  
  
 `pQFEVersion`  
 <span data-ttu-id="5f600-113">[out] The version number of the CLR that is associated with a software update.</span><span class="sxs-lookup"><span data-stu-id="5f600-113">[out] The version number of the CLR that is associated with a software update.</span></span>  
  
 `cchVersionString`  
 <span data-ttu-id="5f600-114">[in] The length, in characters, of the buffer that `szVersionString` points to.</span><span class="sxs-lookup"><span data-stu-id="5f600-114">[in] The length, in characters, of the buffer that `szVersionString` points to.</span></span>  
  
 `pcchVersionString`  
 <span data-ttu-id="5f600-115">[out] The length, in characters, of `szVersionString`.</span><span class="sxs-lookup"><span data-stu-id="5f600-115">[out] The length, in characters, of `szVersionString`.</span></span>  
  
 `szVersionString`  
 <span data-ttu-id="5f600-116">[out] The CLR version string.</span><span class="sxs-lookup"><span data-stu-id="5f600-116">[out] The CLR version string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f600-117">주의</span><span class="sxs-lookup"><span data-stu-id="5f600-117">Remarks</span></span>  
 <span data-ttu-id="5f600-118">You may pass null for any parameter.</span><span class="sxs-lookup"><span data-stu-id="5f600-118">You may pass null for any parameter.</span></span> <span data-ttu-id="5f600-119">However, `pcchVersionString` cannot be null unless `szVersionString` is also null.</span><span class="sxs-lookup"><span data-stu-id="5f600-119">However, `pcchVersionString` cannot be null unless `szVersionString` is also null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f600-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f600-120">Requirements</span></span>  
 <span data-ttu-id="5f600-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f600-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f600-122">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5f600-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5f600-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f600-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f600-124">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f600-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f600-125">참조</span><span class="sxs-lookup"><span data-stu-id="5f600-125">See also</span></span>

- [<span data-ttu-id="5f600-126">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5f600-126">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="5f600-127">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5f600-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="5f600-128">프로파일링</span><span class="sxs-lookup"><span data-stu-id="5f600-128">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
