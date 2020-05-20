---
title: ICLRHostBindingPolicyManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager
helpviewer_keywords:
- ICLRHostBindingPolicyManager interface [.NET Framework hosting]
ms.assetid: f9da168b-366b-4b2b-bdb9-330b6bad5a6b
topic_type:
- apiref
ms.openlocfilehash: 3cf2a945607bf85a51dbec35342ff5ac46878bca
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703575"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="73499-102">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73499-102">ICLRHostBindingPolicyManager Interface</span></span>
<span data-ttu-id="73499-103">호스트에서 현재 바인딩 정책을 평가 하 고 지정 된 어셈블리에 대 한 정책 변경 내용을 전달 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="73499-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="73499-104">메서드</span><span class="sxs-lookup"><span data-stu-id="73499-104">Methods</span></span>  
  
|<span data-ttu-id="73499-105">메서드</span><span class="sxs-lookup"><span data-stu-id="73499-105">Method</span></span>|<span data-ttu-id="73499-106">설명</span><span class="sxs-lookup"><span data-stu-id="73499-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="73499-107">EvaluatePolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="73499-107">EvaluatePolicy Method</span></span>](iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="73499-108">호스트를 대신 하 여 바인딩 정책을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="73499-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="73499-109">ModifyApplicationPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="73499-109">ModifyApplicationPolicy Method</span></span>](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="73499-110">지정 된 어셈블리에 대 한 바인딩 정책을 수정 하 고 정책의 새 버전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="73499-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73499-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="73499-111">Requirements</span></span>  
 <span data-ttu-id="73499-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73499-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73499-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="73499-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="73499-114">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73499-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73499-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73499-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73499-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73499-116">See also</span></span>

- [<span data-ttu-id="73499-117">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73499-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="73499-118">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73499-118">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="73499-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73499-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
