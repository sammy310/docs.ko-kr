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
ms.openlocfilehash: 6132e94544b30486b70ecfec49c1ddd5e3c0f50b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178109"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="8cff6-102">GetRequestedRuntimeVersionForCLSID 함수</span><span class="sxs-lookup"><span data-stu-id="8cff6-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="8cff6-103">지정된 `CLSID`을 사용 하 이 클래스에 대 한 적절 한 공통 언어 런타임 (CLR) 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8cff6-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="8cff6-104">이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cff6-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cff6-105">구문</span><span class="sxs-lookup"><span data-stu-id="8cff6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,
    [out]  LPWSTR     pVersion,
    [in]  DWORD      cchBuffer,
    [out] DWORD*     dwLength,
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cff6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8cff6-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="8cff6-107">【인】  구성 `CLSID` 요소의 입니다.</span><span class="sxs-lookup"><span data-stu-id="8cff6-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="8cff6-108">【아웃】  성공적으로 완료되면 버전 번호 문자열이 포함된 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="8cff6-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="8cff6-109">【인】  `pVersion` 버퍼의 크기(와이드 문자)입니다.</span><span class="sxs-lookup"><span data-stu-id="8cff6-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="8cff6-110">【아웃】 반환된 버퍼의 길이(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="8cff6-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="8cff6-111">【인】  CLSID_RESOLUTION_FLAGS 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="8cff6-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="8cff6-112">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cff6-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="8cff6-113">CLSID_RESOLUTION_DEFAULT: (0x0) 기본 interop 동작을 사용해야 하는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8cff6-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
- <span data-ttu-id="8cff6-114">CLSID_RESOLUTION_REGISTERED: (0x1) 레지스트리를 검색 하 고 shim 정책을 적용 해야 합니다 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cff6-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8cff6-115">Return Value</span><span class="sxs-lookup"><span data-stu-id="8cff6-115">Return Value</span></span>  
  
|<span data-ttu-id="8cff6-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8cff6-116">HRESULT</span></span>|<span data-ttu-id="8cff6-117">Description</span><span class="sxs-lookup"><span data-stu-id="8cff6-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8cff6-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="8cff6-118">S_OK</span></span>|<span data-ttu-id="8cff6-119">함수가 성공적으로 반환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8cff6-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="8cff6-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="8cff6-120">E_INVALIDARG</span></span>|<span data-ttu-id="8cff6-121">매개 변수 중 하나에 잘못된 형식 또는 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cff6-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="8cff6-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="8cff6-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="8cff6-123">버퍼가 `pVersion` 전체 버전 문자열을 보유할 만큼 크지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cff6-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="8cff6-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="8cff6-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="8cff6-125">지정된 `CLSID`에 등록된 클래스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8cff6-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="8cff6-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="8cff6-126">E_POINTER</span></span>|<span data-ttu-id="8cff6-127">`dwLength`null이거나 `cchBuffer` 버전 문자열을 보유할 수 있을 `pVersion` 만큼 크지만 null입니다.</span><span class="sxs-lookup"><span data-stu-id="8cff6-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8cff6-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8cff6-128">Requirements</span></span>  
 <span data-ttu-id="8cff6-129">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8cff6-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cff6-130">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="8cff6-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8cff6-131">**.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cff6-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cff6-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8cff6-132">See also</span></span>

- [<span data-ttu-id="8cff6-133">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="8cff6-133">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
