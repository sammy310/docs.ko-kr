---
description: '자세히 알아보기: ICLRRuntimeInfo:: LoadErrorString 메서드'
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
ms.openlocfilehash: 0523b5b89072db50c83c52065c22e9df7167a027
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785070"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="a35fc-103">ICLRRuntimeInfo::LoadErrorString 메서드</span><span class="sxs-lookup"><span data-stu-id="a35fc-103">ICLRRuntimeInfo::LoadErrorString Method</span></span>

<span data-ttu-id="a35fc-104">HRESULT 값을 지정 된 문화권에 대 한 적절 한 오류 메시지로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a35fc-104">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="a35fc-105">이 메서드는 다음 함수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="a35fc-105">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="a35fc-106">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="a35fc-106">LoadStringRC</span></span>](loadstringrc-function.md)  
  
- [<span data-ttu-id="a35fc-107">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="a35fc-107">LoadStringRCEx</span></span>](loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="a35fc-108">구문</span><span class="sxs-lookup"><span data-stu-id="a35fc-108">Syntax</span></span>  
  
```cpp  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a35fc-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a35fc-109">Parameters</span></span>  

 `iResourceID`  
 <span data-ttu-id="a35fc-110">진행 변환할 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="a35fc-110">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="a35fc-111">제한이 지정 된 HRESULT와 연결 된 메시지 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a35fc-111">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="a35fc-112">[in, out] `pwzbuffer` 버퍼 오버런을 방지 하기 위한의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a35fc-112">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="a35fc-113">가 null 인 경우는 `pwzbuffer` `pcchBuffer` 미리 할당을 허용 하는의 예상 크기를 제공 합니다 `pwzbuffer` .</span><span class="sxs-lookup"><span data-stu-id="a35fc-113">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="a35fc-114">진행 문화권 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="a35fc-114">[in] The culture identifier.</span></span> <span data-ttu-id="a35fc-115">기본 문화권을 사용 하려면-1을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a35fc-115">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a35fc-116">Return Value</span><span class="sxs-lookup"><span data-stu-id="a35fc-116">Return Value</span></span>  

 <span data-ttu-id="a35fc-117">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a35fc-117">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a35fc-118">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a35fc-118">HRESULT</span></span>|<span data-ttu-id="a35fc-119">설명</span><span class="sxs-lookup"><span data-stu-id="a35fc-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a35fc-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="a35fc-120">S_OK</span></span>|<span data-ttu-id="a35fc-121">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a35fc-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="a35fc-122">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="a35fc-122">E_POINTER</span></span>|<span data-ttu-id="a35fc-123">`pcchBuffer`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="a35fc-123">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="a35fc-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a35fc-124">E_INVALIDARG</span></span>|<span data-ttu-id="a35fc-125">`pwzBuffer`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="a35fc-125">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a35fc-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a35fc-126">Requirements</span></span>  

 <span data-ttu-id="a35fc-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a35fc-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a35fc-128">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="a35fc-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a35fc-129">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a35fc-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a35fc-130">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a35fc-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a35fc-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a35fc-131">See also</span></span>

- [<span data-ttu-id="a35fc-132">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a35fc-132">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="a35fc-133">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a35fc-133">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="a35fc-134">호스팅</span><span class="sxs-lookup"><span data-stu-id="a35fc-134">Hosting</span></span>](index.md)
