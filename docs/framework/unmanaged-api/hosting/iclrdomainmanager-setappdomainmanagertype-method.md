---
title: ICLRDomainManager::SetAppDomainManagerType 메서드
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cfef7d929d40996716a02a4db51630827011a68
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183250"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="eb946-102">ICLRDomainManager::SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="eb946-102">ICLRDomainManager::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="eb946-103">파생 된 유형을 지정 합니다 <xref:System.AppDomainManager?displayProperty=nameWithType> 기본 응용 프로그램 도메인을 초기화 하는 데 사용할 응용 프로그램 도메인 관리자의 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="eb946-103">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb946-104">구문</span><span class="sxs-lookup"><span data-stu-id="eb946-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb946-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eb946-105">Parameters</span></span>  
 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="eb946-106">[in] 응용 프로그램 도메인 관리자 유형;를 포함 하는 어셈블리의 표시 이름 예를 들어: "AdMgrExample, 버전 1.0.0.0, Culture = neutral, PublicKeyToken = 6856bccf150f00b3 ="입니다.</span><span class="sxs-lookup"><span data-stu-id="eb946-106">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="eb946-107">[in] 네임 스페이스를 포함 하 여 응용 프로그램 도메인 관리자의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="eb946-107">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="eb946-108">[in] 조합을 [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) 응용 프로그램 도메인 관리자에 대 한 정보를 제공 하는 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="eb946-108">[in] A combination of [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb946-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="eb946-109">Return Value</span></span>  
 <span data-ttu-id="eb946-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="eb946-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="eb946-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eb946-111">HRESULT</span></span>|<span data-ttu-id="eb946-112">설명</span><span class="sxs-lookup"><span data-stu-id="eb946-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eb946-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="eb946-113">S_OK</span></span>|<span data-ttu-id="eb946-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="eb946-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="eb946-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="eb946-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="eb946-116">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb946-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb946-117">설명</span><span class="sxs-lookup"><span data-stu-id="eb946-117">Remarks</span></span>  
 <span data-ttu-id="eb946-118">현재 유일한 정의 대 한 값 `dwInitializeDomainFlags` 됩니다 `eInitializeNewDomainFlags_NoSecurityChanges`를 CLR (공용 언어 런타임)을 설정 하는 응용 프로그램 도메인 관리자를 실행 하는 동안 보안 설정을 수정 하지는 알려줍니다는 <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="eb946-118">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="eb946-119">이렇게 하면 조건부가 있는 어셈블리의 로드를 최적화 하기 위해 CLR <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="eb946-119">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="eb946-120">이 값은이 어셈블리 집합의 전이적 closure 크면 시작 시간을 대폭 개선할에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb946-120">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eb946-121">호스트를 지정 하는 경우 `eInitializeNewDomainFlags_NoSecurityChanges` 응용 프로그램 도메인 관리자는 <xref:System.InvalidOperationException> 응용 프로그램 도메인의 보안을 수정 하 려 하는 경우 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb946-121">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="eb946-122">호출 된 [iclrcontrol:: Setappdomainmanagertype](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)호출 하는 것과 같습니다 `ICLRDomainManager::SetAppDomainManagerType` 사용 하 여 `eInitializeNewDomainFlags_None`입니다.</span><span class="sxs-lookup"><span data-stu-id="eb946-122">Calling the [ICLRControl::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb946-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eb946-123">Requirements</span></span>  
 <span data-ttu-id="eb946-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="eb946-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb946-125">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="eb946-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="eb946-126">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="eb946-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="eb946-127">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="eb946-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="eb946-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="eb946-128">See also</span></span>

- [<span data-ttu-id="eb946-129">호스팅</span><span class="sxs-lookup"><span data-stu-id="eb946-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="eb946-130">ICLRDomainManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eb946-130">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
- [<span data-ttu-id="eb946-131">EInitializeNewDomainFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="eb946-131">EInitializeNewDomainFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
