---
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
ms.openlocfilehash: 0ce822533b0699f3467dc08044aa4dab59285a77
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120309"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a><span data-ttu-id="bb030-102">ICLRRuntimeInfo::GetDefaultStartupFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="bb030-102">ICLRRuntimeInfo::GetDefaultStartupFlags Method</span></span>
<span data-ttu-id="bb030-103">런타임을 시작 하는 데 사용 되는 시작 플래그 및 호스트 구성 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bb030-103">Gets the startup flags and host configuration file that will be used to start the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb030-104">구문</span><span class="sxs-lookup"><span data-stu-id="bb030-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb030-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bb030-105">Parameters</span></span>  
 `pdwStartupFlags`  
 <span data-ttu-id="bb030-106">제한이 현재 설정 된 호스트 시작 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bb030-106">[out] A pointer to the host startup flags that are currently set.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="bb030-107">제한이 현재 호스트 구성 파일의 디렉터리 경로에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bb030-107">[out] A pointer to the directory path of the current host configuration file.</span></span>  
  
 `pcchHostConfigFile`  
 <span data-ttu-id="bb030-108">[in, out] 입력 시 버퍼 오버런을 방지 하기 위한 `pwzHostConfigFile`크기입니다.</span><span class="sxs-lookup"><span data-stu-id="bb030-108">[in, out] On input, the size of `pwzHostConfigFile`, to avoid buffer overruns.</span></span> <span data-ttu-id="bb030-109">`pwzHostConfigFile`가 null 인 경우 메서드는 미리 할당에 대 한 `pwzHostConfigFile`의 필수 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb030-109">If `pwzHostConfigFile` is null, the method returns the required size of `pwzHostConfigFile` for pre-allocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb030-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="bb030-110">Return Value</span></span>  
 <span data-ttu-id="bb030-111">이 메서드는 다음과 같은 특정 HRESULT 및 메서드 오류를 나타내는 HRESULT 오류를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb030-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="bb030-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bb030-112">HRESULT</span></span>|<span data-ttu-id="bb030-113">설명</span><span class="sxs-lookup"><span data-stu-id="bb030-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bb030-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="bb030-114">S_OK</span></span>|<span data-ttu-id="bb030-115">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bb030-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb030-116">주의</span><span class="sxs-lookup"><span data-stu-id="bb030-116">Remarks</span></span>  
 <span data-ttu-id="bb030-117">이 메서드는 기본 플래그 값 (`STARTUP_CONCURRENT_GC` 및 `NULL`) 또는 [ICLRRuntimeInfo:: SetDefaultStartupFlags 메서드에](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md)대 한 이전 호출에서 제공 된 값 또는이 런타임에 바인딩된 경우 `CorBind*` 메서드가 설정 하는 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb030-117">This method returns the default flag values (`STARTUP_CONCURRENT_GC` and `NULL`), or the values provided by a previous call to the [ICLRRuntimeInfo::SetDefaultStartupFlags method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), or the values set by any of the `CorBind*` methods if they are bound to this runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb030-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bb030-118">Requirements</span></span>  
 <span data-ttu-id="bb030-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb030-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb030-120">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="bb030-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bb030-121">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb030-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb030-122">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb030-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb030-123">참조</span><span class="sxs-lookup"><span data-stu-id="bb030-123">See also</span></span>

- [<span data-ttu-id="bb030-124">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bb030-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="bb030-125">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bb030-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="bb030-126">호스팅</span><span class="sxs-lookup"><span data-stu-id="bb030-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
