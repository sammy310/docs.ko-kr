---
description: '자세히 알아보기: ICLRDomainManager:: Set Fordefaultappdomain 메서드'
title: ICLRDomainManager::SetPropertiesForDefaultAppDomain 메서드
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
ms.openlocfilehash: 08e6c885d5d089fa22c30a4e3cef69480b840031
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689445"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="59062-103">ICLRDomainManager::SetPropertiesForDefaultAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="59062-103">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>

<span data-ttu-id="59062-104">기본 응용 프로그램 도메인을 초기화 하는 데 사용 되는 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="59062-104">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59062-105">구문</span><span class="sxs-lookup"><span data-stu-id="59062-105">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59062-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59062-106">Parameters</span></span>  

 `nProperties`  
 <span data-ttu-id="59062-107">진행 및의 항목 수입니다 `pwszPropertyNames` `pwszPropertyValues` .</span><span class="sxs-lookup"><span data-stu-id="59062-107">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="59062-108">진행 속성 이름의 배열 이거나, 속성이 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="59062-108">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="59062-109">현재이 메서드에서 인식 되는 유일한 속성 이름은 "PARTIAL_TRUST_VISIBLE_ASSEMBLIES"입니다.</span><span class="sxs-lookup"><span data-stu-id="59062-109">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="59062-110">진행 속성 값의 배열 이거나, 속성이 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="59062-110">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59062-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="59062-111">Return Value</span></span>  

 <span data-ttu-id="59062-112">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="59062-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="59062-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="59062-113">HRESULT</span></span>|<span data-ttu-id="59062-114">설명</span><span class="sxs-lookup"><span data-stu-id="59062-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="59062-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="59062-115">S_OK</span></span>|<span data-ttu-id="59062-116">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="59062-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="59062-117">HRESULT_FROM_WIN32 (ERROR_UNKNOWN_PROPERTY)</span><span class="sxs-lookup"><span data-stu-id="59062-117">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|<span data-ttu-id="59062-118">`pwszPropertyNames` 이 메서드에서 인식 하지 않는 속성 이름을 포함 하는 경우</span><span class="sxs-lookup"><span data-stu-id="59062-118">`pwszPropertyNames` includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59062-119">설명</span><span class="sxs-lookup"><span data-stu-id="59062-119">Remarks</span></span>  

 <span data-ttu-id="59062-120">"PARTIAL_TRUST_VISIBLE_ASSEMBLIES"에 대 한 속성 값은 플래그를 사용 하는 조건부 (APTCA) 특성을 포함 하는 어셈블리 목록으로 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> , 기본 응용 프로그램 도메인에서 부분적으로 신뢰할 수 있는 호출자에 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59062-120">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59062-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59062-121">Requirements</span></span>  

 <span data-ttu-id="59062-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59062-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59062-123">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="59062-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="59062-124">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59062-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="59062-125">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59062-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59062-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59062-126">See also</span></span>

- [<span data-ttu-id="59062-127">호스팅</span><span class="sxs-lookup"><span data-stu-id="59062-127">Hosting</span></span>](index.md)
- [<span data-ttu-id="59062-128">ICLRDomainManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59062-128">ICLRDomainManager Interface</span></span>](iclrdomainmanager-interface.md)
