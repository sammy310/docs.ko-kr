---
title: GetRequestedRuntimeVersionForCLSID 함수
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersionForCLSID
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersionForCLSID
helpviewer_keywords:
- GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ca125932ede48aa43bc51e3d5a7851fb7762547
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490311"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="544f3-102">GetRequestedRuntimeVersionForCLSID 함수</span><span class="sxs-lookup"><span data-stu-id="544f3-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="544f3-103">적절 한 공용 언어 런타임 (CLR) 버전 정보가 지정 된 클래스에 대 한 가져옵니다 `CLSID`합니다.</span><span class="sxs-lookup"><span data-stu-id="544f3-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="544f3-104">.NET Framework 4에서이 함수에 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="544f3-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="544f3-105">구문</span><span class="sxs-lookup"><span data-stu-id="544f3-105">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="544f3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="544f3-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="544f3-107">[in]  `CLSID` 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="544f3-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="544f3-108">[out]  성공적으로 완료 되는 버전 번호 문자열을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="544f3-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="544f3-109">[in]  와이드 문자에서 크기의는 `pVersion` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="544f3-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="544f3-110">[out] 반환된 된 버퍼의 길이 (바이트) 합니다.</span><span class="sxs-lookup"><span data-stu-id="544f3-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="544f3-111">[in]  CLSID_RESOLUTION_FLAGS 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="544f3-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="544f3-112">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="544f3-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="544f3-113">CLSID_RESOLUTION_DEFAULT: (0x0) 기본 interop 동작을 사용 해야 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="544f3-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
- <span data-ttu-id="544f3-114">CLSID_RESOLUTION_REGISTERED: (0x1) 검색 해야 하는 레지스트리 및 적용할 shim 정책을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="544f3-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="544f3-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="544f3-115">Return Value</span></span>  
  
|<span data-ttu-id="544f3-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="544f3-116">HRESULT</span></span>|<span data-ttu-id="544f3-117">설명</span><span class="sxs-lookup"><span data-stu-id="544f3-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="544f3-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="544f3-118">S_OK</span></span>|<span data-ttu-id="544f3-119">함수 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="544f3-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="544f3-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="544f3-120">E_INVALIDARG</span></span>|<span data-ttu-id="544f3-121">매개 변수 중 하나에 잘못 된 형식 또는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="544f3-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="544f3-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="544f3-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="544f3-123">`pVersion` 버퍼가 전체 버전 문자열을 저장할 만큼 충분히 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="544f3-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="544f3-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="544f3-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="544f3-125">지정 된 등록 클래스인 `CLSID`합니다.</span><span class="sxs-lookup"><span data-stu-id="544f3-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="544f3-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="544f3-126">E_POINTER</span></span>|<span data-ttu-id="544f3-127">`dwLength` 이 null 또는 `cchBuffer` 버전 문자열을 포함할 수 있도록 충분히 큰 있지만 `pVersion` null입니다.</span><span class="sxs-lookup"><span data-stu-id="544f3-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="544f3-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="544f3-128">Requirements</span></span>  
 <span data-ttu-id="544f3-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="544f3-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="544f3-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="544f3-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="544f3-131">**.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="544f3-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="544f3-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="544f3-132">See also</span></span>

- [<span data-ttu-id="544f3-133">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="544f3-133">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
