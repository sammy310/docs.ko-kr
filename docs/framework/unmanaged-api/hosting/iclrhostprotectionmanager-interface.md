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
ms.openlocfilehash: e8ead998907d55b0bfbf82e5f6f4e7c504f657ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714161"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="8cf40-102">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8cf40-102">ICLRHostProtectionManager Interface</span></span>

<span data-ttu-id="8cf40-103">호스트에서 특정 관리 되는 클래스, 메서드, 속성 및 필드가 부분적으로 신뢰할 수 있는 코드에서 실행 되는 것을 차단할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf40-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8cf40-104">메서드</span><span class="sxs-lookup"><span data-stu-id="8cf40-104">Methods</span></span>  
  
|<span data-ttu-id="8cf40-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8cf40-105">Method</span></span>|<span data-ttu-id="8cf40-106">설명</span><span class="sxs-lookup"><span data-stu-id="8cf40-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8cf40-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="8cf40-107">SetEagerSerializeGrantSets</span></span>](iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="8cf40-108">는 심각한 CLR (공용 언어 런타임) 오류를 일으킬 수 있는 드문 경합 상태를 발생 시 키 지 않도록 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf40-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="8cf40-109">SetProtectedCategories 메서드</span><span class="sxs-lookup"><span data-stu-id="8cf40-109">SetProtectedCategories Method</span></span>](iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="8cf40-110">부분적으로 신뢰할 수 있는 코드에서 실행 되는 것을 차단 해야 하는 관리 되는 형식 및 멤버의 범주를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf40-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8cf40-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8cf40-111">Requirements</span></span>  

 <span data-ttu-id="8cf40-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8cf40-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cf40-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8cf40-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8cf40-114">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cf40-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8cf40-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cf40-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cf40-116">참조</span><span class="sxs-lookup"><span data-stu-id="8cf40-116">See also</span></span>

- [<span data-ttu-id="8cf40-117">EApiCategories 열거형</span><span class="sxs-lookup"><span data-stu-id="8cf40-117">EApiCategories Enumeration</span></span>](eapicategories-enumeration.md)
- [<span data-ttu-id="8cf40-118">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8cf40-118">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
