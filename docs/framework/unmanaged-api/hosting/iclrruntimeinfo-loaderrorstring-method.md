---
title: ICLRRuntimeInfo::LoadErrorString 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadErrorString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd7bdcf891146a15953b7466e0f6dc680495bd5a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64585055"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="19e4d-102">ICLRRuntimeInfo::LoadErrorString 메서드</span><span class="sxs-lookup"><span data-stu-id="19e4d-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="19e4d-103">HRESULT 값을 지정된 된 문화권에 대 한 적절 한 오류 메시지를 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="19e4d-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="19e4d-104">이 메서드는 다음 함수를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="19e4d-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="19e4d-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="19e4d-105">LoadStringRC</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
- [<span data-ttu-id="19e4d-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="19e4d-106">LoadStringRCEx</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="19e4d-107">구문</span><span class="sxs-lookup"><span data-stu-id="19e4d-107">Syntax</span></span>  
  
```  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19e4d-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="19e4d-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="19e4d-109">[in] 변환할 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="19e4d-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="19e4d-110">[out] 지정 된 HRESULT와 사용 하 여 연결 된 메시지 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="19e4d-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="19e4d-111">[out에서] 크기 `pwzbuffer` 버퍼 오버런을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="19e4d-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="19e4d-112">하는 경우 `pwzbuffer` 이 null 이면 `pcchBuffer` 의 예상된 크기를 제공 `pwzbuffer` 미리 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="19e4d-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="19e4d-113">[in] 문화권 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="19e4d-113">[in] The culture identifier.</span></span> <span data-ttu-id="19e4d-114">기본 문화권을 사용 하려면-1을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19e4d-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19e4d-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="19e4d-115">Return Value</span></span>  
 <span data-ttu-id="19e4d-116">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="19e4d-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="19e4d-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="19e4d-117">HRESULT</span></span>|<span data-ttu-id="19e4d-118">설명</span><span class="sxs-lookup"><span data-stu-id="19e4d-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19e4d-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="19e4d-119">S_OK</span></span>|<span data-ttu-id="19e4d-120">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="19e4d-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="19e4d-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="19e4d-121">E_POINTER</span></span>|<span data-ttu-id="19e4d-122">`pcchBuffer`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="19e4d-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="19e4d-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="19e4d-123">E_INVALIDARG</span></span>|<span data-ttu-id="19e4d-124">`pwzBuffer`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="19e4d-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="19e4d-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="19e4d-125">Requirements</span></span>  
 <span data-ttu-id="19e4d-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="19e4d-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19e4d-127">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="19e4d-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="19e4d-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="19e4d-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19e4d-129">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19e4d-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19e4d-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="19e4d-130">See also</span></span>

- [<span data-ttu-id="19e4d-131">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19e4d-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="19e4d-132">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19e4d-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="19e4d-133">호스팅</span><span class="sxs-lookup"><span data-stu-id="19e4d-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
