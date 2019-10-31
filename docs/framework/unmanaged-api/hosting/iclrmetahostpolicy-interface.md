---
title: ICLRMetaHostPolicy 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy
helpviewer_keywords:
- ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type:
- apiref
ms.openlocfilehash: 277c13895374116eb67f6515f45df638f61b0453
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140861"
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="d1428-102">ICLRMetaHostPolicy 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1428-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="d1428-103">정책 기준, 관리 되는 어셈블리, 버전 및 구성 파일을 기반으로 CLR (공용 언어 런타임) 인터페이스에 대 한 포인터를 반환 하는 [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1428-103">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d1428-104">메서드</span><span class="sxs-lookup"><span data-stu-id="d1428-104">Methods</span></span>  
  
|<span data-ttu-id="d1428-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d1428-105">Method</span></span>|<span data-ttu-id="d1428-106">설명</span><span class="sxs-lookup"><span data-stu-id="d1428-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d1428-107">GetRequestedRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="d1428-107">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="d1428-108">정책 기준, 관리 되는 어셈블리, 버전 및 구성 파일을 기반으로 기본 CLR 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1428-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1428-109">주의</span><span class="sxs-lookup"><span data-stu-id="d1428-109">Remarks</span></span>  
 <span data-ttu-id="d1428-110">다음 코드와 같이 [Clrcreateinstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) 함수를 호출 하 여이 인터페이스에 대 한 참조를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1428-110">You can get a reference to this interface by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> <span data-ttu-id="d1428-111">이 인터페이스는 실제로 CLR을 로드 하거나 활성화 하지 않지만 설치 또는 로드 된 사용 가능한 버전에 따라 기본 CLR 버전을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1428-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="d1428-112">.NET Framework 4 호스팅 API는 정책을 통합 하므로 특정 요구 사항이 있는 호스트에서 의도 하지 않은 페널티를 발생 시 키 지 않고 기본 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1428-112">The .NET Framework 4 hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="d1428-113">예를 들어, 대부분의 Mscoree.dll 내보내기는 특정 CLR에 바인딩되고, 메서드는 논리적으로이를 요구 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1428-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="d1428-114">[METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) 열거형은 대부분의 호스트에 공통 되는 바인딩 정책을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1428-114">The [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1428-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1428-115">Requirements</span></span>  
 <span data-ttu-id="d1428-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1428-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1428-117">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="d1428-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d1428-118">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1428-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d1428-119">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1428-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1428-120">참조</span><span class="sxs-lookup"><span data-stu-id="d1428-120">See also</span></span>

- [<span data-ttu-id="d1428-121">.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1428-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="d1428-122">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1428-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="d1428-123">호스팅</span><span class="sxs-lookup"><span data-stu-id="d1428-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
