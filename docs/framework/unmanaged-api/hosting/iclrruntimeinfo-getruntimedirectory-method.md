---
description: '자세히 알아보기: ICLRRuntimeInfo:: GetRuntimeDirectory 메서드'
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
ms.openlocfilehash: 1e833887568d0a61e9ff9ec358b6979a4bacce41
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637094"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="b26ae-103">ICLRRuntimeInfo::GetRuntimeDirectory 메서드</span><span class="sxs-lookup"><span data-stu-id="b26ae-103">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>

<span data-ttu-id="b26ae-104">이 인터페이스와 연결 된 CLR (공용 언어 런타임)의 설치 디렉터리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b26ae-104">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="b26ae-105">이 메서드는 .NET Framework 버전 2.0, 3.0 및 3.5에 제공 된 [GetCORSystemDirectory](getcorsystemdirectory-function.md) 함수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="b26ae-105">This method supersedes the [GetCORSystemDirectory](getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b26ae-106">구문</span><span class="sxs-lookup"><span data-stu-id="b26ae-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b26ae-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b26ae-107">Parameters</span></span>  

 `pwzBuffer`  
 <span data-ttu-id="b26ae-108">제한이 CLR 설치 디렉터리를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b26ae-108">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="b26ae-109">설치 경로가 정규화 되어 있습니다. 예를 들면 "c:\windows\microsoft.net\framework\v1.0.3705 \\ "입니다.</span><span class="sxs-lookup"><span data-stu-id="b26ae-109">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="b26ae-110">[in, out] `pwzBuffer` 버퍼 오버런을 방지 하기 위해의 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b26ae-110">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="b26ae-111">가 null 인 경우에는 `pwzBuffer` `pchBuffer` 의 필수 크기를 반환 합니다 `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="b26ae-111">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b26ae-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="b26ae-112">Return Value</span></span>  

 <span data-ttu-id="b26ae-113">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b26ae-113">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b26ae-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b26ae-114">HRESULT</span></span>|<span data-ttu-id="b26ae-115">설명</span><span class="sxs-lookup"><span data-stu-id="b26ae-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b26ae-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="b26ae-116">S_OK</span></span>|<span data-ttu-id="b26ae-117">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b26ae-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="b26ae-118">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b26ae-118">E_POINTER</span></span>|<span data-ttu-id="b26ae-119">`pwzBuffer` 또는 `pchBuffer`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="b26ae-119">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b26ae-120">설명</span><span class="sxs-lookup"><span data-stu-id="b26ae-120">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b26ae-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b26ae-121">Requirements</span></span>  

 <span data-ttu-id="b26ae-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b26ae-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b26ae-123">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="b26ae-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b26ae-124">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b26ae-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b26ae-125">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b26ae-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b26ae-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b26ae-126">See also</span></span>

- [<span data-ttu-id="b26ae-127">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b26ae-127">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="b26ae-128">호스팅</span><span class="sxs-lookup"><span data-stu-id="b26ae-128">Hosting</span></span>](index.md)
