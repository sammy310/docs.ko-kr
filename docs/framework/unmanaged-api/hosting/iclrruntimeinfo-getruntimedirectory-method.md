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
ms.openlocfilehash: d744abf5c502e9b9510cf9fd6479149b6c2177cc
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762216"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="9f3c3-102">ICLRRuntimeInfo::GetRuntimeDirectory 메서드</span><span class="sxs-lookup"><span data-stu-id="9f3c3-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="9f3c3-103">이 인터페이스와 연결 된 CLR (공용 언어 런타임)의 설치 디렉터리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9f3c3-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="9f3c3-104">이 메서드는 .NET Framework 버전 2.0, 3.0 및 3.5에 제공 된 [GetCORSystemDirectory](getcorsystemdirectory-function.md) 함수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3c3-104">This method supersedes the [GetCORSystemDirectory](getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f3c3-105">구문</span><span class="sxs-lookup"><span data-stu-id="9f3c3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f3c3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9f3c3-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="9f3c3-107">제한이 CLR 설치 디렉터리를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3c3-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="9f3c3-108">설치 경로가 정규화 되어 있습니다. 예를 들면 "c:\windows\microsoft.net\framework\v1.0.3705 \\ "입니다.</span><span class="sxs-lookup"><span data-stu-id="9f3c3-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="9f3c3-109">[in, out] `pwzBuffer`버퍼 오버런을 방지 하기 위해의 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3c3-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="9f3c3-110">가 null 인 경우에는 `pwzBuffer` `pchBuffer` 의 필수 크기를 반환 합니다 `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="9f3c3-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f3c3-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="9f3c3-111">Return Value</span></span>  
 <span data-ttu-id="9f3c3-112">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9f3c3-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9f3c3-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9f3c3-113">HRESULT</span></span>|<span data-ttu-id="9f3c3-114">Description</span><span class="sxs-lookup"><span data-stu-id="9f3c3-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9f3c3-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="9f3c3-115">S_OK</span></span>|<span data-ttu-id="9f3c3-116">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9f3c3-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="9f3c3-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="9f3c3-117">E_POINTER</span></span>|<span data-ttu-id="9f3c3-118">`pwzBuffer` 또는 `pchBuffer` 이 null입니다.</span><span class="sxs-lookup"><span data-stu-id="9f3c3-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f3c3-119">설명</span><span class="sxs-lookup"><span data-stu-id="9f3c3-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f3c3-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9f3c3-120">Requirements</span></span>  
 <span data-ttu-id="9f3c3-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f3c3-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f3c3-122">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="9f3c3-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9f3c3-123">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f3c3-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f3c3-124">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f3c3-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f3c3-125">참조</span><span class="sxs-lookup"><span data-stu-id="9f3c3-125">See also</span></span>

- [<span data-ttu-id="9f3c3-126">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9f3c3-126">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="9f3c3-127">호스팅</span><span class="sxs-lookup"><span data-stu-id="9f3c3-127">Hosting</span></span>](index.md)
