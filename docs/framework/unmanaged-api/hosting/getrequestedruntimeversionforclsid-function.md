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
ms.openlocfilehash: 899d6e74902e47f1f41b849bd5c25048baa175f7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617141"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="80ea9-102">GetRequestedRuntimeVersionForCLSID 함수</span><span class="sxs-lookup"><span data-stu-id="80ea9-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="80ea9-103">지정 된을 사용 하 여 클래스에 대 한 적절 한 CLR (공용 언어 런타임) 버전 정보를 가져옵니다 `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="80ea9-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="80ea9-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80ea9-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80ea9-105">구문</span><span class="sxs-lookup"><span data-stu-id="80ea9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,
    [out]  LPWSTR     pVersion,
    [in]  DWORD      cchBuffer,
    [out] DWORD*     dwLength,
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80ea9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="80ea9-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="80ea9-107">진행  `CLSID`구성 요소의입니다.</span><span class="sxs-lookup"><span data-stu-id="80ea9-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="80ea9-108">제한이  성공적으로 완료 되 면 버전 번호 문자열을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="80ea9-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="80ea9-109">진행  버퍼의 크기 (와이드 문자) `pVersion` 입니다.</span><span class="sxs-lookup"><span data-stu-id="80ea9-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="80ea9-110">제한이 반환 된 버퍼의 길이 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="80ea9-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="80ea9-111">진행  CLSID_RESOLUTION_FLAGS 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="80ea9-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="80ea9-112">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80ea9-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="80ea9-113">CLSID_RESOLUTION_DEFAULT: (0x0) 기본 interop 동작을 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ea9-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
- <span data-ttu-id="80ea9-114">CLSID_RESOLUTION_REGISTERED: (0x1) 레지스트리를 검색 하 고 shim 정책을 적용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80ea9-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80ea9-115">Return Value</span><span class="sxs-lookup"><span data-stu-id="80ea9-115">Return Value</span></span>  
  
|<span data-ttu-id="80ea9-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="80ea9-116">HRESULT</span></span>|<span data-ttu-id="80ea9-117">설명</span><span class="sxs-lookup"><span data-stu-id="80ea9-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="80ea9-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="80ea9-118">S_OK</span></span>|<span data-ttu-id="80ea9-119">함수에서을 (를) 반환 했습니다.</span><span class="sxs-lookup"><span data-stu-id="80ea9-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="80ea9-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="80ea9-120">E_INVALIDARG</span></span>|<span data-ttu-id="80ea9-121">매개 변수 중 하나에 잘못 된 형식 또는 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ea9-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="80ea9-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="80ea9-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="80ea9-123">`pVersion`버퍼가 작아서 전체 버전 문자열을 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80ea9-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="80ea9-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="80ea9-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="80ea9-125">지정 된에 등록 된 클래스가 없는 경우 `CLSID`</span><span class="sxs-lookup"><span data-stu-id="80ea9-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="80ea9-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="80ea9-126">E_POINTER</span></span>|<span data-ttu-id="80ea9-127">`dwLength`가 null 이거나 `cchBuffer` 버전 문자열을 저장할 수 있을 만큼 크지만 `pVersion` 가 null 인 경우</span><span class="sxs-lookup"><span data-stu-id="80ea9-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="80ea9-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="80ea9-128">Requirements</span></span>  
 <span data-ttu-id="80ea9-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80ea9-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80ea9-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="80ea9-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="80ea9-131">**.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80ea9-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80ea9-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80ea9-132">See also</span></span>

- [<span data-ttu-id="80ea9-133">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="80ea9-133">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
