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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e494bbbd08a77329b7b64816216e4bb2e1b724a2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074198"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="85a01-102">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85a01-102">ICLRHostBindingPolicyManager Interface</span></span>
<span data-ttu-id="85a01-103">현재 바인딩 정책을 확인 하 고 지정된 된 어셈블리에 대 한 정책 변경 내용을 알리는 호스트에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a01-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="85a01-104">메서드</span><span class="sxs-lookup"><span data-stu-id="85a01-104">Methods</span></span>  
  
|<span data-ttu-id="85a01-105">메서드</span><span class="sxs-lookup"><span data-stu-id="85a01-105">Method</span></span>|<span data-ttu-id="85a01-106">설명</span><span class="sxs-lookup"><span data-stu-id="85a01-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="85a01-107">EvaluatePolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="85a01-107">EvaluatePolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="85a01-108">호스트를 대신 하 여 바인딩 정책을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="85a01-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="85a01-109">ModifyApplicationPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="85a01-109">ModifyApplicationPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="85a01-110">지정된 된 어셈블리에 대 한 바인딩 정책 수정 하 고 정책의 새 버전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85a01-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="85a01-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85a01-111">Requirements</span></span>  
 <span data-ttu-id="85a01-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="85a01-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85a01-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="85a01-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85a01-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="85a01-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="85a01-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="85a01-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="85a01-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="85a01-116">See also</span></span>

- [<span data-ttu-id="85a01-117">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85a01-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="85a01-118">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85a01-118">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="85a01-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85a01-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
