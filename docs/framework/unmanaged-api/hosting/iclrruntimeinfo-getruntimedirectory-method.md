---
title: ICLRRuntimeInfo::GetRuntimeDirectory 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetRuntimeDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type:
- apiref
ms.openlocfilehash: b0a2e5f259fe1ee566f9cc25152b2d2a1f740bea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120335"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="24970-102">ICLRRuntimeInfo::GetRuntimeDirectory 메서드</span><span class="sxs-lookup"><span data-stu-id="24970-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="24970-103">이 인터페이스와 연결 된 CLR (공용 언어 런타임)의 설치 디렉터리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="24970-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="24970-104">이 메서드는 .NET Framework 버전 2.0, 3.0 및 3.5에 제공 된 [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) 함수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="24970-104">This method supersedes the [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24970-105">구문</span><span class="sxs-lookup"><span data-stu-id="24970-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24970-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="24970-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="24970-107">제한이 CLR 설치 디렉터리를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="24970-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="24970-108">설치 경로가 정규화 되어 있습니다. 예를 들면 "c:\windows\microsoft.net\framework\v1.0.3705\\"입니다.</span><span class="sxs-lookup"><span data-stu-id="24970-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="24970-109">[in, out] 버퍼 오버런을 방지 하기 위해 `pwzBuffer`의 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="24970-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="24970-110">`pwzBuffer`가 null 이면 `pchBuffer` `pwzBuffer`의 필수 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="24970-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="24970-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="24970-111">Return Value</span></span>  
 <span data-ttu-id="24970-112">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="24970-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="24970-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="24970-113">HRESULT</span></span>|<span data-ttu-id="24970-114">설명</span><span class="sxs-lookup"><span data-stu-id="24970-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="24970-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="24970-115">S_OK</span></span>|<span data-ttu-id="24970-116">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="24970-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="24970-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="24970-117">E_POINTER</span></span>|<span data-ttu-id="24970-118">`pwzBuffer` 또는 `pchBuffer`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="24970-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24970-119">주의</span><span class="sxs-lookup"><span data-stu-id="24970-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24970-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="24970-120">Requirements</span></span>  
 <span data-ttu-id="24970-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24970-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24970-122">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="24970-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="24970-123">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24970-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="24970-124">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24970-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24970-125">참조</span><span class="sxs-lookup"><span data-stu-id="24970-125">See also</span></span>

- [<span data-ttu-id="24970-126">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="24970-126">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="24970-127">호스팅</span><span class="sxs-lookup"><span data-stu-id="24970-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
