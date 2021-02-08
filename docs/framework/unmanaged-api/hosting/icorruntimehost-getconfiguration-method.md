---
description: '자세히 알아보기: ICorRuntimeHost:: GetConfiguration 메서드'
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
ms.openlocfilehash: d3e3f065c3957fb29daa11ed7c46858a53865c91
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784836"
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="91541-103">ICorRuntimeHost::GetConfiguration 메서드</span><span class="sxs-lookup"><span data-stu-id="91541-103">ICorRuntimeHost::GetConfiguration Method</span></span>

<span data-ttu-id="91541-104">호스트가 CLR (공용 언어 런타임)의 콜백 구성을 지정 하는 데 사용할 수 있는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="91541-104">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91541-105">구문</span><span class="sxs-lookup"><span data-stu-id="91541-105">Syntax</span></span>  
  
```cpp  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91541-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="91541-106">Parameters</span></span>  

 `pConfiguration`  
 <span data-ttu-id="91541-107">제한이 CLR을 구성 하는 데 사용할 수 있는 [ICorConfiguration](icorconfiguration-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="91541-107">[out] A pointer to the address of an [ICorConfiguration](icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91541-108">설명</span><span class="sxs-lookup"><span data-stu-id="91541-108">Remarks</span></span>  

 <span data-ttu-id="91541-109">CLR은 초기화 되기 전에 구성 해야 합니다. 그렇지 않으면 `GetConfiguration` 메서드는 오류를 나타내는 HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="91541-109">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91541-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="91541-110">Requirements</span></span>  

 <span data-ttu-id="91541-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="91541-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91541-112">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="91541-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="91541-113">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91541-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91541-114">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="91541-114">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91541-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91541-115">See also</span></span>

- [<span data-ttu-id="91541-116">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="91541-116">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
