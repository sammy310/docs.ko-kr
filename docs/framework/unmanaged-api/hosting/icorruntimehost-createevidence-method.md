---
title: ICorRuntimeHost::CreateEvidence 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateEvidence
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateEvidence
helpviewer_keywords:
- CreateEvidence method [.NET Framework hosting]
- ICorRuntimeHost::CreateEvidence method [.NET Framework hosting]
ms.assetid: e235ea80-b84c-4442-a4c3-fc96c25a8eb9
topic_type:
- apiref
ms.openlocfilehash: 429ce0510162b3256cdf58f4820b04dd80243e29
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139640"
---
# <a name="icorruntimehostcreateevidence-method"></a><span data-ttu-id="799e8-102">ICorRuntimeHost::CreateEvidence 메서드</span><span class="sxs-lookup"><span data-stu-id="799e8-102">ICorRuntimeHost::CreateEvidence Method</span></span>
<span data-ttu-id="799e8-103">호스트가 [Createdomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) 또는 [createdomainex](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) 메서드에 전달할 보안 증명 정보를 만들 수 있도록 하는 <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>형식의 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="799e8-103">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, which allows the host to create security evidence to pass to the [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="799e8-104">구문</span><span class="sxs-lookup"><span data-stu-id="799e8-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="799e8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="799e8-105">Parameters</span></span>  
 `pEvidence`  
 <span data-ttu-id="799e8-106">제한이 보안 증명 정보를 만드는 데 사용 되는 <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> 인스턴스에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="799e8-106">[out] A interface pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instance used to create security evidence.</span></span> <span data-ttu-id="799e8-107">이 포인터는 `IUnknown`형식화 되므로 호출자는 일반적으로이 인터페이스에서 `QueryInterface`를 호출 하 여 <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>에 대 한 포인터를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="799e8-107">This pointer is typed `IUnknown`, so callers should typically call `QueryInterface` on this interface to obtain a pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="799e8-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="799e8-108">Return Value</span></span>  
  
|<span data-ttu-id="799e8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="799e8-109">HRESULT</span></span>|<span data-ttu-id="799e8-110">설명</span><span class="sxs-lookup"><span data-stu-id="799e8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="799e8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="799e8-111">S_OK</span></span>|<span data-ttu-id="799e8-112">작업에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="799e8-112">The operation was successful.</span></span>|  
|<span data-ttu-id="799e8-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="799e8-113">S_FALSE</span></span>|<span data-ttu-id="799e8-114">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="799e8-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="799e8-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="799e8-115">E_FAIL</span></span>|<span data-ttu-id="799e8-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="799e8-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="799e8-117">메서드가 E_FAIL을 반환 하는 경우 프로세스에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="799e8-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="799e8-118">모든 호스팅 Api에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="799e8-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="799e8-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="799e8-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="799e8-120">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="799e8-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="799e8-121">주의</span><span class="sxs-lookup"><span data-stu-id="799e8-121">Remarks</span></span>  
 <span data-ttu-id="799e8-122">이 메서드는 네이티브 코드에서 채울 수 없는 빈 컬렉션을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="799e8-122">This method returns an empty collection that cannot be populated from native code.</span></span> <span data-ttu-id="799e8-123"><xref:System.Security.Policy.Evidence> 메서드를 대신 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="799e8-123">You should use the <xref:System.Security.Policy.Evidence> method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="799e8-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="799e8-124">Requirements</span></span>  
 <span data-ttu-id="799e8-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="799e8-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="799e8-126">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="799e8-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="799e8-127">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="799e8-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="799e8-128">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="799e8-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="799e8-129">참조</span><span class="sxs-lookup"><span data-stu-id="799e8-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="799e8-130">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="799e8-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
