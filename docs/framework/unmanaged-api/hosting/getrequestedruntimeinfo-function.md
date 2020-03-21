---
title: GetRequestedRuntimeInfo 함수
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeInfo
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeInfo
helpviewer_keywords:
- GetRequestedRuntimeInfo function [.NET Framework hosting]
ms.assetid: 0dfd7cdc-c116-4e25-b56a-ac7b0378c942
topic_type:
- apiref
ms.openlocfilehash: db721e1ef774c87de0fa7da178463d832a3da756
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178148"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="d4fe2-102">GetRequestedRuntimeInfo 함수</span><span class="sxs-lookup"><span data-stu-id="d4fe2-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="d4fe2-103">응용 프로그램에서 요청한 공통 언어 런타임(CLR)에 대한 버전 및 디렉터리 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="d4fe2-104">이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4fe2-105">구문</span><span class="sxs-lookup"><span data-stu-id="d4fe2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeInfo (  
    [in]  LPCWSTR  pExe,
    [in]  LPCWSTR  pwszVersion,
    [in]  LPCWSTR  pConfigurationFile,
    [in]  DWORD    startupFlags,
    [in]  DWORD    runtimeInfoFlags,
    [out] LPWSTR   pDirectory,
    [in]  DWORD    dwDirectory,
    [out] DWORD   *dwDirectoryLength,
    [out] LPWSTR   pVersion,
    [in]  DWORD    cchBuffer,
    [out] DWORD   *dwlength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4fe2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d4fe2-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="d4fe2-107">【인】 응용 프로그램의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="d4fe2-108">【인】 런타임의 버전 번호를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="d4fe2-109">【인】 와 연결된 구성 파일의 이름입니다. `pExe`</span><span class="sxs-lookup"><span data-stu-id="d4fe2-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="d4fe2-110">【인】 [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) 열거 값 중 하나 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-110">[in] One or more of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="d4fe2-111">【인】 [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) 열거 값 중 하나 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-111">[in] One or more of the [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="d4fe2-112">【아웃】 성공적으로 완료되면 런타임에 대한 디렉터리 경로를 포함하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="d4fe2-113">【인】 디렉터리 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="d4fe2-114">【아웃】 디렉터리 경로 문자열의 길이에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="d4fe2-115">【아웃】 성공적으로 완료될 때 런타임의 버전 번호를 포함하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="d4fe2-116">【인】 버전 문자열 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="d4fe2-117">【아웃】 버전 문자열의 길이에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4fe2-118">Return Value</span><span class="sxs-lookup"><span data-stu-id="d4fe2-118">Return Value</span></span>  
 <span data-ttu-id="d4fe2-119">이 메서드는 다음 값 외에 WinError.h에 정의된 표준 구성 요소 개체 모델(COM) 오류 코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="d4fe2-120">반환 코드</span><span class="sxs-lookup"><span data-stu-id="d4fe2-120">Return code</span></span>|<span data-ttu-id="d4fe2-121">Description</span><span class="sxs-lookup"><span data-stu-id="d4fe2-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d4fe2-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="d4fe2-122">S_OK</span></span>|<span data-ttu-id="d4fe2-123">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="d4fe2-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="d4fe2-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="d4fe2-125">디렉터리 버퍼가 디렉터리 경로를 저장할 만큼 크지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="d4fe2-126">-또는-</span><span class="sxs-lookup"><span data-stu-id="d4fe2-126">- or -</span></span><br /><br /> <span data-ttu-id="d4fe2-127">버전 버퍼가 버전 문자열을 저장할 만큼 크지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4fe2-128">설명</span><span class="sxs-lookup"><span data-stu-id="d4fe2-128">Remarks</span></span>  
 <span data-ttu-id="d4fe2-129">메서드는 `GetRequestedRuntimeInfo` 프로세스에 로드된 버전에 대한 런타임 정보를 반환하며, 컴퓨터에 설치된 최신 버전은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="d4fe2-130">.NET Framework 버전 2.0에서는 다음과 같이 메서드를 사용하여 최신 `GetRequestedRuntimeInfo` 설치된 버전에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
- <span data-ttu-id="d4fe2-131">`pExe`에서 및 `pwszVersion` `pConfigurationFile` 매개 변수를 null로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
- <span data-ttu-id="d4fe2-132">매개 변수에 대한 `RUNTIME_INFO_FLAGS` 열거형에 `runtimeInfoFlags` RUNTIME_INFO_UPGRADE_VERSION 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="d4fe2-133">메서드는 `GetRequestedRuntimeInfo` 다음과 같은 상황에서 최신 CLR 버전을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
- <span data-ttu-id="d4fe2-134">특정 CLR 버전 로드를 지정하는 응용 프로그램 구성 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="d4fe2-135">.NET Framework는 `pConfigurationFile` 매개 변수에 대해 null을 지정하는 경우에도 구성 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
- <span data-ttu-id="d4fe2-136">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 메서드는 이전 CLR 버전을 지정하는 방법을 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-136">The [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
- <span data-ttu-id="d4fe2-137">이전 CLR 버전에 대해 컴파일된 응용 프로그램이 현재 실행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="d4fe2-138">매개 `runtimeInfoFlags` 변수의 경우 한 번에 `RUNTIME_INFO_FLAGS` 열거형의 아키텍처 상수 중 하나만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
- <span data-ttu-id="d4fe2-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="d4fe2-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="d4fe2-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="d4fe2-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="d4fe2-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="d4fe2-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4fe2-142">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d4fe2-142">Requirements</span></span>  
 <span data-ttu-id="d4fe2-143">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4fe2-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4fe2-144">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="d4fe2-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d4fe2-145">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d4fe2-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d4fe2-146">**.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4fe2-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4fe2-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4fe2-147">See also</span></span>

- [<span data-ttu-id="d4fe2-148">GetRequestedRuntimeVersion 함수</span><span class="sxs-lookup"><span data-stu-id="d4fe2-148">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="d4fe2-149">GetVersionFromProcess 함수</span><span class="sxs-lookup"><span data-stu-id="d4fe2-149">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="d4fe2-150">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="d4fe2-150">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
