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
ms.openlocfilehash: 7c6b328793e6437682ad8d642e611be30e7b0fe6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702150"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="63081-102">ICLRDomainManager::SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="63081-102">ICLRDomainManager::SetAppDomainManagerType Method</span></span>

<span data-ttu-id="63081-103"><xref:System.AppDomainManager?displayProperty=nameWithType>기본 응용 프로그램 도메인을 초기화 하는 데 사용 되는 응용 프로그램 도메인 관리자의 클래스에서 파생 된 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="63081-103">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63081-104">구문</span><span class="sxs-lookup"><span data-stu-id="63081-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63081-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="63081-105">Parameters</span></span>  

 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="63081-106">진행 응용 프로그램 도메인 관리자 유형을 포함 하는 어셈블리의 표시 이름입니다. 예: "AdMgrExample, Version = 1.0.0.0, Culture = 중립, PublicKeyToken = 6856bccf150f00b3".</span><span class="sxs-lookup"><span data-stu-id="63081-106">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="63081-107">진행 네임 스페이스를 포함 하는 응용 프로그램 도메인 관리자의 유형 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="63081-107">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="63081-108">진행 응용 프로그램 도메인 관리자에 대 한 정보를 제공 하는 [EInitializeNewDomainFlags](einitializenewdomainflags-enumeration.md) 열거형 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="63081-108">[in] A combination of [EInitializeNewDomainFlags](einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63081-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="63081-109">Return Value</span></span>  

 <span data-ttu-id="63081-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="63081-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="63081-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="63081-111">HRESULT</span></span>|<span data-ttu-id="63081-112">설명</span><span class="sxs-lookup"><span data-stu-id="63081-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="63081-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="63081-113">S_OK</span></span>|<span data-ttu-id="63081-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="63081-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="63081-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="63081-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="63081-116">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63081-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63081-117">설명</span><span class="sxs-lookup"><span data-stu-id="63081-117">Remarks</span></span>  

 <span data-ttu-id="63081-118">현재에 대해 정의 된 유일한 값은 `dwInitializeDomainFlags` 이며,이는 `eInitializeNewDomainFlags_NoSecurityChanges` 응용 프로그램 도메인 관리자가 메서드를 실행 하는 동안 보안 설정을 수정 하지 않음을 CLR (공용 언어 런타임)에 지시 하는입니다 <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="63081-118">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="63081-119">이렇게 하면 CLR에서 조건부 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) 특성이 있는 어셈블리 로드를 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63081-119">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="63081-120">이로 인해이 어셈블리 집합의 전이적 클로저가 큰 경우 시작 시간이 크게 향상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63081-120">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="63081-121">호스트에서 `eInitializeNewDomainFlags_NoSecurityChanges` 응용 프로그램 도메인 관리자를 지정 하는 경우 <xref:System.InvalidOperationException> 응용 프로그램 도메인의 보안을 수정 하려고 시도 하면이 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63081-121">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="63081-122">[ICLRControl:: SetAppDomainManagerType](iclrcontrol-setappdomainmanagertype-method.md)메서드를 호출 하는 것은로를 호출 하는 것과 같습니다 `ICLRDomainManager::SetAppDomainManagerType` `eInitializeNewDomainFlags_None` .</span><span class="sxs-lookup"><span data-stu-id="63081-122">Calling the [ICLRControl::SetAppDomainManagerType](iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63081-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="63081-123">Requirements</span></span>  

 <span data-ttu-id="63081-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63081-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63081-125">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="63081-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="63081-126">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63081-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63081-127">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63081-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63081-128">참조</span><span class="sxs-lookup"><span data-stu-id="63081-128">See also</span></span>

- [<span data-ttu-id="63081-129">호스팅</span><span class="sxs-lookup"><span data-stu-id="63081-129">Hosting</span></span>](index.md)
- [<span data-ttu-id="63081-130">ICLRDomainManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="63081-130">ICLRDomainManager Interface</span></span>](iclrdomainmanager-interface.md)
- [<span data-ttu-id="63081-131">EInitializeNewDomainFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="63081-131">EInitializeNewDomainFlags Enumeration</span></span>](einitializenewdomainflags-enumeration.md)
