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
ms.openlocfilehash: bb7c3659930f308328cba121c06a88cb6a95eb26
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504162"
---
# <a name="iclrmetahost-interface"></a><span data-ttu-id="3a550-102">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a550-102">ICLRMetaHost Interface</span></span>
<span data-ttu-id="3a550-103">버전 번호에 따라 특정 버전의 CLR (공용 언어 런타임)을 반환 하 고, 모든 설치 된 Clr을 나열 하 고, 지정 된 프로세스에서 로드 되는 모든 런타임을 나열 하 고, 어셈블리를 컴파일하는 데 사용 되는 CLR 버전을 검색 하 고, 정리 된 런타임 종료를 사용 하 여 프로세스를 끝내 고, 레거시 API 바인딩을 쿼리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a550-103">Provides methods that return a specific version of the common language runtime (CLR) based on its version number, list all installed CLRs, list all runtimes that are loaded in a specified process, discover the CLR version used to compile an assembly, exit a process with a clean runtime shutdown, and query legacy API binding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3a550-104">메서드</span><span class="sxs-lookup"><span data-stu-id="3a550-104">Methods</span></span>  
  
|<span data-ttu-id="3a550-105">방법</span><span class="sxs-lookup"><span data-stu-id="3a550-105">Method</span></span>|<span data-ttu-id="3a550-106">설명</span><span class="sxs-lookup"><span data-stu-id="3a550-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3a550-107">EnumerateInstalledRuntimes 메서드</span><span class="sxs-lookup"><span data-stu-id="3a550-107">EnumerateInstalledRuntimes Method</span></span>](iclrmetahost-enumerateinstalledruntimes-method.md)|<span data-ttu-id="3a550-108">컴퓨터에 설치 된 각 CLR 버전에 대 한 유효한 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 인터페이스 포인터를 포함 하는 열거형을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a550-108">Returns an enumeration that contains a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface pointer for each CLR version that is installed on a computer.</span></span>|  
|[<span data-ttu-id="3a550-109">EnumerateLoadedRuntimes 메서드</span><span class="sxs-lookup"><span data-stu-id="3a550-109">EnumerateLoadedRuntimes Method</span></span>](iclrmetahost-enumerateloadedruntimes-method.md)|<span data-ttu-id="3a550-110">지정 된 프로세스에 로드 된 각 CLR에 대해 유효한 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 인터페이스 포인터를 포함 하는 열거형을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a550-110">Returns an enumeration that contains a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface pointer for each CLR that is loaded in a given process.</span></span> <span data-ttu-id="3a550-111">이 메서드는 [Getversionfromprocess](getversionfromprocess-function.md)를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a550-111">This method supersedes [GetVersionFromProcess](getversionfromprocess-function.md).</span></span>|  
|[<span data-ttu-id="3a550-112">ExitProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="3a550-112">ExitProcess Method</span></span>](iclrmetahost-exitprocess-method.md)|<span data-ttu-id="3a550-113">로드 된 모든 런타임을 정상적으로 종료 하 고 프로세스를 종료 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a550-113">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="3a550-114">[Corexitprocess](corexitprocess-function.md) 함수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a550-114">Supersedes the [CorExitProcess](corexitprocess-function.md) function.</span></span>|  
|[<span data-ttu-id="3a550-115">GetRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="3a550-115">GetRuntime Method</span></span>](iclrmetahost-getruntime-method.md)|<span data-ttu-id="3a550-116">특정 CLR 버전에 해당 하는 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3a550-116">Gets the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that corresponds to a particular CLR version.</span></span> <span data-ttu-id="3a550-117">이 메서드는 [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) 플래그와 함께 사용 되는 [CorBindToRuntimeEx](corbindtoruntimeex-function.md) 함수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a550-117">This method supersedes the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) flag.</span></span>|  
|[<span data-ttu-id="3a550-118">GetVersionFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="3a550-118">GetVersionFromFile Method</span></span>](iclrmetahost-getversionfromfile-method.md)|<span data-ttu-id="3a550-119">해당 파일 경로가 지정 된 경우 메타 데이터에 저장 된 어셈블리의 원래 .NET Framework 컴파일 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3a550-119">Gets the assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="3a550-120">이 메서드는 [GetFileVersion](getfileversion-function.md)을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a550-120">This method supersedes [GetFileVersion](getfileversion-function.md).</span></span>|  
|[<span data-ttu-id="3a550-121">QueryLegacyV2RuntimeBinding 메서드</span><span class="sxs-lookup"><span data-stu-id="3a550-121">QueryLegacyV2RuntimeBinding Method</span></span>](iclrmetahost-querylegacyv2runtimebinding-method.md)|<span data-ttu-id="3a550-122">레거시 정품 인증 정책이 바인딩된 런타임을 나타내는 인터페이스를 반환 합니다. 예를 들어 `useLegacyV2RuntimeActivationPolicy` , 레거시 활성화 api를 직접 사용 하거나 [ICLRRuntimeInfo:: BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) 메서드를 호출 하 여 [ \<startup> 요소](../../configure-apps/file-schema/startup/startup-element.md) 구성 파일 항목의 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a550-122">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> Element](../../configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>|  
|[<span data-ttu-id="3a550-123">RequestRuntimeLoadedNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="3a550-123">RequestRuntimeLoadedNotification Method</span></span>](iclrmetahost-requestruntimeloadednotification-method.md)|<span data-ttu-id="3a550-124">CLR 버전이 처음 로드 되었지만 아직 시작 되지 않은 경우 지정 된 함수 포인터에 대 한 콜백을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a550-124">Guarantees a callback to the specified function pointer when a CLR version is first loaded, but not yet started.</span></span> <span data-ttu-id="3a550-125">이 메서드는 [Lockclrversion](lockclrversion-function.md) 을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a550-125">This method supersedes [LockClrVersion](lockclrversion-function.md)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a550-126">설명</span><span class="sxs-lookup"><span data-stu-id="3a550-126">Remarks</span></span>  
 <span data-ttu-id="3a550-127">이 인터페이스의 인스턴스를 가져오는 유일한 방법은 다음과 같이 [Clrcreateinstance](clrcreateinstance-function.md) 함수를 호출 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3a550-127">The only way to get an instance of this interface is by calling the [CLRCreateInstance](clrcreateinstance-function.md) function as follows:</span></span>  
  
```cpp  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a><span data-ttu-id="3a550-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a550-128">Requirements</span></span>  
 <span data-ttu-id="3a550-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a550-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a550-130">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="3a550-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3a550-131">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a550-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a550-132">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a550-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a550-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a550-133">See also</span></span>

- [<span data-ttu-id="3a550-134">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a550-134">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="3a550-135">호스팅</span><span class="sxs-lookup"><span data-stu-id="3a550-135">Hosting</span></span>](index.md)
