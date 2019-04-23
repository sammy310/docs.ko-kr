---
title: ICLRMetaHost 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRMetaHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost
helpviewer_keywords:
- ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1b189b79a02f04b7f795ff2524441f12b053cec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59143951"
---
# <a name="iclrmetahost-interface"></a><span data-ttu-id="14cc8-102">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="14cc8-102">ICLRMetaHost Interface</span></span>
<span data-ttu-id="14cc8-103">해당 버전 번호를 기준으로 CLR (공용 언어 런타임)의 특정 버전을 반환, 모든 설치 된 Clr list, 지정된 된 프로세스에 로드 되는 모든 런타임 목록, 어셈블리로 컴파일, 프로세스를 종료 하는 데 CLR 버전을 검색 하는 메서드를 제공 합니다. 깨끗 한 런타임이 종료 및 레거시 API 바인딩을 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cc8-103">Provides methods that return a specific version of the common language runtime (CLR) based on its version number, list all installed CLRs, list all runtimes that are loaded in a specified process, discover the CLR version used to compile an assembly, exit a process with a clean runtime shutdown, and query legacy API binding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="14cc8-104">메서드</span><span class="sxs-lookup"><span data-stu-id="14cc8-104">Methods</span></span>  
  
|<span data-ttu-id="14cc8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="14cc8-105">Method</span></span>|<span data-ttu-id="14cc8-106">설명</span><span class="sxs-lookup"><span data-stu-id="14cc8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="14cc8-107">EnumerateInstalledRuntimes 메서드</span><span class="sxs-lookup"><span data-stu-id="14cc8-107">EnumerateInstalledRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateinstalledruntimes-method.md)|<span data-ttu-id="14cc8-108">유효한 포함 하는 열거자를 반환 합니다 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 컴퓨터에 설치 되어 있는 각 CLR 버전에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="14cc8-108">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each CLR version that is installed on a computer.</span></span>|  
|[<span data-ttu-id="14cc8-109">EnumerateLoadedRuntimes 메서드</span><span class="sxs-lookup"><span data-stu-id="14cc8-109">EnumerateLoadedRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateloadedruntimes-method.md)|<span data-ttu-id="14cc8-110">유효한 포함 하는 열거자를 반환 합니다 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 주어진된 프로세스에서 로드 되는 각 CLR에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="14cc8-110">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each CLR that is loaded in a given process.</span></span> <span data-ttu-id="14cc8-111">이 메서드를 대체 [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="14cc8-111">This method supersedes [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md).</span></span>|  
|[<span data-ttu-id="14cc8-112">ExitProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="14cc8-112">ExitProcess Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)|<span data-ttu-id="14cc8-113">로드 된 모든 런타임을 정상적으로 종료 하 고 프로세스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cc8-113">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="14cc8-114">대체는 [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="14cc8-114">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>|  
|[<span data-ttu-id="14cc8-115">GetRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="14cc8-115">GetRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)|<span data-ttu-id="14cc8-116">가져옵니다 합니다 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 특정 CLR 버전에 해당 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="14cc8-116">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular CLR version.</span></span> <span data-ttu-id="14cc8-117">이 메서드를 대체 합니다 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수를 사용 합니다 [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="14cc8-117">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) flag.</span></span>|  
|[<span data-ttu-id="14cc8-118">GetVersionFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="14cc8-118">GetVersionFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getversionfromfile-method.md)|<span data-ttu-id="14cc8-119">파일 경로가 지정 된 어셈블리의 원래.net 컴파일 버전을 (메타 데이터에 저장 됨)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="14cc8-119">Gets the assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="14cc8-120">이 메서드를 대체 [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="14cc8-120">This method supersedes [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md).</span></span>|  
|[<span data-ttu-id="14cc8-121">QueryLegacyV2RuntimeBinding 메서드</span><span class="sxs-lookup"><span data-stu-id="14cc8-121">QueryLegacyV2RuntimeBinding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-querylegacyv2runtimebinding-method.md)|<span data-ttu-id="14cc8-122">레거시 활성화 정책이 바인딩된, 예를 들어 사용 하 여 런타임을 나타내는 인터페이스를 반환 합니다 `useLegacyV2RuntimeActivationPolicy` 특성을 합니다 [ \<시작 > 요소](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) 직접 사용 하 여 구성 파일 항목 호출 하거나 레거시 활성화 Api는 [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="14cc8-122">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>|  
|[<span data-ttu-id="14cc8-123">RequestRuntimeLoadedNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="14cc8-123">RequestRuntimeLoadedNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-requestruntimeloadednotification-method.md)|<span data-ttu-id="14cc8-124">CLR 버전을 처음 로드 되었지만 아직 시작 하지 않은 경우 지정 된 함수 포인터에 대 한 콜백의 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="14cc8-124">Guarantees a callback to the specified function pointer when a CLR version is first loaded, but not yet started.</span></span> <span data-ttu-id="14cc8-125">이 메서드를 대체 [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)</span><span class="sxs-lookup"><span data-stu-id="14cc8-125">This method supersedes [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14cc8-126">설명</span><span class="sxs-lookup"><span data-stu-id="14cc8-126">Remarks</span></span>  
 <span data-ttu-id="14cc8-127">호출 하 여이 인터페이스의 인스턴스를 가져올 유일한 방법은는 [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) 같이 함수:</span><span class="sxs-lookup"><span data-stu-id="14cc8-127">The only way to get an instance of this interface is by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as follows:</span></span>  
  
```  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a><span data-ttu-id="14cc8-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="14cc8-128">Requirements</span></span>  
 <span data-ttu-id="14cc8-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="14cc8-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14cc8-130">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="14cc8-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="14cc8-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="14cc8-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="14cc8-132">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14cc8-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14cc8-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="14cc8-133">See also</span></span>

- [<span data-ttu-id="14cc8-134">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="14cc8-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="14cc8-135">호스팅</span><span class="sxs-lookup"><span data-stu-id="14cc8-135">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
