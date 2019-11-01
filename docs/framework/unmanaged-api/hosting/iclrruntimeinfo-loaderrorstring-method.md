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
ms.openlocfilehash: 20f2041599e85b8df20a7a9cf44680da9f17244e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195937"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="0c984-102">ICLRRuntimeInfo::LoadErrorString 메서드</span><span class="sxs-lookup"><span data-stu-id="0c984-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="0c984-103">HRESULT 값을 지정 된 문화권에 대 한 적절 한 오류 메시지로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c984-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="0c984-104">이 메서드는 다음 함수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c984-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="0c984-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="0c984-105">LoadStringRC</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
- [<span data-ttu-id="0c984-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="0c984-106">LoadStringRCEx</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="0c984-107">구문</span><span class="sxs-lookup"><span data-stu-id="0c984-107">Syntax</span></span>  
  
```cpp  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c984-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c984-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="0c984-109">진행 변환할 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="0c984-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="0c984-110">제한이 지정 된 HRESULT와 연결 된 메시지 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c984-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="0c984-111">[in, out] 버퍼 오버런을 방지 하기 위한 `pwzbuffer` 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="0c984-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="0c984-112">`pwzbuffer`가 null 인 경우 `pcchBuffer`는 예상 되는 `pwzbuffer` 크기를 제공 하 여 미리 할당를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c984-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="0c984-113">진행 문화권 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="0c984-113">[in] The culture identifier.</span></span> <span data-ttu-id="0c984-114">기본 문화권을 사용 하려면-1을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c984-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c984-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="0c984-115">Return Value</span></span>  
 <span data-ttu-id="0c984-116">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0c984-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0c984-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0c984-117">HRESULT</span></span>|<span data-ttu-id="0c984-118">설명</span><span class="sxs-lookup"><span data-stu-id="0c984-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0c984-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="0c984-119">S_OK</span></span>|<span data-ttu-id="0c984-120">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0c984-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="0c984-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="0c984-121">E_POINTER</span></span>|<span data-ttu-id="0c984-122">`pcchBuffer`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="0c984-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="0c984-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0c984-123">E_INVALIDARG</span></span>|<span data-ttu-id="0c984-124">`pwzBuffer`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="0c984-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c984-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c984-125">Requirements</span></span>  
 <span data-ttu-id="0c984-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c984-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c984-127">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="0c984-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0c984-128">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c984-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c984-129">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c984-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c984-130">참조</span><span class="sxs-lookup"><span data-stu-id="0c984-130">See also</span></span>

- [<span data-ttu-id="0c984-131">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c984-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="0c984-132">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c984-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="0c984-133">호스팅</span><span class="sxs-lookup"><span data-stu-id="0c984-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
