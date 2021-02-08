---
description: '자세히 알아보기: GetRequestedRuntimeInfo 함수'
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
ms.openlocfilehash: 63d0bdcd07be5727cddc0acc352e8358b5ff0090
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785291"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="818d6-103">GetRequestedRuntimeInfo 함수</span><span class="sxs-lookup"><span data-stu-id="818d6-103">GetRequestedRuntimeInfo Function</span></span>

<span data-ttu-id="818d6-104">응용 프로그램에서 요청 하는 CLR (공용 언어 런타임)에 대 한 버전 및 디렉터리 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-104">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="818d6-105">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="818d6-106">구문</span><span class="sxs-lookup"><span data-stu-id="818d6-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="818d6-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="818d6-107">Parameters</span></span>  

 `pExe`  
 <span data-ttu-id="818d6-108">진행 응용 프로그램의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-108">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="818d6-109">진행 런타임의 버전 번호를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-109">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="818d6-110">진행 와 연결 된 구성 파일의 이름입니다 `pExe` .</span><span class="sxs-lookup"><span data-stu-id="818d6-110">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="818d6-111">진행 [STARTUP_FLAGS](startup-flags-enumeration.md) 열거형 값 중 하나 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-111">[in] One or more of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="818d6-112">진행 [RUNTIME_INFO_FLAGS](runtime-info-flags-enumeration.md) 열거형 값 중 하나 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-112">[in] One or more of the [RUNTIME_INFO_FLAGS](runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="818d6-113">제한이 성공적으로 완료 되 면 런타임에 대 한 디렉터리 경로를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-113">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="818d6-114">진행 디렉터리 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-114">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="818d6-115">제한이 디렉터리 경로 문자열의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-115">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="818d6-116">제한이 성공적으로 완료 되 면 런타임의 버전 번호를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-116">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="818d6-117">진행 버전 문자열 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-117">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="818d6-118">제한이 버전 문자열의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-118">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="818d6-119">Return Value</span><span class="sxs-lookup"><span data-stu-id="818d6-119">Return Value</span></span>  

 <span data-ttu-id="818d6-120">이 메서드는 Winerror.h에 정의 된 대로 다음 값 외에 표준 COM (구성 요소 개체 모델) 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-120">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="818d6-121">반환 코드</span><span class="sxs-lookup"><span data-stu-id="818d6-121">Return code</span></span>|<span data-ttu-id="818d6-122">설명</span><span class="sxs-lookup"><span data-stu-id="818d6-122">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="818d6-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="818d6-123">S_OK</span></span>|<span data-ttu-id="818d6-124">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-124">The method completed successfully.</span></span>|  
|<span data-ttu-id="818d6-125">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="818d6-125">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="818d6-126">디렉터리 버퍼가 디렉터리 경로를 저장할 만큼 크지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-126">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="818d6-127">또는</span><span class="sxs-lookup"><span data-stu-id="818d6-127">- or -</span></span><br /><br /> <span data-ttu-id="818d6-128">버전 버퍼의 크기가 작아서 버전 문자열을 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-128">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="818d6-129">설명</span><span class="sxs-lookup"><span data-stu-id="818d6-129">Remarks</span></span>  

 <span data-ttu-id="818d6-130">`GetRequestedRuntimeInfo`메서드는 프로세스에 로드 된 버전에 대 한 런타임 정보를 반환 합니다 .이 정보는 컴퓨터에 최신 버전이 설치 되어 있지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-130">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="818d6-131">.NET Framework 버전 2.0에서는 다음과 같이 메서드를 사용 하 여 설치 된 최신 버전에 대 한 정보를 가져올 수 있습니다 `GetRequestedRuntimeInfo` .</span><span class="sxs-lookup"><span data-stu-id="818d6-131">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
- <span data-ttu-id="818d6-132">`pExe`, `pwszVersion` 및 `pConfigurationFile` 매개 변수를 null로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-132">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
- <span data-ttu-id="818d6-133">`RUNTIME_INFO_FLAGS`매개 변수에 대 한 열거형에 RUNTIME_INFO_UPGRADE_VERSION 플래그를 지정 합니다 `runtimeInfoFlags` .</span><span class="sxs-lookup"><span data-stu-id="818d6-133">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="818d6-134">`GetRequestedRuntimeInfo`메서드는 다음과 같은 상황에서 최신 CLR 버전을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-134">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
- <span data-ttu-id="818d6-135">특정 CLR 버전 로드를 지정 하는 응용 프로그램 구성 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-135">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="818d6-136">매개 변수에 null을 지정 하는 경우에도 .NET Framework는 구성 파일을 사용 합니다 `pConfigurationFile` .</span><span class="sxs-lookup"><span data-stu-id="818d6-136">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
- <span data-ttu-id="818d6-137">이전 CLR 버전을 지정 하 여 [CorBindToRuntimeEx](corbindtoruntimeex-function.md) 메서드를 호출 했습니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-137">The [CorBindToRuntimeEx](corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
- <span data-ttu-id="818d6-138">이전 CLR 버전용으로 컴파일된 응용 프로그램이 현재 실행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="818d6-138">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="818d6-139">`runtimeInfoFlags`매개 변수의 경우 한 번에 열거의 아키텍처 상수 중 하나만 지정할 수 있습니다 `RUNTIME_INFO_FLAGS` .</span><span class="sxs-lookup"><span data-stu-id="818d6-139">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
- <span data-ttu-id="818d6-140">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="818d6-140">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="818d6-141">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="818d6-141">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="818d6-142">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="818d6-142">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="818d6-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="818d6-143">Requirements</span></span>  

 <span data-ttu-id="818d6-144">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="818d6-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="818d6-145">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="818d6-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="818d6-146">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="818d6-146">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="818d6-147">**.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="818d6-147">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="818d6-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="818d6-148">See also</span></span>

- [<span data-ttu-id="818d6-149">GetRequestedRuntimeVersion 함수</span><span class="sxs-lookup"><span data-stu-id="818d6-149">GetRequestedRuntimeVersion Function</span></span>](getrequestedruntimeversion-function.md)
- [<span data-ttu-id="818d6-150">GetVersionFromProcess 함수</span><span class="sxs-lookup"><span data-stu-id="818d6-150">GetVersionFromProcess Function</span></span>](getversionfromprocess-function.md)
- [<span data-ttu-id="818d6-151">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="818d6-151">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
