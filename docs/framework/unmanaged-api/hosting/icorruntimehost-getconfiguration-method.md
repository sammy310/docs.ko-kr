---
title: ICorRuntimeHost::GetConfiguration 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type:
- apiref
ms.openlocfilehash: 2a50814a67be5a01a7413050683a915355665f3c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720648"
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="635dc-102">ICorRuntimeHost::GetConfiguration 메서드</span><span class="sxs-lookup"><span data-stu-id="635dc-102">ICorRuntimeHost::GetConfiguration Method</span></span>

<span data-ttu-id="635dc-103">호스트가 CLR (공용 언어 런타임)의 콜백 구성을 지정 하는 데 사용할 수 있는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="635dc-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="635dc-104">구문</span><span class="sxs-lookup"><span data-stu-id="635dc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="635dc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="635dc-105">Parameters</span></span>  

 `pConfiguration`  
 <span data-ttu-id="635dc-106">제한이 CLR을 구성 하는 데 사용할 수 있는 [ICorConfiguration](icorconfiguration-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="635dc-106">[out] A pointer to the address of an [ICorConfiguration](icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="635dc-107">설명</span><span class="sxs-lookup"><span data-stu-id="635dc-107">Remarks</span></span>  

 <span data-ttu-id="635dc-108">CLR은 초기화 되기 전에 구성 해야 합니다. 그렇지 않으면 `GetConfiguration` 메서드는 오류를 나타내는 HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="635dc-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="635dc-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="635dc-109">Requirements</span></span>  

 <span data-ttu-id="635dc-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="635dc-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="635dc-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="635dc-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="635dc-112">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="635dc-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="635dc-113">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="635dc-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="635dc-114">참조</span><span class="sxs-lookup"><span data-stu-id="635dc-114">See also</span></span>

- [<span data-ttu-id="635dc-115">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="635dc-115">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
