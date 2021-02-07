---
description: '자세히 알아보기: ICLRRuntimeInfo:: GetVersionString 메서드'
title: ICLRRuntimeInfo::GetVersionString 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetVersionString
helpviewer_keywords:
- ICLRRuntimeInfo::GetVersionString method [.NET Framework hosting]
- GetVersionString method, ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 98b097ef-2276-4dd9-8551-b03c972e8179
topic_type:
- apiref
ms.openlocfilehash: 1c7603f4e9bb1142c415ba9da7a05a52d2d5e776
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753876"
---
# <a name="iclrruntimeinfogetversionstring-method"></a><span data-ttu-id="71c90-103">ICLRRuntimeInfo::GetVersionString 메서드</span><span class="sxs-lookup"><span data-stu-id="71c90-103">ICLRRuntimeInfo::GetVersionString Method</span></span>

<span data-ttu-id="71c90-104">지정 된 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 인터페이스와 연결 된 CLR (공용 언어 런타임) 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="71c90-104">Gets common language runtime (CLR) version information associated with a given [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="71c90-105">이 메서드는 다음 함수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c90-105">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="71c90-106">GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="71c90-106">GetRequestedRuntimeInfo</span></span>](getrequestedruntimeinfo-function.md)  
  
- [<span data-ttu-id="71c90-107">GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="71c90-107">GetRequestedRuntimeVersion</span></span>](getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="71c90-108">구문</span><span class="sxs-lookup"><span data-stu-id="71c90-108">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71c90-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="71c90-109">Parameters</span></span>  

 `pwzBuffer`  
 <span data-ttu-id="71c90-110">제한이 "V *A*. 형식의 .NET Framework 컴파일 버전입니다. *B*[.*X*] ".</span><span class="sxs-lookup"><span data-stu-id="71c90-110">[out] The .NET Framework compilation version in the format "v *A*.*B*[.*X*]".</span></span> <span data-ttu-id="71c90-111">*A*, *B* 및 *X* 는 주 버전, 부 버전 및 빌드 번호에 해당 하는 10 진수입니다.</span><span class="sxs-lookup"><span data-stu-id="71c90-111">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="71c90-112">*X* 는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="71c90-112">*X* is optional.</span></span> <span data-ttu-id="71c90-113">*X* 가 없는 경우에는 후행 기간이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71c90-113">If *X* is not present, there is no trailing period.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="71c90-114">이 매개 변수는 C:\Windows\Microsoft.NET\Framework. 아래에 표시 되는 .NET Framework 버전의 디렉터리 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c90-114">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="71c90-115">예제 값은 "v v1.0.3705", "v 1.1.4322", "v 2.0.50727" 및 "v 4.0입니다. *x*", 여기서 *x* 는 설치 된 빌드 번호에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="71c90-115">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*x*", where *x* depends on the build number installed.</span></span> <span data-ttu-id="71c90-116">"V" 접두사는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="71c90-116">Note that the "v" prefix is mandatory.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="71c90-117">[in, out] `pwzBuffer` 버퍼 오버런을 방지 하기 위해의 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c90-117">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="71c90-118">`pwzBuffer`가 이면 `null` 미리 할당을 `pchBuffer` 허용 하기 위해의 필요한 크기를 반환 `pwzBuffer` 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c90-118">If `pwzBuffer` is `null`, `pchBuffer` returns the required size of `pwzBuffer` to allow preallocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71c90-119">Return Value</span><span class="sxs-lookup"><span data-stu-id="71c90-119">Return Value</span></span>  

 <span data-ttu-id="71c90-120">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="71c90-120">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="71c90-121">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71c90-121">HRESULT</span></span>|<span data-ttu-id="71c90-122">설명</span><span class="sxs-lookup"><span data-stu-id="71c90-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71c90-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="71c90-123">S_OK</span></span>|<span data-ttu-id="71c90-124">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="71c90-124">The method completed successfully.</span></span>|  
|<span data-ttu-id="71c90-125">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="71c90-125">E_POINTER</span></span>|<span data-ttu-id="71c90-126">`pwzBuffer` 또는 `pchBuffer`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="71c90-126">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71c90-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="71c90-127">Requirements</span></span>  

 <span data-ttu-id="71c90-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71c90-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71c90-129">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="71c90-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="71c90-130">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c90-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71c90-131">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71c90-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71c90-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71c90-132">See also</span></span>

- [<span data-ttu-id="71c90-133">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="71c90-133">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="71c90-134">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="71c90-134">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="71c90-135">.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="71c90-135">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="71c90-136">호스팅</span><span class="sxs-lookup"><span data-stu-id="71c90-136">Hosting</span></span>](index.md)
