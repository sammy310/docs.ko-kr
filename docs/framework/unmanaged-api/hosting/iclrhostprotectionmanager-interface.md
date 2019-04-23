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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd096344c987d8901f0baab86e370abbb03528e5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177777"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="c6f82-102">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6f82-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="c6f82-103">특정 관리 되는 클래스, 메서드, 속성 및 부분적으로 신뢰할 수 있는 코드에서 실행 되는 필드를 차단 하도록 호스트를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f82-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c6f82-104">메서드</span><span class="sxs-lookup"><span data-stu-id="c6f82-104">Methods</span></span>  
  
|<span data-ttu-id="c6f82-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c6f82-105">Method</span></span>|<span data-ttu-id="c6f82-106">설명</span><span class="sxs-lookup"><span data-stu-id="c6f82-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c6f82-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="c6f82-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="c6f82-108">심각한 공용 언어 런타임 (CLR) 오류를 일으킬 수 있는 경합 상태가 발생 하지 않도록 합니다 보장을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f82-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="c6f82-109">SetProtectedCategories 메서드</span><span class="sxs-lookup"><span data-stu-id="c6f82-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="c6f82-110">관리 되는 형식 및 부분적으로 신뢰할 수 있는 코드의 실행에서 차단 해야 하는 멤버의 범주를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6f82-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c6f82-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6f82-111">Requirements</span></span>  
 <span data-ttu-id="c6f82-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c6f82-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6f82-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c6f82-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6f82-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c6f82-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6f82-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6f82-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6f82-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="c6f82-116">See also</span></span>

- [<span data-ttu-id="c6f82-117">EApiCategories 열거형</span><span class="sxs-lookup"><span data-stu-id="c6f82-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="c6f82-118">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6f82-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
