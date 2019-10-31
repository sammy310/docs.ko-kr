---
title: ICLRHostProtectionManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager
helpviewer_keywords:
- ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type:
- apiref
ms.openlocfilehash: 0487a87420c888cf5466f54c28c2d89623260add
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141055"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="32b02-102">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32b02-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="32b02-103">호스트에서 특정 관리 되는 클래스, 메서드, 속성 및 필드가 부분적으로 신뢰할 수 있는 코드에서 실행 되는 것을 차단할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="32b02-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="32b02-104">메서드</span><span class="sxs-lookup"><span data-stu-id="32b02-104">Methods</span></span>  
  
|<span data-ttu-id="32b02-105">메서드</span><span class="sxs-lookup"><span data-stu-id="32b02-105">Method</span></span>|<span data-ttu-id="32b02-106">설명</span><span class="sxs-lookup"><span data-stu-id="32b02-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="32b02-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="32b02-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="32b02-108">는 심각한 CLR (공용 언어 런타임) 오류를 일으킬 수 있는 드문 경합 상태를 발생 시 키 지 않도록 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="32b02-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="32b02-109">SetProtectedCategories 메서드</span><span class="sxs-lookup"><span data-stu-id="32b02-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="32b02-110">부분적으로 신뢰할 수 있는 코드에서 실행 되는 것을 차단 해야 하는 관리 되는 형식 및 멤버의 범주를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="32b02-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="32b02-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32b02-111">Requirements</span></span>  
 <span data-ttu-id="32b02-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32b02-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32b02-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="32b02-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32b02-114">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32b02-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32b02-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32b02-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32b02-116">참조</span><span class="sxs-lookup"><span data-stu-id="32b02-116">See also</span></span>

- [<span data-ttu-id="32b02-117">EApiCategories 열거형</span><span class="sxs-lookup"><span data-stu-id="32b02-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="32b02-118">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32b02-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
