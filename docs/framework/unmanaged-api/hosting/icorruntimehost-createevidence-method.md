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
ms.openlocfilehash: 6627fce519934177aefd26a612e5b00ca1941d02
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715669"
---
# <a name="icorruntimehostcreateevidence-method"></a><span data-ttu-id="1bb52-102">ICorRuntimeHost::CreateEvidence 메서드</span><span class="sxs-lookup"><span data-stu-id="1bb52-102">ICorRuntimeHost::CreateEvidence Method</span></span>

<span data-ttu-id="1bb52-103"><xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>호스트가 [createdomain](icorruntimehost-createdomain-method.md) 또는 [createdomainex](icorruntimehost-createdomainex-method.md) 메서드에 전달할 보안 증명 정보를 만들 수 있도록 하는 형식의 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1bb52-103">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, which allows the host to create security evidence to pass to the [CreateDomain](icorruntimehost-createdomain-method.md) or [CreateDomainEx](icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bb52-104">구문</span><span class="sxs-lookup"><span data-stu-id="1bb52-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bb52-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1bb52-105">Parameters</span></span>  

 `pEvidence`  
 <span data-ttu-id="1bb52-106">제한이 <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> 보안 증명 정보를 만드는 데 사용 된 인스턴스에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1bb52-106">[out] A interface pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instance used to create security evidence.</span></span> <span data-ttu-id="1bb52-107">이 포인터는 형식화 되어 `IUnknown` 있으므로 호출자는 일반적으로 `QueryInterface` 이 인터페이스에서를 호출 하 여에 대 한 포인터를 가져와야 합니다 <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="1bb52-107">This pointer is typed `IUnknown`, so callers should typically call `QueryInterface` on this interface to obtain a pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1bb52-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="1bb52-108">Return Value</span></span>  
  
|<span data-ttu-id="1bb52-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1bb52-109">HRESULT</span></span>|<span data-ttu-id="1bb52-110">설명</span><span class="sxs-lookup"><span data-stu-id="1bb52-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1bb52-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1bb52-111">S_OK</span></span>|<span data-ttu-id="1bb52-112">작업이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb52-112">The operation was successful.</span></span>|  
|<span data-ttu-id="1bb52-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="1bb52-113">S_FALSE</span></span>|<span data-ttu-id="1bb52-114">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb52-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="1bb52-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1bb52-115">E_FAIL</span></span>|<span data-ttu-id="1bb52-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb52-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="1bb52-117">메서드가 E_FAIL 반환 하는 경우 해당 프로세스에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb52-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="1bb52-118">호스팅 Api에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bb52-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1bb52-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1bb52-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1bb52-120">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bb52-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bb52-121">설명</span><span class="sxs-lookup"><span data-stu-id="1bb52-121">Remarks</span></span>  

 <span data-ttu-id="1bb52-122">이 메서드는 네이티브 코드에서 채울 수 없는 빈 컬렉션을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bb52-122">This method returns an empty collection that cannot be populated from native code.</span></span> <span data-ttu-id="1bb52-123">대신 메서드를 사용 해야 <xref:System.Security.Policy.Evidence> 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bb52-123">You should use the <xref:System.Security.Policy.Evidence> method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bb52-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1bb52-124">Requirements</span></span>  

 <span data-ttu-id="1bb52-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bb52-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bb52-126">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1bb52-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1bb52-127">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bb52-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1bb52-128">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="1bb52-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bb52-129">참조</span><span class="sxs-lookup"><span data-stu-id="1bb52-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="1bb52-130">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1bb52-130">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
