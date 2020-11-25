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
ms.openlocfilehash: 24679118e4255282f7da3ff8be2ce9c08250e181
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732049"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="ec6db-102">ICLRRuntimeInfo::GetRuntimeDirectory 메서드</span><span class="sxs-lookup"><span data-stu-id="ec6db-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>

<span data-ttu-id="ec6db-103">이 인터페이스와 연결 된 CLR (공용 언어 런타임)의 설치 디렉터리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ec6db-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="ec6db-104">이 메서드는 .NET Framework 버전 2.0, 3.0 및 3.5에 제공 된 [GetCORSystemDirectory](getcorsystemdirectory-function.md) 함수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6db-104">This method supersedes the [GetCORSystemDirectory](getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec6db-105">구문</span><span class="sxs-lookup"><span data-stu-id="ec6db-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec6db-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ec6db-106">Parameters</span></span>  

 `pwzBuffer`  
 <span data-ttu-id="ec6db-107">제한이 CLR 설치 디렉터리를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6db-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="ec6db-108">설치 경로가 정규화 되어 있습니다. 예를 들면 "c:\windows\microsoft.net\framework\v1.0.3705 \\ "입니다.</span><span class="sxs-lookup"><span data-stu-id="ec6db-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="ec6db-109">[in, out] `pwzBuffer` 버퍼 오버런을 방지 하기 위해의 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6db-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="ec6db-110">가 null 인 경우에는 `pwzBuffer` `pchBuffer` 의 필수 크기를 반환 합니다 `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="ec6db-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec6db-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="ec6db-111">Return Value</span></span>  

 <span data-ttu-id="ec6db-112">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ec6db-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ec6db-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ec6db-113">HRESULT</span></span>|<span data-ttu-id="ec6db-114">설명</span><span class="sxs-lookup"><span data-stu-id="ec6db-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ec6db-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="ec6db-115">S_OK</span></span>|<span data-ttu-id="ec6db-116">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ec6db-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="ec6db-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ec6db-117">E_POINTER</span></span>|<span data-ttu-id="ec6db-118">`pwzBuffer` 또는 `pchBuffer`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="ec6db-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec6db-119">설명</span><span class="sxs-lookup"><span data-stu-id="ec6db-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec6db-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ec6db-120">Requirements</span></span>  

 <span data-ttu-id="ec6db-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ec6db-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec6db-122">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="ec6db-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ec6db-123">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec6db-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec6db-124">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec6db-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec6db-125">참조</span><span class="sxs-lookup"><span data-stu-id="ec6db-125">See also</span></span>

- [<span data-ttu-id="ec6db-126">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ec6db-126">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="ec6db-127">호스팅</span><span class="sxs-lookup"><span data-stu-id="ec6db-127">Hosting</span></span>](index.md)
