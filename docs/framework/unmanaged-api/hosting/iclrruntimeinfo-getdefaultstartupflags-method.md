---
description: '자세히 알아보기: ICLRRuntimeInfo:: GetDefaultStartupFlags 메서드'
title: ICLRRuntimeInfo::GetDefaultStartupFlags 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
ms.openlocfilehash: c6afb19319fd24d499c2c216f2ce0adc2e7a886c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637179"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a><span data-ttu-id="36ec1-103">ICLRRuntimeInfo::GetDefaultStartupFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="36ec1-103">ICLRRuntimeInfo::GetDefaultStartupFlags Method</span></span>

<span data-ttu-id="36ec1-104">런타임을 시작 하는 데 사용 되는 시작 플래그 및 호스트 구성 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="36ec1-104">Gets the startup flags and host configuration file that will be used to start the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36ec1-105">구문</span><span class="sxs-lookup"><span data-stu-id="36ec1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36ec1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="36ec1-106">Parameters</span></span>  

 `pdwStartupFlags`  
 <span data-ttu-id="36ec1-107">제한이 현재 설정 된 호스트 시작 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="36ec1-107">[out] A pointer to the host startup flags that are currently set.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="36ec1-108">제한이 현재 호스트 구성 파일의 디렉터리 경로에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="36ec1-108">[out] A pointer to the directory path of the current host configuration file.</span></span>  
  
 `pcchHostConfigFile`  
 <span data-ttu-id="36ec1-109">[in, out] 입력 시 `pwzHostConfigFile` 버퍼 오버런을 방지 하기 위한의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="36ec1-109">[in, out] On input, the size of `pwzHostConfigFile`, to avoid buffer overruns.</span></span> <span data-ttu-id="36ec1-110">`pwzHostConfigFile`가 null 인 경우 메서드는 `pwzHostConfigFile` 미리 할당을 위해의 필수 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="36ec1-110">If `pwzHostConfigFile` is null, the method returns the required size of `pwzHostConfigFile` for pre-allocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36ec1-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="36ec1-111">Return Value</span></span>  

 <span data-ttu-id="36ec1-112">이 메서드는 다음과 같은 특정 HRESULT 및 메서드 오류를 나타내는 HRESULT 오류를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="36ec1-112">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="36ec1-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="36ec1-113">HRESULT</span></span>|<span data-ttu-id="36ec1-114">설명</span><span class="sxs-lookup"><span data-stu-id="36ec1-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="36ec1-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="36ec1-115">S_OK</span></span>|<span data-ttu-id="36ec1-116">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="36ec1-116">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36ec1-117">설명</span><span class="sxs-lookup"><span data-stu-id="36ec1-117">Remarks</span></span>  

 <span data-ttu-id="36ec1-118">이 메서드는 기본 플래그 값 ( `STARTUP_CONCURRENT_GC` 및 `NULL` )을 반환 하거나, [ICLRRuntimeInfo:: SetDefaultStartupFlags 메서드에](iclrruntimeinfo-setdefaultstartupflags-method.md)대 한 이전 호출에서 제공 된 값을 반환 하거나, `CorBind*` 이 런타임에 바인딩된 경우 메서드에 의해 설정 된 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="36ec1-118">This method returns the default flag values (`STARTUP_CONCURRENT_GC` and `NULL`), or the values provided by a previous call to the [ICLRRuntimeInfo::SetDefaultStartupFlags method](iclrruntimeinfo-setdefaultstartupflags-method.md), or the values set by any of the `CorBind*` methods if they are bound to this runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36ec1-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="36ec1-119">Requirements</span></span>  

 <span data-ttu-id="36ec1-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36ec1-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36ec1-121">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="36ec1-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="36ec1-122">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36ec1-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="36ec1-123">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36ec1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36ec1-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36ec1-124">See also</span></span>

- [<span data-ttu-id="36ec1-125">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36ec1-125">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="36ec1-126">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36ec1-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="36ec1-127">호스팅</span><span class="sxs-lookup"><span data-stu-id="36ec1-127">Hosting</span></span>](index.md)
