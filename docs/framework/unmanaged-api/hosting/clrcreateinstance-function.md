---
description: '자세한 정보: CLRCreateInstance 함수'
title: CLRCreateInstance 함수
ms.date: 03/30/2017
api_name:
- CLRCreateInstance
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- CLRCreateInstance
helpviewer_keywords:
- CLRCreateInstance function [.NET Framework hosting]
ms.assetid: 5de13327-96c6-4697-a89e-b8bf40717855
topic_type:
- apiref
ms.openlocfilehash: 3b4dd9f07444f3e7ca68af3b85a7a053fc72b772
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799943"
---
# <a name="clrcreateinstance-function"></a><span data-ttu-id="80daa-103">CLRCreateInstance 함수</span><span class="sxs-lookup"><span data-stu-id="80daa-103">CLRCreateInstance Function</span></span>

<span data-ttu-id="80daa-104">[ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md)또는 [ICLRDebugging](../debugging/iclrdebugging-interface.md)의 세 가지 인터페이스 중 하나를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="80daa-104">Provides one of three interfaces: [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md), or [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80daa-105">구문</span><span class="sxs-lookup"><span data-stu-id="80daa-105">Syntax</span></span>  
  
```cpp  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80daa-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="80daa-106">Parameters</span></span>  

 `clsid`  
 <span data-ttu-id="80daa-107">진행 CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy 또는 CLSID_CLRDebugging의 세 가지 클래스 식별자 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="80daa-107">[in] One of three class identifiers: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy, or CLSID_CLRDebugging.</span></span>  
  
 `riid`  
 <span data-ttu-id="80daa-108">진행 Iid (인터페이스 식별자): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy 또는 IID_ICLRDebugging 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="80daa-108">[in] One of three interface identifiers (IIDs): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy, or IID_ICLRDebugging.</span></span>  
  
 `ppInterface`  
 <span data-ttu-id="80daa-109">제한이 [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md)또는 [ICLRDebugging](../debugging/iclrdebugging-interface.md)의 세 가지 인터페이스 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="80daa-109">[out] One of three interfaces: [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md), or [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80daa-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="80daa-110">Return Value</span></span>  

 <span data-ttu-id="80daa-111">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="80daa-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="80daa-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="80daa-112">HRESULT</span></span>|<span data-ttu-id="80daa-113">설명</span><span class="sxs-lookup"><span data-stu-id="80daa-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="80daa-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="80daa-114">S_OK</span></span>|<span data-ttu-id="80daa-115">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="80daa-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="80daa-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="80daa-116">E_POINTER</span></span>|<span data-ttu-id="80daa-117">`ppInterface`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="80daa-117">`ppInterface` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80daa-118">설명</span><span class="sxs-lookup"><span data-stu-id="80daa-118">Remarks</span></span>  

 <span data-ttu-id="80daa-119">다음 표에서는 및에 대해 지원 되는 조합을 보여 줍니다 `clsid` `riid` .</span><span class="sxs-lookup"><span data-stu-id="80daa-119">The following table shows the supported combinations for `clsid` and `riid`.</span></span>  
  
|`clsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="80daa-120">CLSID_CLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="80daa-120">CLSID_CLRMetaHost</span></span>|<span data-ttu-id="80daa-121">IID_ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="80daa-121">IID_ICLRMetaHost</span></span>|  
|<span data-ttu-id="80daa-122">CLSID_CLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="80daa-122">CLSID_CLRMetaHostPolicy</span></span>|<span data-ttu-id="80daa-123">IID_ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="80daa-123">IID_ICLRMetaHostPolicy</span></span>|  
|<span data-ttu-id="80daa-124">CLSID_CLRDebugging</span><span class="sxs-lookup"><span data-stu-id="80daa-124">CLSID_CLRDebugging</span></span>|<span data-ttu-id="80daa-125">IID_ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="80daa-125">IID_ICLRDebugging</span></span>|  
  
 <span data-ttu-id="80daa-126">다음 코드에서는를 사용 하 여 `CLRCreateInstance` 세 가지 인터페이스를 모두 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="80daa-126">The following code shows how to use `CLRCreateInstance` to get all three interfaces:</span></span>  
  
```cpp  
#include <metahost.h>  
#pragma comment(lib, "mscoree.lib")  
  
ICLRMetaHost       *pMetaHost       = NULL;  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
ICLRDebugging      *pCLRDebugging   = NULL;  
HRESULT hr;  
hr = CLRCreateInstance(CLSID_CLRMetaHost, IID_ICLRMetaHost,  
                    (LPVOID*)&pMetaHost);  
hr = CLRCreateInstance (CLSID_CLRMetaHostPolicy, IID_ICLRMetaHostPolicy,  
                    (LPVOID*)&pMetaHostPolicy);  
hr = CLRCreateInstance (CLSID_CLRDebugging, IID_ICLRDebugging,  
                    (LPVOID*)&pCLRDebugging);  
```  
  
## <a name="requirements"></a><span data-ttu-id="80daa-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="80daa-127">Requirements</span></span>  

 <span data-ttu-id="80daa-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80daa-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80daa-129">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="80daa-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="80daa-130">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80daa-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80daa-131">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80daa-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80daa-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80daa-132">See also</span></span>

- [<span data-ttu-id="80daa-133">호스팅</span><span class="sxs-lookup"><span data-stu-id="80daa-133">Hosting</span></span>](index.md)
